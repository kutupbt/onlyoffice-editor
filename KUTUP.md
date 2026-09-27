# Kutup's fork of the OnlyOffice browser editor

This is [Kutup](https://github.com/kutupbt/kutup)'s fork of CryptPad's
[`onlyoffice-editor`](https://github.com/cryptpad/onlyoffice-editor): the
OnlyOffice `sdkjs` and `web-apps` source (git subtrees of
[ONLYOFFICE/sdkjs](https://github.com/ONLYOFFICE/sdkjs) and
[ONLYOFFICE/web-apps](https://github.com/ONLYOFFICE/web-apps)) with
CryptPad's changes, which let the editor run entirely in the browser. Kutup
opens documents with it client-side; the server never sees their content.

- **Branch `kutup`** is what Kutup ships: **ONLYOFFICE 9.4.0**
  (`sdkjs` and `web-apps` at `v9.4.0.131`, pulled with `git subtree pull`)
  with CryptPad's changes carried over from their `v9.3.0.140+2`; Kutup's own
  changes go on it. From 9.4, `sdkjs` is built by `build/build.py` (plain
  concatenation, strict mode) instead of Grunt and Closure. CryptPad's later `v9.3.2+` builds are based on Euro-Office, a
  fork of OnlyOffice, and are not merged: Kutup follows ONLYOFFICE.
- **`main`** follows CryptPad's `main`, for pulling their updates.
- **Releases** are tagged `kutup-<version>.<n>` (for example
  `kutup-v9.4.0.131.1`), so CryptPad's `v*` release workflow does not run
  on them. Each release notes the exact commit it was built from.

## Build

```sh
make build        # Docker; writes output/onlyoffice-editor.zip and its .sha512
make test
```

Kutup's packaging ([kutup-office-assets](https://github.com/kutupbt/kutup-office-assets))
pins the release by URL and SHA-512.

## Updating

From CryptPad: merge or rebase `kutup` onto a newer CryptPad tag. From
OnlyOffice directly: `git subtree pull --prefix sdkjs|web-apps` as in
[README.md](README.md). Then build, test Kutup's office editor in a browser,
and release.

## Licence

AGPL-3.0, with the ONLYOFFICE Section 7 additional terms in the source files
(keep the original product logo and legal notices; no trademark rights).
ONLYOFFICE is a trademark of its owner; this fork is not affiliated with or
endorsed by ONLYOFFICE or CryptPad.
