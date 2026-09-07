# KROMA

A self-hosted media stack that plays your files as they are: one Rust server,
thin clients for the TV, the phone, the desktop and the browser, and modules
for everything past playback and catalog.

- **[maxscharwath/kroma](https://github.com/maxscharwath/kroma)**, the server, the clients and the first-party modules.
- **[`@kromatv/sdk`](https://www.npmjs.com/package/@kromatv/sdk)**, everything a module needs, in one package: `bunx @kromatv/sdk create`.
- **[kroma.tv](https://kroma.tv)**, the site; **[modules.kroma.tv](https://modules.kroma.tv)**, the module catalog.

## Write a module

```bash
bunx @kromatv/sdk create            # a few questions, then a project ready to run
cd tv.acme.notes
bunx kroma login http://localhost:4040
bunx kroma dev                      # build, install on your server, rebuild on every save
bunx kroma build                    # dist/modules/tv.acme.notes.kmod
```

A module is a small Rust sidecar the server spawns and a React page the
KROMA app renders with its own design system. The page's runtime is the
app's, injected when the module loads, so the SDK ships types only; the
Rust crates a sidecar links come inside the same package. The authoring
guide is [`modules/README.md`](https://github.com/maxscharwath/kroma/blob/main/modules/README.md).
