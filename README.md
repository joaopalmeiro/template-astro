# template-astro

Opinionated [Astro](https://astro.build/) template for new projects.

## Getting Started

1. Go to or create the project folder.
2. Get the template files:

```bash
npx giget github:joaopalmeiro/template-astro . --force
```

3. Search for `template-astro` and replace it with the project name. Ignore the template repository URL in the [NOTES.md](NOTES.md) file.
4. Search for `Opinionated Astro template for new projects.`/`Opinionated [Astro](https://astro.build/) template for new projects.` and replace it with the (short) project description.
5. Search for `João Palmeiro` and replace it with the author's name.
6. Search for `joaopalmeiro@proton.me` and replace it with the author's email address.
7. Change the `author.url` field in the `package.json` file to the author's website/social media profile.
8. Install [fnm](https://github.com/Schniz/fnm) (if necessary).
9. Run the first two commands in the [`Development`](#development) section to install [Node.js](https://nodejs.org/en) and the development dependencies.
10. Open the [NOTES.md](NOTES.md) file and install the project-specific dependencies according to the first command in the [`Commands`](NOTES.md#commands) section.
11. Remove `minimal-demo/` from the [.gitignore](.gitignore) file.
12. Delete the [TEMPLATE.md](TEMPLATE.md) file.
13. Delete the [`Getting Started`](#getting-started) section.

## Development

Install [fnm](https://github.com/Schniz/fnm) (if necessary).

```bash
fnm install && fnm use && node --version && npm --version
```

```bash
npm install
```

```bash
npm run dev
```

```bash
npm run lint
```

```bash
npm run format
```

## Deployment

```bash
npm run build
```
