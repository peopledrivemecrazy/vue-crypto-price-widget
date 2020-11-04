# Crypto price widget made with Vue

A Vue implementation of my earlier [Svelte version](https://github.com/peopledrivemecrazy/svelte-crypto-price-widget). Both deployments use the same API.

## Vue vs Svelte


| Metrics              | Vue                                                     | Svelte                            |
|----------------------|---------------------------------------------------------|-----------------------------------|
| Website              | [https://vue-widget.anoram.com/](https://vue-widget.anoram.com/)                                                 | [https://widget.anoram.com](https://widget.anoram.com)                               |
| Bundle Size in KB    | 17.5                                                    | 4.5                               |
| Developer experience | not easy to use .includes()  alternative way .indexOf() | no issue using javascript methods |
| Bundler              | vite+webpack                                            | rollup                            |



## Local development and testing

Clone the repo,

`yarn` and then `yarn-dev` to check with bundle size `yarn build`.