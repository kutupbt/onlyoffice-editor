# Kutup's fork of the OnlyOffice browser editor

This is [Kutup](https://github.com/kutupbt/kutup)'s fork of CryptPad's
[`onlyoffice-editor`](https://github.com/cryptpad/onlyoffice-editor): the
OnlyOffice `sdkjs` and `web-apps` source (git subtrees of
[ONLYOFFICE/sdkjs](https://github.com/ONLYOFFICE/sdkjs) and
[ONLYOFFICE/web-apps](https://github.com/ONLYOFFICE/web-apps)) with
CryptPad's changes, which let the editor run entirely in the browser. Kutup
opens documents with it client-side; the server never sees their content.

- **Branch `kutup`** is what Kutup ships. It starts at CryptPad's
  `v9.2.0.119+5` (`4fcd833d`); Kutup's own changes go on it.
- **`main`** follows CryptPad's `main`, for pulling their updates.
- **Releases** are tagged `kutup-<CryptPad version>.<n>` (for example
  `kutup-v9.2.0.119+5.1`), so CryptPad's `v*` release workflow does not run
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
