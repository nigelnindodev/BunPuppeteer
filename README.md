# Bun Puppeteer

To install dependencies:

```bash
bun install
```

To run:

```bash
bun run index.ts
```

This project was created using `bun init` in bun v1.0.2. [Bun](https://bun.sh) is a fast all-in-one JavaScript runtime.

## Motivation for this repo

Bun is [too impressive](https://medium.com/deno-the-complete-reference/node-js-vs-deno-vs-bun-native-http-hello-world-server-benchmarking-f48edd514513) to ignore at this point:

- See linked benchmark above
- First class support for TypeScript

Been working on a private project using Puppeteer and Node 18. Using Puppeteer for:

- Web scrapping and collecting thousands of data points per minute.
- Finding dynamic elements on a webpage and performing automated actions.

The major pain with Node and Puppeteer has been *performance*.

This is around CPU usage, when opening a page as described above with thousands of DOM changes per minute.

This repo will document what I can share publicly with transitioning Puppeteer from Node to Bun.

### Know issues (with Puppeteer)

- Puppeteer should work out of the box according to [to this tweet](https://twitter.com/jarredsumner/status/1664892235966734337), but doesn't. Starting point GitHub issue for investigating this can be found [here](https://github.com/oven-sh/bun/issues/4705).

### Know issues (related private to project, but still worth mentioning)

- Potential issues with `timers/promises` library from Node compatibility. Mentioned in this [Github Issue](https://github.com/oven-sh/bun/issues/5021).
  - Blocker as `timers/promises` allows for simplified non-blocking operations, without which reasonable performance given already high CPU usage would be impossible.
