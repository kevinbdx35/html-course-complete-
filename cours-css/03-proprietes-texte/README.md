# Module 3 : Propriétés de texte et typographie

## 🎯 Objectifs du module

- Maîtriser les propriétés de formatage de texte
- Comprendre la typographie web
- Utiliser les polices et les unités de mesure
- Créer des mises en forme de texte attractives

## 📝 Propriétés de base du texte

### Couleur du texte

```css
/* Couleurs nommées */
p { color: red; }
h1 { color: blue; }

/* Couleurs hexadécimales */
.titre { color: #2c3e50; }
.sous-titre { color: #3498db; }

/* Couleurs RGB */
.texte { color: rgb(44, 62, 80); }
.lien { color: rgba(52, 152, 219, 0.8); }

/* Couleurs HSL */
.accent { color: hsl(200, 70%, 50%); }
.transparent { color: hsla(200, 70%, 50%, 0.5); }
```

### Taille de police

```css
/* Tailles absolues */
.petit { font-size: 12px; }
.moyen { font-size: 16px; }
.grand { font-size: 24px; }

/* Tailles relatives */
.relatif { font-size: 1.2em; }
.responsive { font-size: 1.5rem; }

/* Tailles en pourcentage */
.pourcentage { font-size: 120%; }

/* Mots-clés */
.keyword { font-size: large; }
.autre { font-size: x-large; }
```

### Famille de polices

```css
/* Police système */
.serif { font-family: "Times New Roman", serif; }
.sans-serif { font-family: Arial, sans-serif; }
.monospace { font-family: "Courier New", monospace; }

/* Stack de polices */
.moderne {
    font-family: "Helvetica Neue", Arial, sans-serif;
}

/* Polices web sécurisées */
.web-safe {
    font-family: Georgia, "Times New Roman", serif;
}
```

### Poids de police

```css
/* Valeurs numériques */
.leger { font-weight: 100; }
.normal { font-weight: 400; }
.gras { font-weight: 700; }
.tres-gras { font-weight: 900; }

/* Mots-clés */
.bold { font-weight: bold; }
.bolder { font-weight: bolder; }
.lighter { font-weight: lighter; }
```

## 🎨 Styles de texte avancés

### Style et décoration

```css
/* Style de police */
.italique { font-style: italic; }
.oblique { font-style: oblique; }
.normal { font-style: normal; }

/* Décoration de texte */
.souligne { text-decoration: underline; }
.barre { text-decoration: line-through; }
.surligne { text-decoration: overline; }
.aucune { text-decoration: none; }

/* Décoration avancée */
.decoration-complexe {
    text-decoration: underline dotted red;
    text-underline-offset: 5px;
}
```

### Transformation de texte

```css
/* Transformation */
.majuscules { text-transform: uppercase; }
.minuscules { text-transform: lowercase; }
.capitalise { text-transform: capitalize; }
.normale { text-transform: none; }

/* Variantes de police */
.petites-caps { font-variant: small-caps; }
```

## 📏 Espacement et alignement

### Alignement du texte

```css
/* Alignement horizontal */
.gauche { text-align: left; }
.centre { text-align: center; }
.droite { text-align: right; }
.justifie { text-align: justify; }

/* Alignement vertical */
.valign-top { vertical-align: top; }
.valign-middle { vertical-align: middle; }
.valign-bottom { vertical-align: bottom; }
```

### Espacement des lettres et mots

```css
/* Espacement des lettres */
.espacement-lettres { letter-spacing: 2px; }
.condense { letter-spacing: -1px; }

/* Espacement des mots */
.espacement-mots { word-spacing: 5px; }
.mots-serres { word-spacing: -2px; }
```

### Hauteur de ligne

```css
/* Valeurs numériques */
.ligne-normale { line-height: 1.6; }
.ligne-large { line-height: 2; }

/* Valeurs absolues */
.ligne-pixels { line-height: 24px; }
.ligne-em { line-height: 1.5em; }

/* Pourcentages */
.ligne-pourcentage { line-height: 150%; }
```

## 🌐 Polices web et Google Fonts

### Polices système sécurisées

```css
/* Stack de polices robuste */
.police-systeme {
    font-family: 
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Roboto,
        sans-serif;
}
```

### Google Fonts

**HTML :**
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
```

**CSS :**
```css
body {
    font-family: 'Roboto', sans-serif;
}

