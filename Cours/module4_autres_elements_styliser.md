
# Module 4 — Autres éléments à styliser

## Objectifs pédagogiques

- Savoir styliser les listes HTML.
- Savoir modifier l’apparence des liens hypertexte.
- Comprendre la gestion du style sur les tableaux.
- Manipuler les pseudo-classes courantes pour interactions.

---

## 1️⃣ Styliser les listes

### Rappel HTML de base

Liste ordonnée (`<ol>`) :

```html
<ol>
  <li>Premier item</li>
  <li>Deuxième item</li>
</ol>
```

Liste non ordonnée (`<ul>`) :

```html
<ul>
  <li>Pomme</li>
  <li>Poire</li>
</ul>
```

### a) Modifier le type de puce : list-style-type

```css
ul {
  list-style-type: square;
}
```

Autres valeurs fréquentes :

| list-style-type | Description |
|------------------|-------------|
| disc (défaut)    | rond plein |
| circle           | rond vide  |
| square           | carré plein |
| none             | supprime les puces |

Pour listes ordonnées :

```css
ol {
  list-style-type: upper-roman;
}
```

Autres valeurs possibles : decimal, lower-alpha, upper-alpha, lower-roman.

### b) Position des puces : list-style-position

- inside : les puces sont dans le bloc de texte
- outside (défaut) : les puces sont à l’extérieur

```css
ul {
  list-style-position: inside;
}
```

### c) Supprimer totalement les puces

```css
ul {
  list-style: none;
  padding-left: 0;
}
```

### d) Image personnalisée de puce : list-style-image

```css
ul {
  list-style-image: url("puce.png");
}
```

⚠ Très peu utilisé aujourd'hui car difficilement responsive.

---

## 2️⃣ Styliser les liens

### a) Rappel HTML d’un lien

```html
<a href="https://www.exemple.com">Lien vers exemple</a>
```

### b) Modifier la couleur et l’apparence

```css
a {
  color: blue;
  text-decoration: none;
  font-weight: bold;
}
```

Supprimer le soulignement :

```css
a {
  text-decoration: none;
}
```

### c) Utiliser les pseudo-classes de lien

| Pseudo-classe | Quand elle s’applique |
|----------------|-----------------------|
| :link          | avant d’avoir cliqué |
| :visited       | après avoir visité   |
| :hover         | au survol            |
| :active        | pendant le clic      |

Exemple complet :

```css
a:link {
  color: blue;
}

a:visited {
  color: purple;
}

a:hover {
  color: red;
  text-decoration: underline;
}

a:active {
  color: orange;
}
```

💡 Important en accessibilité : toujours conserver un contraste suffisant et indiquer les états de visite.

### d) Démonstration pédagogique : effet de bouton

```css
a {
  display: inline-block;
  background-color: #007bff;
  color: white;
  padding: 10px 20px;
  border-radius: 5px;
  text-decoration: none;
  transition: background-color 0.3s;
}

a:hover {
  background-color: #0056b3;
}
```

---

## 3️⃣ Styliser les tableaux

### a) Rappel HTML d’un tableau

```html
<table>
  <thead>
    <tr>
      <th>Nom</th>
      <th>Âge</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Jean</td>
      <td>25</td>
    </tr>
  </tbody>
</table>
```

### b) Bordures et espacement

Par défaut, chaque cellule a sa propre bordure :

```css
table, th, td {
  border: 1px solid black;
}
```

Fusionner les bordures avec `border-collapse` :

```css
table {
  border-collapse: collapse;
}
```

- collapse : fusionne les bordures
- separate : comportement par défaut

### c) Espacement interne et externe

```css
th, td {
  padding: 10px;
  text-align: center;
}
```

### d) Mise en forme complète

```css
table {
  border-collapse: collapse;
  width: 100%;
}

th {
  background-color: #f2f2f2;
}

td, th {
  border: 1px solid #ddd;
  padding: 8px;
}
```

### e) Alternance de couleur (zébrage) avec nth-child

```css
tbody tr:nth-child(even) {
  background-color: #f9f9f9;
}
```

---

## 🎯 Exercice pratique 4 — Annuaire complet

### Objectif

Créer une page d’annuaire stylisée regroupant :

- Une liste de membres (utilisation de liste)
- Des liens vers leur profil
- Un tableau récapitulatif

### Fichier HTML de base

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Annuaire CSS</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Annuaire de l'équipe</h1>

  <ul>
    <li><a href="#">Jean Dupont</a></li>
    <li><a href="#">Marie Curie</a></li>
    <li><a href="#">Albert Einstein</a></li>
  </ul>

  <table>
    <thead>
      <tr>
        <th>Nom</th>
        <th>Poste</th>
        <th>Ville</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Jean Dupont</td>
        <td>Développeur</td>
        <td>Paris</td>
      </tr>
      <tr>
        <td>Marie Curie</td>
        <td>Scientifique</td>
        <td>Varsovie</td>
      </tr>
      <tr>
        <td>Albert Einstein</td>
        <td>Physicien</td>
        <td>Berne</td>
      </tr>
    </tbody>
  </table>
</body>
</html>
```

### Corrigé proposé (style.css)

```css
body {
  font-family: Arial, sans-serif;
  margin: 40px;
}

h1 {
  text-align: center;
  color: #333;
}

ul {
  list-style-type: none;
  padding-left: 0;
}

ul li {
  margin-bottom: 10px;
}

a {
  text-decoration: none;
  color: #007bff;
  font-weight: bold;
  transition: color 0.3s;
}

a:hover {
  color: #0056b3;
}

table {
  border-collapse: collapse;
  width: 100%;
  margin-top: 30px;
}

th {
  background-color: #f2f2f2;
}

td, th {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: center;
}

tbody tr:nth-child(even) {
  background-color: #f9f9f9;
}
```

---

**FIN DU MODULE 4**
