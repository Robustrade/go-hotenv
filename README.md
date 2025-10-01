# go-modules

Internal repository for reusable Go modules.

This repo hosts multiple small, independent Go packages maintained internally for shared use across projects at **Kulu**.  
Each subfolder (e.g., `hotenv/`) is its own Go module with its own `go.mod`.

---

## Structure

```
go-modules/
├── hotenv/          # Environment auto-reload utility
├── another-module/  # (future modules go here)
└── README.md
```

Each submodule can be versioned and imported independently:

```bash
go get github.com/kulu/go-modules/<module-name>@<tag>
```

Example:
```bash
go get github.com/kulu/go-modules/hotenv@v1.0.0
```

---

## Releasing a new version

1. Commit changes in the module folder.
2. Create and push a **tag** with the module path prefix:

```bash
git tag hotenv/v0.1.0
git push origin hotenv/v0.1.0
```

3. Consumers can then update with:

```bash
go get -u github.com/kulu/go-modules/hotenv@hotenv/v1.0.0
```
---

## Current modules

| Module | Description | Version |
|---------|--------------|----------|
| [hotenv](./hotenv) | Read `.env` files with real-time reload support | v1.0.0 |

---

**Maintainers:** Internal SRE team  
