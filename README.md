# photo-editing-hub

One repo collecting 44 open-source photo editing projects: desktop editors,
web/JavaScript editors, image libraries, AI photo tools and mobile SDKs.

Nothing is copied here. The full catalog (grouped, with best picks, licenses
and links) lives in [`photo-editor-repos/SKILL.md`](photo-editor-repos/SKILL.md),
and every project is linked as a **git submodule** under `editors/`, `web/`,
`libs/`, `ai/` and `mobile/`, pinned to a recent upstream commit.

Clone everything:

```bash
git clone --recurse-submodules https://github.com/adityaparthiban200729/photo-editing-hub.git
```

Update all submodules to their pinned commits later:

```bash
git submodule update --init --recursive
```

Each project keeps its own license - check the catalog table before reusing code.
