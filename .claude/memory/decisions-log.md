# Decisions Log

## 2026-06-16 — Init knowledgebase

**Décision** : Initialiser le repo `knowledgebase` comme KB centralisée ouritres.

**Approche retenue** : git submodule monté à `knowledge-base/` dans les repos
consommateurs. Aligné avec le chemin attendu par le skill `maxime-kb`
(`knowledge-base/index.md`).

**Structure** :
- `index.md` — index léger, chargé systématiquement
- `active/<thème>/` — fiches actives
- `archived/` — fiches archivées

**Alternatives écartées** : package npm/nuget (overkill), symlink (fragile Windows),
KB embarquée dans chaque repo (duplication).

**Approuvé par** : Philippe — 2026-06-16