.titre {
    font-family: 'Roboto', sans-serif;
    font-weight: 700;
}
```

### Polices personnalisées (@font-face)

```css
@font-face {
    font-family: 'MaPolice';
    src: url('fonts/mapolice.woff2') format('woff2'),
         url('fonts/mapolice.woff') format('woff');
    font-weight: normal;
    font-style: normal;
    font-display: swap;
}

.custom-font {
    font-family: 'MaPolice', Arial, sans-serif;
}
```

## 📐 Unités de mesure

### Unités absolues

```css
/* Pixels */
.pixels { font-size: 16px; }

/* Points (impression) */
.points { font-size: 12pt; }

/* Autres unités rares */
.cm { font-size: 1cm; }
.mm { font-size: 10mm; }
.in { font-size: 0.5in; }
```

### Unités relatives

```css
/* Em - relatif au parent */
.em-parent {
    font-size: 18px;
}
.em-enfant {
    font-size: 1.2em; /* 18px × 1.2 = 21.6px */
}

/* Rem - relatif à la racine */
html { font-size: 16px; }
.rem-element { font-size: 1.5rem; } /* 16px × 1.5 = 24px */

/* Pourcentages */
.pourcentage { font-size: 120%; }
```

### Unités viewport

```css
/* Viewport width/height */
.vw-titre { font-size: 5vw; }
.vh-titre { font-size: 8vh; }

