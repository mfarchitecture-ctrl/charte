# Charte graphique

Socle visuel commun des applications (KELZONE, ARCHIPILOT, ...). Un fichier CSS, des polices,
une page de démonstration.

## Contenu

- `charte.css` : variables (thèmes clair/sombre), base, boutons, champs, cartes, badges, tableau,
  modale, barre latérale.
- `polices/` : Outfit (auto-hébergée, licence incluse). Pas de Google Fonts.
- `demo.html` : tous les composants, avec bouton de thème. À ouvrir pour juger un changement.

## Règle maîtresse

**Le noir est l'interface ; la couleur est une donnée ou une erreur.** Jamais de couleur
d'accent décorative. Les couleurs (`--couleur-erreur`, `-succes`, `-alerte`, `-info`) ne servent
qu'à exprimer un état (statut, priorité, retard).

## Utiliser la charte dans une appli

1. Copier `charte.css` et le dossier `polices/` tels quels à côté du HTML de l'appli.
2. `<link rel="stylesheet" href="charte.css">` **avant** le CSS propre à l'appli.
3. Le CSS de l'appli n'utilise que les variables (`var(--surface)`, `var(--ligne)`, ...), jamais
   de couleur en dur. Il ne redéfinit pas les composants de la charte.
4. Thème manuel : poser `data-theme="light"` ou `"dark"` sur `<html>` (sinon, suit le système).

## Modifier la charte

On ne change la charte qu'ici. Vérifier le rendu dans `demo.html` (clair et sombre), incrémenter
la version en tête de `charte.css`, committer, puis recopier `charte.css` dans chaque appli.
Quand un composant propre à une appli se retrouve dans une deuxième, il monte dans la charte.
