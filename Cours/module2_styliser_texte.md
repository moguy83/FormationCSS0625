
# Module 2 — Styliser le texte

## Objectifs pédagogiques

- Savoir modifier l’apparence du texte avec CSS.
- Connaître les différentes manières de définir les couleurs.
- Comprendre les différentes unités de mesure.
- Jouer sur l’alignement, les décorations, la police, l’importance.

---

## 1️⃣ Changer la couleur du texte

Propriété principale : `color`

Exemple simple :

```css
p {
  color: red;
}
```

Cela applique la couleur rouge à tous les paragraphes.

---

## 2️⃣ Les couleurs CSS

### a) Couleurs par nom

CSS connaît une liste de couleurs prédéfinies :

```css
p {
  color: blue;
  color: orange;
  color: darkgreen;
  color: coral;
}
```

Il existe 147 noms de couleurs standards (voir la liste complète sur MDN).

### b) Couleurs hexadécimales

Format `#RRGGBB` :

```css
p {
  color: #ff0000; /* rouge pur */
  color: #00ff00; /* vert pur */
  color: #0000ff; /* bleu pur */
}
```

On peut aussi utiliser la forme abrégée :

```css
color: #f00; /* équivalent à #ff0000 */
```

### c) Couleurs en `rgb()` et `rgba()`

Format décimal de 0 à 255 :

```css
p {
  color: rgb(255, 0, 0); /* rouge */
  color: rgb(0, 128, 0); /* vert foncé */
  color: rgb(0, 0, 255); /* bleu */
}
```

Avec transparence grâce à `rgba()` (a = alpha, de 0 à 1) :

```css
p {
  color: rgba(255, 0, 0, 0.5); /* rouge transparent à 50% */
}
```

### d) Couleurs en `hsl()` et `hsla()`

Format souvent plus pratique pour des dégradés ou ajustements dynamiques.

- `h` = teinte (0 à 360°)
- `s` = saturation (0% à 100%)
- `l` = luminosité (0% à 100%)

```css
p {
  color: hsl(0, 100%, 50%); /* rouge pur */
  color: hsl(120, 100%, 25%); /* vert foncé */
  color: hsl(240, 100%, 50%); /* bleu pur */
}
```

Avec transparence :

```css
p {
  color: hsla(240, 100%, 50%, 0.3);
}
```

---

## 3️⃣ Changer la taille du texte

Propriété : `font-size`

Exemples :

```css
p {
  font-size: 20px;
}
```

### a) Unités absolues

| Unité | Signification |
|-------|----------------|
| px    | pixels        |
| pt    | points (impression) |
| cm    | centimètres   |
| mm    | millimètres   |

Exemples :

```css
p {
  font-size: 12pt;
  font-size: 1cm;
}
```

Remarque : sur le web, le `px` reste le plus utilisé.

### b) Unités relatives

| Unité | Base de calcul |
|-------|------------------|
| em    | taille relative à l’élément parent |
| rem   | taille relative à la racine (`html`) |
| %     | pourcentage de la taille du parent |

Exemples :

```css
p {
  font-size: 2em;
  font-size: 1.5rem;
  font-size: 120%;
}
```

Cas particulier de `rem` :

```css
html {
  font-size: 16px;
}
p {
  font-size: 1.5rem; /* 24px */
}
```

### c) Viewport units (rare pour la taille du texte)

- `vw` (viewport width)
- `vh` (viewport height)

Exemple (texte responsive) :

```css
h1 {
  font-size: 5vw;
}
```

---

## 4️⃣ Alignement du texte

Propriété : `text-align`

```css
p {
  text-align: left;
  text-align: center;
  text-align: right;
  text-align: justify;
}
```

Exemple justifié :

```css
p {
  text-align: justify;
}
```

---

## 5️⃣ Décoration du texte

`text-decoration`

```css
p {
  text-decoration: underline;
  text-decoration: line-through;
  text-decoration: overline;
  text-decoration: none;
}
```

---

## 6️⃣ Mise en gras et en italique

### Gras

```css
p {
  font-weight: normal;
  font-weight: bold;
  font-weight: 700;
}
```

### Italique

```css
p {
  font-style: normal;
  font-style: italic;
  font-style: oblique;
}
```

---

## 7️⃣ Changer la police

Propriété : `font-family`

Exemples :

```css
p {
  font-family: Arial, Helvetica, sans-serif;
}
```

Toujours prévoir plusieurs polices en cascade.

Polices web safe fréquentes : Arial, Verdana, Times New Roman, Courier New.

Importer des polices avec Google Fonts :

HTML :

```html
<link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
```

CSS :

```css
p {
  font-family: 'Roboto', sans-serif;
}
```

---

## 8️⃣ Importance du style

`!important` permet de forcer une règle :

```css
p {
  color: red !important;
}
```

⚠ Attention : à utiliser avec modération. Cela complique la maintenance et le débogage.

---

## 🎯 Exercice pratique 2 — Styliser un article

### Objectif

Créer un fichier HTML + CSS contenant un article stylisé intégralement.

### Contenu HTML proposé :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Mon article stylisé</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Le CSS, c'est facile !</h1>
  <h2>Un sous-titre accrocheur</h2>
  <p>Voici un premier paragraphe avec du texte d'exemple pour pratiquer le CSS.</p>
  <p>Un autre paragraphe pour expérimenter différentes propriétés de style.</p>
</body>
</html>
```

### Instructions

Dans `style.css` :

- Mettre le `h1` en rouge, centré, police Verdana.
- Mettre le `h2` en bleu foncé, en italique, taille 28px.
- Mettre les `p` en gris foncé, justifiés, taille 1.2em.
- Souligner le premier `p`, barrer le deuxième.

### Corrigé proposé

```css
h1 {
  color: red;
  text-align: center;
  font-family: Verdana, sans-serif;
}

h2 {
  color: darkblue;
  font-style: italic;
  font-size: 28px;
}

p {
  color: #333;
  text-align: justify;
  font-size: 1.2em;
}

p:first-of-type {
  text-decoration: underline;
}

p:nth-of-type(2) {
  text-decoration: line-through;
}
```

---

**FIN DU MODULE 2**
