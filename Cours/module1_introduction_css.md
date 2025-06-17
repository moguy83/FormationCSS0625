
# Module 1 — Introduction au CSS

## Objectifs pédagogiques

- Comprendre l’utilité et le rôle du CSS.
- Connaître les différentes façons d’intégrer du CSS dans une page HTML.
- Comprendre la séparation contenu / design.
- Savoir écrire des commentaires en CSS.

---

## 1️⃣ Contextualisation

CSS (Cascading Style Sheets) = langage de description de présentation pour le HTML.

- Sépare le contenu (HTML) de la présentation (CSS).
- Permet de modifier l'apparence des éléments HTML : couleur, taille, position, etc.

### Pourquoi utiliser le CSS ?

- Meilleure lisibilité et maintenabilité du code.
- Réutilisabilité des styles.
- Meilleure collaboration entre développeurs et designers.
- Responsivité et adaptation sur tous les supports (PC, mobile, tablette…).

---

## 2️⃣ Intégrer du CSS

### a) CSS Inline (directement sur l'élément HTML)

```html
<p style="color: red; font-weight: bold;">Bonjour le monde</p>
```

- Avantage : rapide pour de petites modifications ponctuelles.
- Inconvénient : difficile à maintenir sur le long terme.

### b) CSS Interne (dans le fichier HTML via une balise <style>)

```html
<head>
  <style>
    p {
      color: red;
      font-weight: bold;
    }
  </style>
</head>
```

- Avantage : centralisé mais limité à une seule page.
- Inconvénient : pas optimal pour les projets multi-pages.

### c) CSS Externe (fichier .css lié)

Dans le fichier HTML :

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

Dans le fichier styles.css :

```css
p {
  color: red;
  font-weight: bold;
}
```

- Avantage : séparé du HTML, réutilisable, facile à maintenir.

---

## 3️⃣ Séparation contenu / design

Principe fondamental du web moderne :

- Le HTML décrit la structure et le contenu.
- Le CSS décrit la présentation.

### Exemple

HTML :

```html
<p>Bienvenue sur mon site</p>
```

CSS :

```css
p {
  color: blue;
  font-size: 24px;
  font-family: Arial, sans-serif;
}
```

---

## 4️⃣ Les commentaires

En CSS, les commentaires sont écrits ainsi :

```css
/* Ceci est un commentaire */
p {
  color: red; /* Commentaire à la fin de la ligne */
}
```

- Ils ne sont pas interprétés par le navigateur.

---

## 🎯 Exercice 1 — Mise en pratique

Objectif : créer ta première page HTML et y intégrer du CSS sous les 3 formes.

### Instructions

1. Crée un fichier index.html :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Mon premier CSS</title>
</head>
<body>
  <h1>Bienvenue</h1>
  <p>Ceci est un paragraphe stylisé.</p>
</body>
</html>
```

2. Ajoute du CSS :

- Inline : mets le h1 en bleu.
- Interne : mets le p en rouge.
- Externe : crée un fichier style.css qui met le body en gris clair.

---

## ✅ Corrigé de l’exercice 1

### Inline :

```html
<h1 style="color: blue;">Bienvenue</h1>
```

### Interne :

```html
<head>
  <style>
    p {
      color: red;
    }
  </style>
</head>
```

### Externe (fichier style.css) :

```css
body {
  background-color: #f0f0f0;
}
```

Et ne pas oublier dans le HTML principal :

```html
<link rel="stylesheet" href="style.css">
```

---

**FIN DU MODULE 1**
