# Svelte speed test
I've run some adapters locally, and measure their speed with [oha](https://github.com/hatoo/oha). Full result in txt files.

![Graph: Node, Deno and Bun](https://user-images.githubusercontent.com/37719998/201757093-0edfa8c2-3cde-4ba8-a329-8917c4f2a2b7.svg)


|Data|Node|Deno|Bun|
|-|-|-|-|
|Req/s|9023.8510|3248.5757|6143.0011|
|Total,req|100k|100k|10k[^1]|
|Total,s|11.0817|30.7827|1.6279|
|Slowest,s|0.0233|0.0827|0.0255|
|Fastes,s|0.0029|0.0090|0.0006|
|Average,s|0.0055|0.0154|0.0081|

[^1]: Bun adapter breaks after 10k

## Versions used
| Package | Version | [@sveltejs/kit](https://github.com/sveltejs/kit) version |
|-|-|-|
|[@sveltejs/adapter-node](https://github.com/sveltejs/kit/tree/master/packages/adapter-node) | 1.0.0-next.100 | 1.0.0-next.406 |
|[svelte-adapter-deno](https://github.com/pluvial/svelte-adapter-deno) | 0.8.1 | 1.0.0-next.406 |
|[svelte-adapter-bun](https://github.com/gornostay25/svelte-adapter-bun) | 0.3.0 | 1.0.0-next.304 |



## Run locally

```
git clone https://github.com/jonaaronru/svelte-speed-test.git
cd ./svelte-speed-test
```

## Run Deno

```
cd ./svelte-kit-deno/
yarn
yarn build
deno run --allow-env --allow-read --allow-net build/index.js
```

## Run Bun

```
cd ./svelte-kit-bun/
yarn
yarn build
cd ./build
bun run start
```

## Run Node

```
cd ./svelte-kit-node/
yarn yarn build
node build/index.js
```
