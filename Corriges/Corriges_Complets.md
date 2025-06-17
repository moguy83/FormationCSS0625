# Corrigés — Formation CSS Initiation (2 jours)

---

## Corrigé Exercice 1.1 (Module 1)

### Fichier HTML `index.html`

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Exercice 1</title>
  <style>
    p {
      color: red;
    }
  </style>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1 style="color: blue;">Bienvenue</h1>
  <p>Ceci est un paragraphe stylisé.</p>
</body>
</html>
```

### Fichier CSS externe `style.css`

```css
body {
  background-color: #f0f0f0;
}
```

---

## Corrigé Exercice 2.1 (Module 2)

### Fichier `style.css`

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

## Corrigé Exercice 3.1 (Module 3)

### Fichier `style.css`

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
  box-sizing: border-box;
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

## Corrigé Exercice 4.1 (Module 4)

### Fichier `style.css`

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

a:visited {
  color: purple;
}

a:active {
  color: orange;
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

## Corrigé Exercice 5.1 (Module 5)

### Fichier `style.css`

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

.container::after {
  content: "";
  display: block;
  clear: both;
}
```

---

## Corrigé Exercice 6.1 (Module 6)

### Fichier `style.css`

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

button {
  background-color: #007bff;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  transition: background-color 0.3s ease;
  animation: fade 3s infinite alternate;
}

button:hover {
  background-color: #0056b3;
}

@keyframes fade {
  0% { opacity: 0.5; }
  100% { opacity: 1; }
}
```
