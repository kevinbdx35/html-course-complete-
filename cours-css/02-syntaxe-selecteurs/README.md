# Module 2 : Syntaxe et sélecteurs CSS

## 🎯 Objectifs du module

- Maîtriser la syntaxe CSS complète
- Comprendre les différents types de sélecteurs
- Apprendre la spécificité et la cascade
- Utiliser les pseudo-classes et pseudo-éléments

## 📝 Syntaxe CSS approfondie

### Structure d'une règle CSS

```css
sélecteur {
    propriété: valeur;
    propriété: valeur1 valeur2;
    propriété: valeur !important;
}
```

### Commentaires

```css
/* Commentaire sur une ligne */

/*
   Commentaire
   sur plusieurs
   lignes
*/

/* ========================
   SECTION NAVIGATION
   ======================== */
```

### Règles de syntaxe importantes

```css
/* ✅ Correct */
p {
    color: blue;
    font-size: 16px;
    margin: 10px 0;
}

/* ❌ Incorrect */
p {
    color blue;      /* Manque les deux-points */
    font-size: 16px  /* Manque le point-virgule */
    margin 10px 0;   /* Manque les deux-points */
}
```

## 🎯 Types de sélecteurs

### 1. Sélecteurs de base

#### Sélecteur universel
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

#### Sélecteurs d'élément
```css
h1 { color: red; }
p { font-size: 16px; }
div { background: gray; }
```

#### Sélecteurs de classe
```css
.titre { color: blue; }
.bouton { padding: 10px; }
.highlight { background: yellow; }
```

```html
<h1 class="titre">Titre principal</h1>
<button class="bouton">Cliquer</button>
<p class="highlight">Texte surligné</p>
```

#### Sélecteurs d'ID
```css
#header { background: navy; }
#sidebar { width: 300px; }
#footer { text-align: center; }
```

```html
<header id="header">En-tête</header>
<aside id="sidebar">Barre latérale</aside>
<footer id="footer">Pied de page</footer>
```

### 2. Sélecteurs d'attribut

```css
/* Élément avec attribut */
input[type] { border: 1px solid #ccc; }

/* Valeur exacte */
input[type="text"] { background: white; }
input[type="email"] { background: #f0f0f0; }

/* Contient la valeur */
a[href*="google"] { color: red; }

/* Commence par */
a[href^="https"] { color: green; }

/* Finit par */
a[href$=".pdf"] { color: blue; }

/* Contient le mot */
div[class~="active"] { font-weight: bold; }
```

### 3. Sélecteurs combinés

#### Sélecteur descendant (espace)
```css
/* Tous les p dans article */
article p {
    line-height: 1.8;
}

/* Tous les a dans nav */
nav a {
    text-decoration: none;
}
```

#### Sélecteur enfant direct (>)
```css
/* Seulement les p enfants directs */
article > p {
    margin-bottom: 20px;
}

/* Seulement les li enfants de ul */
ul > li {
    list-style: disc;
}
```

#### Sélecteur frère adjacent (+)
```css
/* h1 suivi directement d'un p */
h1 + p {
    font-weight: bold;
    font-size: 1.2em;
}

/* Image suivie d'un paragraphe */
img + p {
    margin-top: 10px;
}
```

#### Sélecteur frères généraux (~)
```css
/* Tous les p après h1 */
h1 ~ p {
    color: gray;
}

/* Tous les div après .active */
.active ~ div {
    opacity: 0.7;
}
```

## 🎭 Pseudo-classes

### Pseudo-classes d'état

```css
/* États des liens */
a:link { color: blue; }
a:visited { color: purple; }
a:hover { color: red; }
a:active { color: orange; }

/* États des éléments de formulaire */
input:focus { border-color: blue; }
input:disabled { background: #f5f5f5; }
input:checked { background: green; }

/* États généraux */
button:hover { background: #007bff; }
.menu-item:active { transform: scale(0.98); }
```

### Pseudo-classes structurelles

```css
/* Premier et dernier enfant */
li:first-child { margin-top: 0; }
li:last-child { margin-bottom: 0; }

/* Enfants par type */
p:first-of-type { font-weight: bold; }
p:last-of-type { margin-bottom: 0; }

/* Nth-child */
tr:nth-child(odd) { background: #f9f9f9; }
tr:nth-child(even) { background: white; }
tr:nth-child(3) { background: yellow; }
tr:nth-child(3n) { background: lightblue; }

/* Nth-of-type */
h2:nth-of-type(2) { color: red; }
img:nth-of-type(odd) { float: left; }
```

### Pseudo-classes de ciblage

```css
/* Élément ciblé par une ancre */
:target { background: yellow; }

/* Élément vide */
p:empty { display: none; }

/* Élément racine */
:root { font-size: 16px; }

/* Négation */
input:not([type="submit"]) { border: 1px solid #ccc; }
```

## 🎨 Pseudo-éléments

### Pseudo-éléments de contenu

```css
/* Before et after */
.citation::before {
    content: "« ";
    color: gray;
}

.citation::after {
    content: " »";
    color: gray;
}

/* Première ligne et première lettre */
p::first-line {
    font-weight: bold;
}

p::first-letter {
    font-size: 3em;
    float: left;
    margin-right: 5px;
}
```

### Pseudo-éléments de sélection

```css
/* Texte sélectionné */
::selection {
    background: #007bff;
    color: white;
}

/* Placeholder des inputs */
input::placeholder {
    color: #999;
    font-style: italic;
}
```

