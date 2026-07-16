# knowledgebase — ouritres

Knowledge base centralisée. Consommée via git submodule monté à `knowledge-base/`
dans les repos consommateurs. Le skill `maxime-kb` lit `knowledge-base/index.json`
puis charge uniquement les fiches pertinentes depuis `knowledge-base/active/`.

Schéma aligné sur `ma.xi.me` (`.wip/specs/kb-json-schema.md`), conçu pour être
partagé entre l'état local de ma.xi.me et ce repo dès le départ.

## Structure

```
index.json               ← index léger, un objet par fiche sans "content" (seul fichier chargé systématiquement)
active/<theme>/<id>.json ← une fiche = attributs + "content", chargée à la demande par thème
archived/                ← fiches obsolètes, jamais chargées sauf demande explicite
```

## Format de fiche (obligatoire)

Fiche JSON avec attributs courts/contrôlés et un seul champ texte libre (`content`) :

```json
{
  "id": "slug-kebab-case",
  "type": "reference | decision | procedure | pattern | contact | glossary",
  "title": "Titre lisible",
  "theme": "thème court",
  "tags": ["mots-clés", "courts"],
  "scope": "global | maxime | <nom-de-repo>",
  "status": "draft | active | suspect | obsolete | archived",
  "confidence": "fact | hypothesis | opinion",
  "audience": "generic | project | secret",
  "source": "URL / PR / discussion (libre)",
  "validated": "YYYY-MM-DD",
  "created": "YYYY-MM-DD",
  "ttl_days": 90,
  "links": ["autres-ids-liés"],
  "content": "Corps de la fiche, Markdown en texte libre"
}
```

Seuls `title`, `source` et `content` sont exemptés de la contrainte de
concision (texte libre par nature).

## Conventions

- Nommage : `active/<thème>/<id>.json`, `id` = nom de fichier sans extension.
- Une fiche = un sujet précis. Pas de fourre-tout.
- Statut `suspect` si la fiche n'a pas été revalidée dans le délai `ttl_days`.
- Archiver (déplacer dans `archived/`) plutôt que supprimer.
- Mettre à jour `index.json` (sans `content`, plus champ `path`) à chaque
  ajout, archivage ou changement d'attribut.

## Ajout comme submodule dans un repo consommateur

```bash
git submodule add <url-du-repo> knowledge-base
git submodule update --init --recursive
```
