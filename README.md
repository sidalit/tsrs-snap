<div align="center">

# tsrs

**TypeScript compiler and language server written in Rust**

[![tsrs](https://snapcraft.io/tsrs/badge.svg)](https://snapcraft.io/tsrs)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [tsrs](https://github.com/oxc-project/tsrs), a Rust implementation of the TypeScript compiler and language server.

</div>

---

## Getting Started

<a href="https://snapcraft.io/tsrs"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install tsrs
cd ~/project/my-project
tsrs --noEmit
```

Use `tsrs -p tsconfig.json` to emit JavaScript, or add `--watch` for continuous builds. Install your project's dependencies with its usual package manager first.

## Configure

Use your project's `tsconfig.json`; there are no `snap set` options. See the [CLI documentation](https://github.com/oxc-project/tsrs/blob/main/docs/USAGE.md) for compiler settings.

Editors that accept a custom language-server command can use `/snap/bin/tsrs --lsp --stdio`.

For projects on removable storage:

```bash
sudo snap connect tsrs:removable-media
```

## Limitations

- Projects and dependency symlinks must stay within non-hidden home directories or connected removable storage.
- External content mappers cannot rely on host-installed tools. Node.js and package managers are not bundled; the npm SDK and browser WebAssembly package remain separate upstream distributions.
- tsrs currently targets TypeScript 7.1 beta and has [upstream compatibility gaps](https://github.com/oxc-project/tsrs/blob/main/docs/DEFAULTS.md), including `--init` and automatic type acquisition.

## Build

```bash
git clone https://github.com/sidalit/tsrs-snap.git
cd tsrs-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/tsrs-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/oxc-project/tsrs/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/tsrs-snap/blob/main/LICENSE).