## ⚖️ Spécificité et cascade

### Calcul de la spécificité

```css
/* Spécificité: 0,0,0,1 */
h1 { color: red; }

/* Spécificité: 0,0,1,0 */
.titre { color: blue; }

/* Spécificité: 0,1,0,0 */
#header { color: green; }

/* Spécificité: 0,0,1,1 */
h1.titre { color: yellow; }

/* Spécificité: 0,1,1,0 */
#header .titre { color: purple; }

/* Force la priorité */
h1 { color: orange !important; }
```

### Ordre de priorité

1. **Styles inline** (1,0,0,0)
2. **IDs** (0,1,0,0)
3. **Classes, attributs, pseudo-classes** (0,0,1,0)
4. **Éléments et pseudo-éléments** (0,0,0,1)

## 💻 Exemple pratique complet

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sélecteurs CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header id="header">
        <nav class="navigation">
            <ul>
                <li><a href="#home" class="active">Accueil</a></li>
                <li><a href="#about">À propos</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <article>
            <h1 class="titre-principal">Titre de l'article</h1>
            <p class="introduction">Ceci est l'introduction de l'article.</p>
            <p>Premier paragraphe normal.</p>
            <p>Deuxième paragraphe normal.</p>
            <p>Dernier paragraphe.</p>
        </article>

        <aside class="sidebar">
            <h2>Articles connexes</h2>
            <ul>
                <li><a href="#">Article 1</a></li>
                <li><a href="#">Article 2</a></li>
                <li><a href="#">Article 3</a></li>
            </ul>
        </aside>
    </main>

    <footer id="footer">
        <p>&copy; 2024 Mon site web</p>
    </footer>
</body>
</html>
```

**CSS :**
```css
/* Reset de base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Styles généraux */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Header */
#header {
    background: #2c3e50;
    color: white;
    padding: 1rem 0;
}

.navigation ul {
    list-style: none;
    display: flex;
    justify-content: center;
}

.navigation li {
    margin: 0 20px;
}

.navigation a {
    color: white;
    text-decoration: none;
    padding: 10px 15px;
    border-radius: 5px;
    transition: background 0.3s;
}

.navigation a:hover {
    background: #34495e;
}

.navigation a.active {
    background: #3498db;
}

/* Main content */
main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 2rem;
}

/* Article */
article {
    background: white;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.titre-principal {
    color: #2c3e50;
    font-size: 2.5em;
    margin-bottom: 1rem;
    border-bottom: 3px solid #3498db;
    padding-bottom: 0.5rem;
}

.introduction {
    font-size: 1.2em;
    font-weight: bold;
    color: #7f8c8d;
    margin-bottom: 1.5rem;
}

article p {
    margin-bottom: 1rem;
    text-align: justify;
}

article p:last-child {
    margin-bottom: 0;
}

/* Sidebar */
.sidebar {
    background: #ecf0f1;
    padding: 1.5rem;
    border-radius: 8px;
    height: fit-content;
}

.sidebar h2 {
    color: #2c3e50;
    margin-bottom: 1rem;
    font-size: 1.3em;
}

.sidebar ul {
    list-style: none;
}

.sidebar li {
    margin-bottom: 0.5rem;
}

.sidebar a {
    color: #3498db;
    text-decoration: none;
}

.sidebar a:hover {
    text-decoration: underline;
}

/* Footer */
#footer {
    background: #2c3e50;
    color: white;
    text-align: center;
    padding: 2rem;
    margin-top: 2rem;
}

/* Pseudo-éléments */
.introduction::before {
    content: "📖 ";
    font-size: 1.2em;
}

article p::first-letter {
    font-size: 1.5em;
    font-weight: bold;
    color: #3498db;
}

/* Pseudo-classes structurelles */
.sidebar li:first-child {
    font-weight: bold;
}

.sidebar li:nth-child(even) {
    background: rgba(52, 152, 219, 0.1);
    padding: 5px;
    border-radius: 3px;
}

/* Sélection de texte */
::selection {
    background: #3498db;
    color: white;
}
```

## ✅ Exercice pratique

1. Créez une page HTML avec :
   - Un header avec navigation
   - Un article avec plusieurs paragraphes
   - Une sidebar avec liste
   - Un footer

2. Utilisez différents sélecteurs :
   - Sélecteurs d'élément, classe, ID
   - Sélecteurs combinés
   - Pseudo-classes (:hover, :first-child, :nth-child)
   - Pseudo-éléments (::before, ::after)

3. Testez la spécificité avec différentes règles

## 🔍 Bonnes pratiques

- **Utilisez des noms de classe descriptifs** : `.btn-primary` plutôt que `.blue`
- **Évitez les sélecteurs trop spécifiques** : `.nav ul li a` → `.nav-link`
- **Organisez vos sélecteurs** par spécificité croissante
- **Utilisez les pseudo-classes** pour les états interactifs
- **Évitez `!important`** sauf cas exceptionnels

## 🔗 Ressources supplémentaires

- [MDN - Sélecteurs CSS](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Selectors)
- [CSS Specificity Calculator](https://specificity.keegan.st/)
- [CSS Selector Game](https://flukeout.github.io/)

---

**Temps estimé :** 3 heures  
**Prochaine étape :** [Module 3 - Propriétés de texte](../03-proprietes-texte/)