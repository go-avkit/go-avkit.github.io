# go-avkit.github.io

The landing page for the [go-avkit](https://github.com/go-avkit) organisation.
Live at <https://go-avkit.github.io/>.

A single-page Hugo site. The prose, the pills and the repository cards all live
in `hugo.toml` under `[params]`; `layouts/index.html` is shared across the
fleet's org sites and should not need editing to add a repository — add a
`[[params.repos]]` block instead.

| Path | Purpose |
| --- | --- |
| `hugo.toml` | site config, prose and the repository cards |
| `layouts/index.html` | the whole page: markup, CSS, theme toggle |
| `static/img/logo.svg` | the 88px organisation mark |

Theme: light, dark and system, defaulting to system, applied before first paint.

```sh
hugo server -D      # local preview on :1313
hugo --minify       # what CI builds
```

BSD-3-Clause.

## The design is not here

It comes from the shared Hugo module
[`go-fleettools/landingkit`](https://github.com/go-fleettools/landingkit),
pinned in `go.mod` (Renovate bumps it); `kit.go` keeps `go mod tidy` from
deleting that requirement. `[params.brand]` in `hugo.toml` is read from the logo by
`landingkit brand`. A file under `layouts/partials/` with the name of one of the
kit's would silently override it.
