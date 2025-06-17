
# Module 5 — La mise en page

## Objectifs pédagogiques

- Comprendre comment positionner des éléments dans une page.
- Manipuler les flottants (float) pour des mises en page simples.
- Maîtriser les différents positionnements (static, relative, absolute, fixed, sticky).
- Visualiser les limites des anciens systèmes de mise en page avant Flexbox et Grid.

---

## 1️⃣ Les éléments flottants (float)

### a) Principe de float

`float` permet de faire « flotter » un élément à gauche ou à droite, pour qu’un autre contenu puisse s’enrouler autour.

Exemple simple :

```css
img {
  float: right;
  margin: 10px;
}
```

L’image se place à droite et le texte du paragraphe s’enroule autour de l’image.

### b) Valeurs possibles

- left : flotte à gauche.
- right : flotte à droite.
- none : comportement normal.
- inherit : hérite du parent.

### c) Problème du parent « vidé »

Lorsque tous les enfants d’un conteneur sont flottants, le conteneur ne prend plus de hauteur.

Exemple illustratif :

```html
<div class="container">
  <div class="box1"></div>
  <div class="box2"></div>
</div>
```

```css
.container {
  background: lightgrey;
}

.box1 {
  float: left;
  width: 100px;
  height: 100px;
  background: red;
}

.box2 {
  float: left;
  width: 100px;
  height: 100px;
  background: blue;
}
```

Le fond gris ne s’affiche pas correctement car la hauteur du conteneur est « effondrée ».

### d) Solution : le clearfix

Méthode moderne via `::after` :

```css
.container::after {
  content: "";
  display: block;
  clear: both;
}
```

Autre possibilité :

```css
.container {
  overflow: hidden;
}
```

💡 Important à montrer car c'était la base avant Flexbox et Grid.

---

## 2️⃣ Le positionnement (position)

La propriété `position` contrôle précisément l’endroit où s’affiche un élément dans la page.

### a) `position: static` (par défaut)

```css
div {
  position: static;
}
```

Comportement naturel de l’élément dans le flux normal.

### b) `position: relative`

```css
div {
  position: relative;
  top: 20px;
  left: 30px;
}
```

L’élément est déplacé par rapport à sa position normale.

L'espace réservé initial reste présent.

### c) `position: absolute`

```css
div {
  position: absolute;
  top: 20px;
  left: 30px;
}
```

L’élément est retiré du flux normal.

Positionné relativement à son premier parent positionné (relative, absolute ou fixed), sinon au `<body>`.

Exemple pédagogique :

```html
<div class="container">
  <div class="relative">
    <div class="absolute"></div>
  </div>
</div>
```

```css
.container {
  position: relative;
  width: 300px;
  height: 300px;
  background: lightgrey;
}

.absolute {
  position: absolute;
  top: 20px;
  left: 20px;
  width: 50px;
  height: 50px;
  background: red;
}
```

💡 Bien expliquer la notion de contexte de positionnement.

### d) `position: fixed`

```css
div {
  position: fixed;
  top: 0;
  right: 0;
}
```

Fixe l’élément par rapport à la fenêtre (viewport).

Ne bouge pas au scroll.

Exemple d'usage : barres de navigation fixes, boutons retour en haut.

### e) `position: sticky`

```css
div {
  position: sticky;
  top: 0;
}
```

Mélange entre relative et fixed.

L'élément reste dans le flux tant qu’il n’atteint pas la position définie.

Pratique pour les en-têtes fixes au scroll.

Démonstration simple :

```css
header {
  position: sticky;
  top: 0;
  background: white;
  border-bottom: 1px solid grey;
}
```

---

## 3️⃣ Cas d’usage comparés (récapitulatif simple)

| Position | Effet principal |
|----------|------------------|
| static   | position normale (défaut) |
| relative | décalage léger sans sortir du flux |
| absolute | position libre par rapport au parent positionné |
| fixed    | toujours visible à la même position (viewport) |
| sticky   | reste visible jusqu’à une certaine position en scroll |

---

## 🎯 Exercice pratique 5 — Maquette simple de page

### Objectif

Mettre en pratique le positionnement simple avec float et position.

### Instructions

Créer une page avec :

- Un header fixe en haut (`position: fixed` ou `sticky`)
- Un menu latéral flottant à gauche (`float: left`)
- Un contenu principal à droite

### Structure HTML proposée

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Maquette positionnement</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>Mon site</header>
  <div class="menu">Menu</div>
  <div class="content">Contenu principal</div>
</body>
</html>
```

### Corrigé proposé (style.css)

```css
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

header {
  background: #333;
  color: white;
  text-align: center;
  padding: 15px;
  position: sticky;
  top: 0;
  z-index: 1;
}

.menu {
  float: left;
  width: 200px;
  height: 100vh;
  background: #eee;
  padding: 20px;
}

.content {
  margin-left: 220px;
  padding: 20px;
}
```

💡 À souligner : on prépare ici le terrain pour Flexbox et Grid.

`float` commence à devenir obsolète pour la mise en page complexe.

`position` reste essentiel pour des éléments isolés (modals, menus flottants, sticky header…).

---

**FIN DU MODULE 5**
