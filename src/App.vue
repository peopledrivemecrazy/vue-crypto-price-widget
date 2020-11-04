<template>
  <nav>
    <ul>
      <li>
        <a
          href="https://github.com/peopledrivemecrazy/vue-crypto-price-widget"
          target="_blank"
          rel="noopener"
          >github</a
        >
      </li>
    </ul>
  </nav>
  <main>
    <div class="flex-grid">
      <div v-if="feed.length==0">loading...</div>
      <div v-else v-for="(item, index) in feed" :key="index" class="col">
        <div class="card">
          <div class="card-text">
            <p>
              {{ item.coin }}
            </p>
            <p>
              {{ item.price }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer class="text-center">
    <p>from <a href="https://anoram.com">anoram</a> and made with</p>
    <br />

    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 196.32 170.02">
      <path
        fill="#42b883"
        d="M120.83 0L98.16 39.26 75.49 0H0l98.16 170.02L196.32 0h-75.49z"
      />
      <path
        fill="#35495e"
        d="M120.83 0L98.16 39.26 75.49 0H39.26l58.9 102.01L157.06 0h-36.23z"
      />
    </svg>
  </footer>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      feed: [],
    };
  },
  async mounted() {
    const response = await fetch("https://api.gemini.com/v1/pricefeed");
    const data = await response.json();

    data.map((c) => {
      if (c.pair.indexOf("USD") !== -1) {
        let tmp = {};
        tmp["coin"] = c.pair.replace("USD", "");
        tmp["price"] = "$ " + c.price;
        this.feed.push(tmp);
      }
    });
  },
};
</script>
