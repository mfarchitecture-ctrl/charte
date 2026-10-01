# CHARTE — mémoire de travail

Socle graphique partagé par les applis de l'utilisateur (KELZONE, ARCHIPILOT, puis 3 autres).
Détail : `README.md`.

## Règles
- Noir = interface ; couleur = donnée ou erreur uniquement. Pas d'accent décoratif.
- Aucune dépendance externe (polices auto-hébergées, pas de Google Fonts).
- Toute couleur passe par une variable ; pas de valeur en dur dans les composants.
- Toute modification se vérifie dans `demo.html`, en clair ET en sombre, puis s'accompagne
  d'une nouvelle version en tête de `charte.css`.
- Référence d'origine : les variables de KELZONE (`C:\Users\laxim\KELZONE\index.html`, bloc `:root`).
- Une question est une question : ne rien modifier sans demande.

## Git
Dépôt privé GitHub `charte`. Branches `preprod` (travail) et `main` (référence stable).
Pas de commit direct sur `main`, pas de `push --force`. Les identifiants GitHub sont gérés par
l'utilisateur.

## État d'avancement (1er octobre 2026)
**Propagation automatique de la charte vers les applis : en place et testée.**
- `.github/workflows/propagation.yml` + `apps.json` : à chaque push sur `main` qui touche `charte.css`,
  `polices/` ou `apps.json`, un robot ouvre une PR « Charte vX.Y.Z » dans chaque appli listée
  (aujourd'hui `kelzone` et `archipilot`). Lancement manuel : Actions → Propager la charte → Run workflow.
- Secret `CHARTE_SYNC_TOKEN` créé dans le dépôt (jeton fine-grained, accès kelzone + archipilot,
  Contents + Pull requests en écriture). S'il expire ou est perdu : le régénérer et remplacer le secret.
- Première propagation faite : PR « Charte v1.0.0 » ouverte (n° 1) dans kelzone et archipilot. **Non mergées.**
- Décision : travail direct sur `main` pour l'instant ; `preprod` à créer plus tard.

**À faire à la reprise**
1. archipilot : le contrôle Cloudflare « Workers Builds » échoue en 0 s sur la PR (probablement sans lien
   avec la charte). Voir les logs Cloudflare, et si `main` d'archipilot est aussi rouge.
2. Dossier de destination : la PR a copié `charte.css` et `polices/` à la **racine** de chaque appli.
   archipilot range ses styles dans `public/styles/` : régler `"dossier"` dans `apps.json` (idem kelzone,
   structure à vérifier), puis relancer la propagation et fermer les PR à la racine.
3. Brancher `<link rel="stylesheet" href="charte.css">` avant le CSS de chaque appli (chantier à part).
4. Ensuite : premières modifications de la charte elle-même (nouvelle version en tête de `charte.css`).
