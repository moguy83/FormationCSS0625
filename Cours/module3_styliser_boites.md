
# Module 3 — Styliser les boîtes

## Objectifs pédagogiques

- Comprendre le modèle de boîte (Box Model) CSS.
- Manipuler la taille, les marges, les bordures et le remplissage (padding).
- Modifier le type de boîte avec display.
- Appliquer des couleurs d’arrière-plan.

---

## 1️⃣ Le modèle de boîte (Box Model)

### Fondamentaux

En CSS, tout élément HTML est une boîte avec les dimensions suivantes :

```
+-----------------------------+
|           Margin            |
|  +-----------------------+  |
|  |       Border          |  |
|  |  +-----------------+  |  |
|  |  |    Padding      |  |  |
|  |  | +-------------+ |  |  |
|  |  | |  Content    | |  |  |
|  |  | +-------------+ |  |  |
|  |  +-----------------+  |  |
|  +-----------------------+  |
+-----------------------------+
```

- Content : le contenu de l'élément (texte, image…)
- Padding : espace entre le contenu et la bordure
- Border : bordure de l'élément
- Margin : espace extérieur séparant la boîte des autres éléments

### Visualisation avec Chrome (ou tout navigateur moderne)

Outil très pédagogique à montrer en formation : Clic droit > Inspecter > Styles > Box Model

### Démonstration simple

```css
div {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  margin: 15px;
}
```

### Calcul de la taille totale de la boîte

Par défaut (`box-sizing: content-box`) :

Largeur totale = width + padding gauche/droite + border gauche/droite + margin gauche/droite

Exemple :

- width: 200px
- padding: 20px -> 40px
- border: 5px -> 10px
- total: 200 + 40 + 10 = 250px (hors margin)

### Alternative : `box-sizing: border-box`

Simplifie les calculs car width inclut tout sauf la margin.

```css
div {
  box-sizing: border-box;
}
```

Très recommandé aujourd'hui.

---

## 2️⃣ Changer le type d’élément (display)

La propriété `display` détermine comment l'élément est affiché.

| Valeur      | Description |
|-------------|-------------|
| block       | nouvelle ligne, prend toute la largeur |
| inline      | dans le flux du texte |
| inline-block| inline mais accepte largeur/hauteur |
| none        | masqué |

### Exemples

#### `display: block` (par défaut sur div, p, h1, etc.) :

```css
div {
  display: block;
}
```

#### `display: inline` :

```css
span {
  display: inline;
}
```

#### `display: inline-block` :

```css
button {
  display: inline-block;
}
```

#### `display: none` (cacher un élément) :

```css
p {
  display: none;
}
```

### Démonstration de conversion

```css
a {
  display: block;
  width: 200px;
  background: yellow;
}
```

Le lien devient un bloc.

---

## 3️⃣ La couleur de fond

Propriété : `background-color`

```css
div {
  background-color: lightblue;
}
```

Autres propriétés associées :

- background-image
- background-repeat
- background-position
- background-size
- background-attachment

### Exemple avec image de fond :

```css
div {
  background-image: url("image.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
```

---

## 4️⃣ La taille des boîtes

Propriétés : `width` et `height`

```css
div {
  width: 300px;
  height: 150px;
}
```

### Valeurs relatives possibles :

```css
div {
  width: 80%;    
  height: 50vh;
}
```

---

## 5️⃣ Les marges

Propriété : `margin`

Créer de l’espace extérieur à la boîte.

### Valeurs simples :

```css
div {
  margin: 20px;
}
```

### Marges séparées :

```css
div {
  margin-top: 10px;
  margin-right: 15px;
  margin-bottom: 20px;
  margin-left: 25px;
}
```

### Syntaxe raccourcie :

```css
div {
  margin: 10px 15px 20px 25px; /* haut, droite, bas, gauche */
}
```

### Centrer un bloc horizontalement :

```css
div {
  margin: 0 auto;
}
```

---

## 6️⃣ Les marges internes (Padding)

Propriété : `padding`

Créer de l’espace intérieur entre le contenu et la bordure.

### Exemples :

```css
div {
  padding: 15px;
}

div {
  padding: 10px 20px;
}
```

---

## 7️⃣ Les bordures

### Propriétés de base :

- border-width
- border-style
- border-color

### Exemple complet :

```css
div {
  border-width: 5px;
  border-style: solid;
  border-color: blue;
}
```

### Syntaxe raccourcie :

```css
div {
  border: 5px solid blue;
}
```

### Styles de bordures possibles :

- solid
- dashed
- dotted
- double
- groove
- ridge
- inset
- outset

### Coins arrondis : `border-radius`

```css
div {
  border-radius: 10px;
}
```

Permet de faire des boutons et des cartes plus modernes.

---

## 🎯 Exercice pratique 3 — Carte de profil

### Objectif

Mettre en pratique toutes les notions du module.

### Instructions

Créer une fiche de profil simple avec :

- Un conteneur centré
- Largeur fixe (300px)
- Couleur de fond claire
- Bordure avec coins arrondis
- Padding intérieur
- Deux paragraphes avec marges et décorations différentes

### Code de base HTML :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Ma carte profil</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="carte">
    <h2>Jean Dupont</h2>
    <p>Développeur web junior</p>
    <p>Passionné de CSS et de belles interfaces !</p>
  </div>
</body>
</html>
```

### Corrigé proposé (style.css)

```css
body {
  background-color: #f5f5f5;
  font-family: Arial, sans-serif;
}

.carte {
  width: 300px;
  margin: 50px auto;
  background-color: #fff;
  border: 2px solid #ddd;
  border-radius: 15px;
  padding: 20px;
  text-align: center;
  box-shadow: 2px 2px 10px rgba(0,0,0,0.1);
}

.carte h2 {
  margin-bottom: 10px;
  color: #333;
}

.carte p:first-of-type {
  color: #666;
  font-style: italic;
}

.carte p:last-of-type {
  color: #444;
  font-weight: bold;
}
```

---

**FIN DU MODULE 3**
