# Sveltekit + D3 + Netlify

This repo shows a solution when using Sveltkit with D3 on Netlify.
I could run everything locally without problems, but would get this message when deployed on Netlify.

```
500

Must use import to load ES Module: /var/task/node_modules/d3-scale/src/index.js
require() of ES modules is not supported.
require() of /var/task/node_modules/d3-scale/src/index.js from /var/task/.netlify/server/entries/pages/index.svelte.js is an ES module file as it is a .js file whose nearest parent package.json contains "type": "module" which defines all .js files in that package scope as ES modules.
Instead rename index.js to end in .cjs, change the requiring code to use import(), or remove "type": "module" from /var/task/node_modules/d3-scale/package.json.

Error [ERR_REQUIRE_ESM]: Must use import to load ES Module: /var/task/node_modules/d3-scale/src/index.js
require() of ES modules is not supported.
require() of /var/task/node_modules/d3-scale/src/index.js from /var/task/.netlify/server/entries/pages/index.svelte.js is an ES module file as it is a .js file whose nearest parent package.json contains "type": "module" which defines all .js files in that package scope as ES modules.
Instead rename index.js to end in .cjs, change the requiring code to use import(), or remove "type": "module" from /var/task/node_modules/d3-scale/package.json.
```

What helped me, was to set the version of Node to `v16.15.1` in `.node-version` and add the following lines to `netlify.toml`:

```toml
[functions]
  node_bundler = "esbuild"
```

See the deployed version running here: [https://papaya-stroopwafel-14b612.netlify.app/](https://papaya-stroopwafel-14b612.netlify.app/)

More information [here](https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c), [here](https://github.com/sveltejs/kit/issues/5177) and [here](https://github.com/ghostdevv/netlify-sveltekit-esm-only-broke/commit/e9bea7eb2e41cd07f470bdd82119472a65d0109d).
Older information are [here](https://github.com/d3/d3/issues/3469) and [here](https://github.com/d3/d3-scale/releases/tag/v4.0.0).
