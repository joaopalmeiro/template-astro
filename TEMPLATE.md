# Template Notes

- https://github.com/withastro/astro/tree/main/examples/minimal
- https://github.com/withastro/astro/releases
- https://github.com/eslint/config-inspector/releases
- https://ota-meshi.github.io/eslint-plugin-astro/user-guide/
  - https://ota-meshi.github.io/eslint-plugin-astro/rules/
  - https://github.com/ota-meshi/eslint-plugin-astro/blob/v0.34.0/src/configs/flat/recommended.ts
- https://docs.astro.build/en/editor-setup/#prettier
  - https://github.com/withastro/prettier-plugin-astro
  - https://prettier.io/docs/en/cli.html
  - https://github.com/withastro/prettier-plugin-astro/tree/v0.13.0?tab=readme-ov-file#recommended-configuration
  - https://github.com/withastro/astro/blob/astro%404.6.0/prettier.config.js
  - https://github.com/withastro/prettier-plugin-astro/blob/v0.13.0/.prettierrc.json
  - https://github.com/withastro/starlight/blob/%40astrojs/starlight%400.21.5/.prettierrc
  - https://prettier.io/docs/en/configuration#basic-configuration
  - https://prettier.io/docs/en/configuration#sharing-configurations
  - https://github.com/will-stone/prettier-config/blob/v7.0.3/package.json#L20: `"dependencies": { "prettier-plugin-packagejson": "^2.4.6" }`
  - https://github.com/shun-shobon/configs/blob/prettier-config-v0.3.1/packages/prettier-config/package.json#L37: `"dependencies": { "local-pkg": "^0.5.0", "prettier-plugin-astro": "^0.13.0", "prettier-plugin-jsdoc": "^1.3.0", "prettier-plugin-pkg": "^0.18.1", "prettier-plugin-tailwindcss": "^0.5.11" }`
  - https://github.com/prettier/prettier/issues/12701: "When using pnpm, one has to use require.resolve or import.meta.resolve in the .prettierrc.js configuration to resolve plugins."
- https://docs.astro.build/en/concepts/why-astro/#easy-to-use:
  - "The `.astro` UI language is a superset of HTML: any valid HTML is valid Astro templating syntax!"
- https://docs.astro.build/en/concepts/islands/:
  - Islands architecture
  - "(...) most JavaScript-based web frameworks hydrate & render an entire website as one large JavaScript application (also known as a single-page application, or SPA). SPAs provide simplicity and power but suffer from page-load performance problems due to heavy client-side JavaScript usage."
  - "In Astro, an "island" refers to any interactive UI component on the page. Think of an island as an interactive widget floating in a sea of otherwise static, lightweight, server-rendered HTML."
  - "An island always runs in isolation from other islands on the page, and multiple islands can exist on a page. Islands can still share state and communicate with each other, even though they run in different component contexts."
  - "Turning any static UI component into an interactive island requires only a `client:*` directive."
- https://esbench.com/
- https://docs.astro.build/en/basics/project-structure/
- https://docs.astro.build/en/reference/configuration-reference/
- https://docs.astro.build/en/basics/astro-components/:
  - "The most important thing to know about Astro components is that they don't render on the client. They render to HTML either at build-time or on-demand using server-side rendering (SSR). You can include JavaScript code inside of your component frontmatter, and all of it will be stripped from the final page sent to your users' browsers."
  - "You can safely write code here that is expensive or sensitive (like a call to your private database) (...)"
  - `const data = await fetch('SOME_SECRET_API_URL/users').then(r => r.json());`
  - "Mix HTML with JavaScript expressions, similar to JSX": `<ul>{myFavoritePokemon.map((data) => <li>{data.name}</li>)}</ul>`
  - Component props: `Astro.props` + `interface Props`
  - https://docs.astro.build/en/basics/astro-components/#transferring-slots
- Data fetching:
  - https://csvbase.com/
  - https://docs.astro.build/en/guides/backend/turso/
  - https://docs.astro.build/en/guides/data-fetching/
- https://docs.astro.build/en/guides/fonts/
- https://docs.astro.build/en/guides/deploy/
- Tailwind CSS:
  - https://docs.astro.build/en/guides/styling/#tailwind
  - https://docs.astro.build/en/guides/integrations-guide/tailwind/
  - https://github.com/withastro/astro/tree/main/packages/integrations/tailwind/
- https://docs.astro.build/en/reference/api-reference/#astrogenerator
- https://docs.astro.build/en/install/manual/#6-add-typescript-support:
  - "(...) create `src/env.d.ts` to let TypeScript know about ambient types available in an Astro project"
- https://docs.astro.build/en/guides/upgrade-to/v3/#moved-astro-check-now-requires-an-external-package: `@astrojs/check`
- https://github.com/withastro/astro/blob/main/packages/astro/tsconfigs/strict.json
- https://github.com/withastro/astro/blob/main/packages/astro/tsconfigs/strictest.json
- https://docs.astro.build/en/guides/integrations-guide/sitemap/
- https://biomejs.dev/internals/language-support/
- https://eslint.org/docs/latest/use/configure/configuration-files#configuration-file: `eslint.config.mjs`
- https://github.com/es-tooling/eslint-plugin-depend/blob/main/src/replacements.ts
- https://openjsf.org/blog/node-js-20-now-available: "`import.meta.resolve()` makes it easier to write scripts which are not sensitive to their exact location, or to the web application's module setup."

## Commands

```bash
npm create astro@latest -- --template minimal
```

```bash
npm create astro@latest -- minimal-demo --template minimal --no-install --no-git --typescript strictest
```

## Snippets

### `.prettierrc.mjs` file

```js
// @ts-check

/** @type {import("prettier").Config} */
export default {
  printWidth: 100,
  semi: true,
  singleQuote: true,
  tabWidth: 2,
  trailingComma: 'es5',
  plugins: ['prettier-plugin-astro'],
  overrides: [
    {
      files: '*.astro',
      options: {
        parser: 'astro',
      },
    },
  ],
};
```
