# Modifications

This is a **modified version** of the ONLYOFFICE editors (`sdkjs` and
`web-apps`), originally developed by **Ascensio System SIA**
(<https://github.com/ONLYOFFICE>). It is based on ONLYOFFICE **9.4.0**
(`sdkjs` and `web-apps` tag `v9.4.0.131`).

The code carries ONLYOFFICE's copyright and licence notices, which must be
kept: GNU AGPL v3 with the additional terms in `sdkjs/LICENSE` and
`web-apps/LICENSE`. ONLYOFFICE is a trademark of Ascensio System SIA; this
version is not affiliated with or endorsed by it.

## Changes by CryptPad (2023-02-22 – 2026-05-15)

From [cryptpad/onlyoffice-editor](https://github.com/cryptpad/onlyoffice-editor),
to run the editors entirely in the browser, with no ONLYOFFICE server:

- collaboration, saving, image uploads and user colours are handed to the
  host application (`window.parent.APP`) instead of the document server;
- duplicate object IDs, which corrupt documents, are detected and reported;
- CryptPad's presentation themes and fonts; editor API wrapper
  (`onlyoffice-editor/`); build (`Makefile`, `Dockerfile`).

Changed code is marked with `CryptPad` / `CRYPTPAD XXX` comments; the full
history is in this repository.

## Changes by Kutup

- **2026-09-27:** fork notice (`KUTUP.md`); the Docker build pins its tools
  (pnpm, Node) and installs make, bzip2 and python3.
- **2026-09-27:** updated from ONLYOFFICE 9.3.0.140 to 9.4.0 (`git subtree
  pull`), carrying CryptPad's changes across; `sdkjs` built with 9.4's
  `build/build.py` instead of Grunt (`sdkjs/Makefile`); the duplicate-ID
  detector's `Proxy` returns from its `set` trap
  (`sdkjs/common/TableId.js`), which 9.4's strict-mode build requires.

- **2026-09-28:** the PDF editor (`web-apps/apps/pdfeditor`) is built and
  shipped (`sdkjs/Makefile`), with CryptPad's client-only patches that the
  other editors already had: no server-version check, no licence checks, no
  feature-suggestion or support links
  (`web-apps/apps/pdfeditor/main/app/controller/Main.js`, `view/FileMenu.js`,
  `view/LeftMenu.js`).

Every change is a commit on the `kutup` branch.
