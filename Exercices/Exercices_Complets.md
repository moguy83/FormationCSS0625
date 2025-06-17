# Pack d’exercices — Formation CSS Initiation (2 jours)

---

## Module 1 — Introduction au CSS

### Exercice 1.1 — Premiers styles CSS

* Créer un fichier `index.html` contenant un titre principal (`h1`) et un paragraphe (`p`).
* Ajouter du CSS inline sur le `h1` pour le mettre en bleu.
* Ajouter du CSS interne dans le fichier HTML pour mettre le paragraphe en rouge.
* Créer un fichier externe `style.css` pour donner une couleur de fond grise au `body`.

---

## Module 2 — Styliser le texte

### Exercice 2.1 — Article stylisé

* Créer un fichier HTML contenant :

  * Un `h1`, un `h2` et deux paragraphes.
* Appliquer les styles suivants :

  * `h1` : rouge, centré, police Verdana.
  * `h2` : bleu foncé, italique, taille 28px.
  * Paragraphes : texte justifié, couleur gris foncé, taille relative `1.2em`.
  * Souligner le premier paragraphe, barrer le deuxième.

---

## Module 3 — Styliser les boîtes

### Exercice 3.1 — Carte de profil

* Créer une fiche de profil avec :

  * Un conteneur centré (largeur 300px).
  * Couleur de fond claire, bordure avec coins arrondis, ombre légère.
  * Deux paragraphes différents (couleur, style italique, gras).
  * Utiliser `box-sizing: border-box`.
  * Expérimenter le `padding` et les `margin`.

---

## Module 4 — Autres éléments à styliser

### Exercice 4.1 — Annuaire

* Créer une page contenant :

  * Une liste non ordonnée avec 3 noms, chaque nom étant un lien.
  * Styliser les liens avec les pseudo-classes : couleur au survol, visited, active.
  * Un tableau de 3 colonnes et 3 lignes listant les noms, fonctions et villes.
  * Appliquer un zébrage sur les lignes du tableau (`nth-child`).
  * Fusionner les bordures avec `border-collapse`.

---

## Module 5 — La mise en page

### Exercice 5.1 — Maquette simple float + position

* Créer une page avec :

  * Un `header` fixe en haut (utiliser `position: sticky` ou `fixed`).
  * Un menu latéral gauche utilisant `float` (200px de large).
  * Un contenu principal prenant le reste de la largeur.
  * Centrer le contenu avec `margin-left`.
  * Gérer le débordement des floats (clearfix).

---

## Module 6 — Mise en page avancée

### Exercice 6.1 — Mini site responsive complet

* Objectif : construire une page vitrine responsive.
* Structure à réaliser :

  * Un header (titre du site).
  * Un menu de navigation.
  * Un contenu principal.
  * Un footer.
* Sur desktop (> 600px de large) : utiliser `display: grid` pour créer 2 colonnes : menu (200px) et contenu.
* Sur mobile (≤ 600px) : menu au-dessus du contenu.
* Ajouter un bouton avec effet de survol et transition.
* Utiliser au moins une petite animation `@keyframes` sur un élément.

---
