# knowledgebase — ouritres

Knowledge base centralisée. Consommée via git submodule monté à `knowledge-base/`
dans les repos consommateurs. Le skill `maxime-kb` lit `knowledge-base/index.md`
puis charge uniquement les fiches pertinentes depuis `knowledge-base/active/`.

## Structure

```
index.md          ← index léger (seul fichier chargé systématiquement)
active/           ← fiches actives, chargées à la demande par thème
archived/         ← fiches obsolètes, jamais chargées sauf demande explicite
```

## Format de fiche (obligatoire)

```markdown
---
Dernière validation: YYYY-MM-DD
Source: [repo / PR / discussion]
Statut: active | suspecte | obsolète | archivée
Portée: global | <thème> | <repo>
---
# Titre de la fiche
...
```

## Conventions

- Nommage : `active/<thème>/<slug-kebab-case>.md`
- Une fiche = un sujet précis. Pas de fourre-tout.
- Statut `suspecte` si la fiche n'a pas été revalidée depuis 90 jours.
- Archiver (déplacer dans `archived/`) plutôt que supprimer.
- Mettre à jour `index.md` à chaque ajout ou archivage.

## Ajout comme submodule dans un repo consommateur

```bash
git submodule add <url-du-repo> knowledge-base
git submodule update --init --recursive
```