/* Viewport min/max */
.vmin-titre { font-size: 4vmin; }
.vmax-titre { font-size: 3vmax; }
```

## 🎯 Gestion avancée du texte

### Contrôle du débordement

```css
/* Débordement de texte */
.ellipsis {
    width: 200px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

/* Césure des mots */
.break-word {
    word-break: break-word;
    overflow-wrap: break-word;
}

/* Coupure des mots */
.hyphens {
    hyphens: auto;
    -webkit-hyphens: auto;
}
```

### Espacement blanc

```css
/* Gestion des espaces */
.nowrap { white-space: nowrap; }
.pre { white-space: pre; }
.pre-wrap { white-space: pre-wrap; }
.pre-line { white-space: pre-line; }
```

### Indentation

```css
/* Indentation de paragraphe */
.indente {
    text-indent: 2em;
}

/* Indentation négative */
.hanging {
    text-indent: -2em;
    margin-left: 2em;
}
```

## 💻 Exemple pratique complet

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Typographie CSS</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Source+Sans+Pro:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1 class="titre-principal">L'Art de la Typographie</h1>
        <p class="sous-titre">Découvrez les secrets d'une belle mise en forme</p>
    </header>

    <main>
        <article>
            <h2 class="titre-section">Introduction</h2>
            <p class="introduction">
                La typographie est l'art de mettre en forme un texte pour le rendre lisible, 
                hiérarchisé et esthétiquement agréable.
            </p>
            
            <p class="paragraphe">
                Elle joue un rôle crucial dans l'expérience utilisateur et la perception 
                d'un site web. Une bonne typographie guide le lecteur et facilite la 
                compréhension du contenu.
            </p>

            <blockquote class="citation">
                « La typographie est l'art de disposer les caractères de manière à rendre 
                le langage visible. »
                <cite>— Ellen Lupton</cite>
            </blockquote>

            <h3 class="titre-subsection">Principes de base</h3>
            <ul class="liste-principes">
                <li>Hiérarchie visuelle</li>
                <li>Lisibilité optimale</li>
                <li>Cohérence stylistique</li>
                <li>Équilibre et espacement</li>
            </ul>
        </article>

        <aside class="sidebar">
            <h3 class="sidebar-titre">Conseils pratiques</h3>
            <p class="conseil">
                Limitez-vous à 2-3 polices maximum par projet pour maintenir la cohérence.
            </p>
            <p class="conseil">
                Utilisez des contrastes suffisants pour garantir l'accessibilité.
            </p>
        </aside>
    </main>
</body>
</html>
```

**CSS :**
```css
/* Variables CSS pour la typographie */
:root {
    --font-primary: 'Source Sans Pro', sans-serif;
    --font-heading: 'Playfair Display', serif;
    --font-size-base: 16px;
    --line-height-base: 1.6;
    --color-text: #333;
    --color-accent: #2c3e50;
    --color-muted: #7f8c8d;
}

/* Reset et base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: var(--font-primary);
    font-size: var(--font-size-base);
    line-height: var(--line-height-base);
    color: var(--color-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

/* Header */
header {
    text-align: center;
    margin-bottom: 3rem;
    padding: 2rem 0;
    border-bottom: 2px solid #ecf0f1;
}

.titre-principal {
    font-family: var(--font-heading);
    font-size: 3rem;
    font-weight: 700;
    color: var(--color-accent);
    margin-bottom: 1rem;
    letter-spacing: -1px;
}

.sous-titre {
    font-size: 1.25rem;
    color: var(--color-muted);
    font-weight: 300;
    font-style: italic;
    text-transform: uppercase;
    letter-spacing: 1px;
}

/* Main content */
main {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 3rem;
}

/* Article */
article {
    background: white;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.titre-section {
    font-family: var(--font-heading);
    font-size: 2.5rem;
    color: var(--color-accent);
    margin-bottom: 1.5rem;
    font-weight: 400;
}

.titre-subsection {
    font-family: var(--font-heading);
    font-size: 1.75rem;
    color: var(--color-accent);
    margin: 2rem 0 1rem 0;
    font-weight: 400;
}

.introduction {
    font-size: 1.125rem;
    font-weight: 600;
    color: var(--color-accent);
    margin-bottom: 1.5rem;
    line-height: 1.8;
}

.paragraphe {
    margin-bottom: 1.5rem;
    text-align: justify;
    text-indent: 1.5em;
}

.citation {
    font-family: var(--font-heading);
    font-size: 1.25rem;
    font-style: italic;
    color: var(--color-muted);
    margin: 2rem 0;
    padding: 1.5rem;
    background: #f8f9fa;
    border-left: 4px solid var(--color-accent);
    position: relative;
}

.citation::before {
    content: """;
    font-size: 4rem;
    color: var(--color-accent);
    position: absolute;
    top: -10px;
    left: 15px;
    opacity: 0.3;
}

.citation cite {
    display: block;
    text-align: right;
    margin-top: 1rem;
    font-size: 0.9rem;
    color: var(--color-text);
}

.liste-principes {
    list-style: none;
    padding-left: 0;
}

.liste-principes li {
    padding: 0.5rem 0;
    padding-left: 2rem;
    position: relative;
}

.liste-principes li::before {
    content: "▶";
    color: var(--color-accent);
    position: absolute;
    left: 0;
    top: 0.5rem;
}

/* Sidebar */
.sidebar {
    background: #f8f9fa;
    padding: 2rem;
    border-radius: 8px;
    height: fit-content;
}

.sidebar-titre {
    font-family: var(--font-heading);
    font-size: 1.5rem;
    color: var(--color-accent);
    margin-bottom: 1rem;
    text-align: center;
}

.conseil {
    background: white;
    padding: 1rem;
    margin-bottom: 1rem;
    border-radius: 5px;
    border-left: 3px solid var(--color-accent);
    font-size: 0.9rem;
    line-height: 1.5;
}

.conseil::before {
    content: "💡 ";
    margin-right: 0.5rem;
}

/* Responsive */
@media (max-width: 768px) {
    main {
        grid-template-columns: 1fr;
    }
    
    .titre-principal {
        font-size: 2rem;
    }
    
    body {
        padding: 1rem;
    }
    
    .paragraphe {
        text-indent: 0;
    }
}

/* Amélioration de l'accessibilité */
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}

/* Sélection de texte */
::selection {
    background: var(--color-accent);
    color: white;
}

/* Focus pour l'accessibilité */
:focus {
    outline: 2px solid var(--color-accent);
    outline-offset: 2px;
}
```

## ✅ Exercice pratique

1. Créez un article de blog avec :
   - Titre principal avec police décorative
   - Sous-titres hiérarchisés
   - Paragraphes avec bonne lisibilité
   - Citation mise en valeur
   - Liste stylisée

2. Utilisez :
   - Google Fonts
   - Différentes unités de mesure
   - Propriétés d'espacement
   - Pseudo-éléments pour la décoration

3. Testez la lisibilité sur différents écrans

## 🔍 Bonnes pratiques

- **Limitez le nombre de polices** (2-3 maximum)
- **Assurez-vous de la lisibilité** (contraste, taille)
- **Utilisez une hiérarchie claire** avec les tailles
- **Optimisez les performances** (font-display: swap)
- **Testez l'accessibilité** (lecteurs d'écran)

## 🔗 Ressources supplémentaires

- [Google Fonts](https://fonts.google.com/)
- [Type Scale](https://type-scale.com/)
- [Contrast Checker](https://webaim.org/resources/contrastchecker/)

---

**Temps estimé :** 3 heures  
**Prochaine étape :** [Module 4 - Couleurs et arrière-plans](../04-couleurs-arriere-plan/)