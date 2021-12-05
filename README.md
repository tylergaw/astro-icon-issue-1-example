An isolated issue using I'm running into trying out [astro-icon](https://github.com/natemoo-re/astro-icon)

Issue: https://github.com/natemoo-re/astro-icon/issues/2

## Steps to reproduce

I've tried this with node `14.6.0` and `16.9.1` with the same results.

Clone this repo

```
git clone git@github.com:tylergaw/astro-icon-issue-1-example.git
cd astro-icon-issue-1-example
```

Install deps

```
yarn
```

Attempt build

```
yarn build
```

or to start

```
yarn start
```

Both building and running the dev server produce the same errors.

Relevant snippets from the errors:

```
[vite] Error when evaluating SSR module /node_modules/svgo/lib/svgo-node.js?v=5f848506:
ReferenceError: require is not defined
  at /node_modules/svgo/lib/svgo-node.js?v=5f848506:3:12
...
```

```
[vite] Error when evaluating SSR module /node_modules/astro-icon/lib/utils.ts:
ReferenceError: require is not defined
  at /node_modules/svgo/lib/svgo-node.js?v=5f848506:1:12
...
```

```
[vite] Error when evaluating SSR module /node_modules/astro-icon/index.ts?v=5f848506:
TypeError: Line must be greater than or equal to 1, got -1
  at BasicSourceMapConsumer.SourceMapConsumer_findMapping [as _findMapping]
...
```

There's more to all the errors, but these seem like the standout bits.
