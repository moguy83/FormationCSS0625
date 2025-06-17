
# Module 6 — Pour aller plus loin : Mise en page avancée

## Objectifs pédagogiques

- Comprendre le responsive design et l’utilisation des media queries.
- Découvrir les animations CSS.
- Maîtriser les bases des systèmes modernes de mise en page : Flexbox et Grid.

---

## 1️⃣ Les media queries — Le responsive design

### a) Pourquoi responsive ?

- Adapter les sites web aux différentes tailles d’écran (mobile, tablette, desktop).
- Meilleure expérience utilisateur.
- Recommandation SEO et accessibilité.

### b) Syntaxe de base

```css
@media (condition) {
  /* règles CSS à appliquer */
}
```

### c) Exemple simple

```css
body {
  background-color: lightblue;
}

@media (max-width: 600px) {
  body {
    background-color: lightcoral;
  }
}
```

Si la largeur de l’écran est inférieure à 600px, le fond devient rouge.

### d) Principaux critères

| Media query | Description |
|--------------|-------------|
| max-width | largeur maximale |
| min-width | largeur minimale |
| orientation: portrait | en mode portrait |
| orientation: landscape | en mode paysage |

### e) Exemple classique mobile-first

```css
body {
  font-size: 18px;
}

@media (max-width: 600px) {
  body {
    font-size: 16px;
  }
}
```

---

## 2️⃣ Les animations CSS

### a) Transitions simples

```css
button {
  background-color: blue;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: darkblue;
}
```

Permet d’adoucir les changements de style.

### b) Animation complète via @keyframes

```css
@keyframes slide {
  0% { transform: translateX(0); }
  100% { transform: translateX(200px); }
}

div {
  animation: slide 2s infinite alternate;
}
```

Crée une animation fluide d’un déplacement horizontal.

---

## 3️⃣ Flexbox — Disposition flexible

### a) Pourquoi Flexbox ?

- Simplifie énormément les mises en page.
- Remplace avantageusement float et position pour organiser des blocs.

### b) Mise en place d’un conteneur flex

```css
.container {
  display: flex;
}
```

Les enfants du conteneur deviennent flexibles.

### c) Principales propriétés du conteneur

| Propriété | Rôle |
|------------|------|
| flex-direction | sens principal (row, column) |
| justify-content | alignement horizontal |
| align-items | alignement vertical |
| flex-wrap | retour à la ligne |

Exemple :

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}
```

### d) Propriétés des éléments enfants

```css
.item {
  flex: 1;
  order: 2;
  align-self: flex-end;
}
```

- flex contrôle la croissance
- order modifie l’ordre d’affichage
- align-self ajuste l’alignement local de l’élément

### e) Démonstration simple

HTML :

```html
<div class="container">
  <div class="box">A</div>
  <div class="box">B</div>
  <div class="box">C</div>
</div>
```

CSS :

```css
.container {
  display: flex;
  justify-content: space-around;
}

.box {
  background: lightcoral;
  padding: 20px;
}
```

---

## 4️⃣ Grid — Grille de mise en page

### a) Pourquoi Grid ?

- Permet de construire des structures en lignes et colonnes.
- Parfait pour les maquettes complexes.

### b) Définir une grille de base

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto auto;
  gap: 10px;
}
```

Ici : 3 colonnes (largeur fixe et fluide), 2 lignes.

### c) Placer un élément dans la grille

```css
.item1 {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

### d) Démonstration simple

HTML :

```html
<div class="container">
  <div class="header">Header</div>
  <div class="menu">Menu</div>
  <div class="main">Main</div>
  <div class="footer">Footer</div>
</div>
```

CSS :

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "menu main"
    "footer footer";
  grid-template-columns: 200px 1fr;
  gap: 10px;
}

.header { grid-area: header; background: lightblue; }
.menu { grid-area: menu; background: lightcoral; }
.main { grid-area: main; background: lightgreen; }
.footer { grid-area: footer; background: lightgrey; }
```

---

## 5️⃣ 🎯 Exercice final — Mini projet responsive

### Objectif

Créer une page vitrine responsive qui s’adapte aux écrans :

- Utilise Grid pour la structure principale.
- Flexbox pour organiser des blocs internes.
- Ajoute une transition au survol de boutons.
- Gère la taille du texte avec media queries.

### Résultat attendu

- Sur desktop : menu latéral à gauche + contenu principal.
- Sur mobile : menu en haut, contenu en dessous.

### Structure HTML de départ

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Mini site responsive</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>Ma Vitrine</header>
  <nav>Menu</nav>
  <main>Contenu principal</main>
  <footer>Pied de page</footer>
</body>
</html>
```

### Corrigé simplifié (style.css)

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

header, nav, main, footer {
  padding: 20px;
  color: white;
}

header { background: #333; }
nav { background: #555; }
main { background: #777; min-height: 300px; }
footer { background: #999; }

.container {
  display: grid;
  grid-template-areas:
    "header header"
    "nav main"
    "footer footer";
  grid-template-columns: 200px 1fr;
}

header { grid-area: header; }
nav { grid-area: nav; }
main { grid-area: main; }
footer { grid-area: footer; }

@media (max-width: 600px) {
  .container {
    grid-template-areas:
      "header"
      "nav"
      "main"
      "footer";
    grid-template-columns: 1fr;
  }
}
```

---

**FIN DU MODULE 6**
