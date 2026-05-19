# ranksource-content

Contenu éditorial du site **ranksource.com** : blog, livres blancs, médias.

Repo séparé du code applicatif. Le site `landingv2/` (sur `EpickOneAgency/ranksource`) consomme ce contenu au build via `scripts/sync-content.mjs`.

## Structure

```
ranksource-content/
├── blog/
│   ├── fr/             Articles en français (source canonique)
│   ├── en/             Versions anglaises (générées via Sonnet ou manuelles)
│   ├── es/             Espagnol
│   ├── de/             Allemand
│   └── it/             Italien
├── whitepaper/         Livres blancs (.md + lien PDF)
├── media/              Images uploadées via Sveltia CMS
└── .github/workflows/
    └── trigger-coolify.yml   Déclenche un rebuild Coolify à chaque push
```

## Flux d'édition

1. Aller sur **https://www.ranksource.com/admin/** (Sveltia CMS, login GitHub).
2. Créer / éditer un article ou un livre blanc.
3. Cliquer **Publier** → Sveltia commit dans ce repo, branche `main`.
4. GitHub Action `trigger-coolify.yml` POST sur Coolify → rebuild landing.
5. L'article est en ligne ~90 sec plus tard.

## Setup initial (une fois)

1. **Créer le repo** sous ton compte GitHub perso :
   - https://github.com/new
   - Owner : `mdezordo` (ton compte perso)
   - Name : `ranksource-content`
   - Public (recommandé, pas de secret dans le contenu)
   - Pas de README auto-généré, on push le nôtre
2. **Initialiser depuis le bootstrap** :
   ```bash
   cd ~/Documents/ranksource-content   # ou autre dossier de travail
   cp -R /chemin/vers/landingv2/content-repo-bootstrap/. .
   git init
   git add .
   git commit -m "chore: bootstrap content repo"
   git branch -M main
   git remote add origin https://github.com/mdezordo/ranksource-content.git
   git push -u origin main
   ```
3. **Ajouter le secret COOLIFY_API_TOKEN** dans les secrets du repo :
   - https://github.com/mdezordo/ranksource-content/settings/secrets/actions
   - New secret → Name : `COOLIFY_API_TOKEN` · Value : le même token que celui utilisé sur EpickOneAgency/ranksource
4. **C'est tout**. Le workflow `trigger-coolify.yml` fait le reste.

## Schéma frontmatter blog

Voir `landingv2/src/content/config.ts` (Zod schema). Résumé des champs requis :

- `title` (4-120 char)
- `description` (40-220 char)
- `pubDate` (YYYY-MM-DD)
- `author`, `authorRole`, `authorAvatar` (optionnels avec défauts)
- `category` (strategy | product | cases | data | guides | news)
- `tags[]`, `readingTime`, `featured`, `draft`
- `locale` (fr | en | es | de | it)
- `translationKey` (clé partagée entre versions linguistiques)
- `ogImage`, `seoKeywords[]`

Le build valide ce schéma. Une frontmatter incomplète fait planter le build → on remarque tout de suite.

## Image cover convention

- Stockée dans `media/` (Sveltia upload), référencée en frontmatter : `cover: /uploads/mon-image.jpg`
- 16:9 idéalement, 1200×630 pour OG sociaux, max 500 ko (recompresser avant upload)
- Sveltia ne fait pas de compression auto, fais-le avant upload.

## Workflow éditorial

L'admin Sveltia tourne en `publish_mode: editorial_workflow` :

1. **Brouillon** : sauvegardé sur branche `cms/posts/<slug>` (Pull Request draft).
2. **En review** : la PR est ouverte sur ce repo, prête à être relue (tu peux la review depuis l'UI GitHub).
3. **Prêt** : approuvée.
4. **Publier** : merge auto sur `main`, le workflow trigger-coolify déclenche le rebuild.

Tu peux désactiver le editorial_workflow et passer en publish direct si tu trouves ça lourd pour un solo : commenter la ligne `publish_mode:` dans `landingv2/public/admin/config.yml`.
