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
