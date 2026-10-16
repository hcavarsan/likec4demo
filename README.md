# LikeC4 Demo

Architecture-as-code demo built with [LikeC4](https://likec4.dev), based on the official
[likec4/template](https://github.com/likec4/template).

**Live site:** https://hcavarsan.github.io/likec4demo/

## What's inside

| Path | Shows |
| --- | --- |
| [`src/_spec.c4`](./src/_spec.c4) | Element kinds, tags, relationship kinds, notation, icons |
| [`src/model.c4`](./src/model.c4) | Model hierarchy, relationships, metadata, links, `navigateTo` |
| [`src/model.views.c4`](./src/model.views.c4) | Scoped element views, `include`/`exclude`, `with {}`, `style` rules |
| [`src/deployment/`](./src/deployment/) | Deployment nodes, named instances, deployment views |
| [`src/use-cases/`](./src/use-cases/) | Dynamic views: notes, `parallel`, and a `variant sequence` diagram with `opt`, `loop`, `alt`/`when`/`else`, `try`/`catch`/`finally` |
| [`src/views.showcase.c4`](./src/views.showcase.c4) | `global` style/predicate groups, `extends`, view groups, tag/kind filters, `rank`, `routing ortho` |
| [`test/validate-model.spec.ts`](./test/validate-model.spec.ts) | Model rules checked with Vitest |
| [`likec4.config.ts`](./likec4.config.ts) | Project config with a custom generator |

## Local development

Requires [Bun](https://bun.sh) (or Node.js 20+ with npm).

```bash
bun install
bun run dev            # live preview
bun run validate       # DSL syntax + semantics
bun run test           # model rules
bun run build -o dist  # static site
```

Install the [LikeC4 VS Code extension](https://marketplace.visualstudio.com/items?itemName=likec4.likec4-vscode) for highlighting, completions and preview.

## Deployment

[`.github/workflows/pages.yml`](./.github/workflows/pages.yml) runs on every push to `main` (or manually):

1. **validate**: `likec4 validate` and the Vitest model rules
2. **build-pages**: `likec4 build --base <pages base path>`
3. **deploy-pages**: publishes `dist/` to GitHub Pages

Repository setting required once: **Settings → Pages → Source: GitHub Actions**.

## License

[MIT](LICENSE)
