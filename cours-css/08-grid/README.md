# Module 8 : CSS Grid Layout

## 🎯 Objectifs du module

- Comprendre le concept de CSS Grid
- Maîtriser la création de grilles complexes
- Utiliser les propriétés du conteneur et des éléments
- Créer des layouts responsives avancés

## 📐 Introduction à CSS Grid

### Qu'est-ce que CSS Grid ?

CSS Grid est un système de layout bidimensionnel qui permet de :
- Créer des grilles complexes facilement
- Contrôler précisément les lignes et colonnes
- Superposer des éléments
- Créer des layouts responsives avancés

### Concepts de base

```css
/* Conteneur grid */
.grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: auto auto;
    gap: 1rem;
}

/* Élément grid */
.grid-item {
    grid-column: 1 / 3;
    grid-row: 1 / 2;
}
```

## 🏗️ Propriétés du conteneur grid

### Display

```css
/* Conteneur grid en bloc */
.grid-container {
    display: grid;
}

/* Conteneur grid en ligne */
.inline-grid {
    display: inline-grid;
}
```

### Grid-template-columns et grid-template-rows

```css
/* Colonnes fixes */
.grid-fixed {
    display: grid;
    grid-template-columns: 200px 300px 100px;
    grid-template-rows: 150px 200px;
}

/* Colonnes flexibles */
.grid-flexible {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
    grid-template-rows: auto 1fr auto;
}

/* Unités mixtes */
.grid-mixed {
    display: grid;
    grid-template-columns: 250px 1fr 20%;
    grid-template-rows: 100px auto minmax(200px, 1fr);
}

/* Repeat */
.grid-repeat {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 200px);
}

/* Auto-fit et auto-fill */
.grid-auto-fit {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}

.grid-auto-fill {
    display: grid;
    grid-template-columns: repeat(auto-fill, 200px);
}
```

### Grid-template-areas

```css
/* Layout nommé */
.grid-areas {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header header header"
        "sidebar main aside"
        "footer footer footer";
}

/* Éléments assignés aux zones */
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.aside { grid-area: aside; }
.footer { grid-area: footer; }
```

### Gap (espacement)

```css
/* Espacement uniforme */
.grid-gap {
    display: grid;
    gap: 20px;
}

/* Espacement différencié */
.grid-gap-custom {
    display: grid;
    row-gap: 30px;
    column-gap: 20px;
}

/* Ancienne syntaxe (compatibilité) */
.grid-gap-legacy {
    display: grid;
    grid-gap: 20px;
    grid-row-gap: 30px;
    grid-column-gap: 20px;
}
```

### Justify et align

```css
/* Alignement des éléments */
.grid-align {
    display: grid;
    justify-items: center;    /* Horizontal */
    align-items: center;      /* Vertical */
}

/* Alignement du contenu */
.grid-content {
    display: grid;
    justify-content: center;  /* Grille horizontalement */
    align-content: center;    /* Grille verticalement */
}

/* Valeurs possibles */
.grid-values {
    justify-items: start | end | center | stretch;
    align-items: start | end | center | stretch;
    justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
    align-content: start | end | center | stretch | space-around | space-between | space-evenly;
}
```

## 🎨 Propriétés des éléments grid

### Grid-column et grid-row

```css
/* Position par numéro de ligne */
.item-position {
    grid-column: 1 / 3;     /* Colonne 1 à 3 */
    grid-row: 2 / 4;        /* Ligne 2 à 4 */
}

/* Avec span */
.item-span {
    grid-column: 2 / span 2;  /* Commence à la colonne 2, s'étend sur 2 */
    grid-row: span 3;         /* S'étend sur 3 lignes */
}

/* Propriétés individuelles */
.item-individual {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: span 2;
}
```

### Grid-area

```css
/* Zone nommée */
.item-named {
    grid-area: header;
}

/* Position complète */
.item-complete {
    grid-area: 1 / 2 / 3 / 4;
    /* row-start / column-start / row-end / column-end */
}
```

### Justify-self et align-self

```css
/* Alignement individuel */
.item-align {
    justify-self: center;   /* Horizontal */
    align-self: end;        /* Vertical */
}

/* Raccourci place-self */
.item-place {
    place-self: center end; /* align-self justify-self */
}
```

## 🎯 Techniques avancées

### Grilles imbriquées (Subgrid)

```css
/* Grille parente */
.parent-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, 1fr);
}

/* Grille enfant (subgrid - support limité) */
.child-grid {
    display: grid;
    grid-column: 2 / 4;
    grid-row: 1 / 3;
    grid-template-columns: subgrid;
    grid-template-rows: subgrid;
}

/* Alternative avec grid imbriqué */
.nested-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
}
```

### Auto-placement

```css
/* Contrôle du placement automatique */
.auto-placement {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-flow: row;        /* row (défaut) | column | row dense | column dense */
    grid-auto-rows: 200px;      /* Taille des lignes auto-générées */
    grid-auto-columns: 150px;   /* Taille des colonnes auto-générées */
}
```

### Superposition d'éléments

```css
/* Éléments qui se chevauchent */
.overlay-grid {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
}

.overlay-item {
    grid-column: 1;
    grid-row: 1;
    z-index: 1;
}

.background-item {
    grid-column: 1;
    grid-row: 1;
    z-index: 0;
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
    <title>CSS Grid - Layout avancé</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Layout principal avec Grid -->
    <div class="page-grid">
        <header class="header">
            <div class="header-content">
                <h1>CSS Grid Mastery</h1>
                <nav class="nav">
                    <a href="#basics">Bases</a>
                    <a href="#advanced">Avancé</a>
                    <a href="#examples">Exemples</a>
                </nav>
            </div>
        </header>

        <aside class="sidebar">
            <h3>Navigation</h3>
            <ul class="sidebar-menu">
                <li><a href="#grid-container">Conteneur Grid</a></li>
                <li><a href="#grid-items">Éléments Grid</a></li>
                <li><a href="#responsive">Responsive</a></li>
                <li><a href="#patterns">Patterns</a></li>
            </ul>
            
            <div class="sidebar-widget">
                <h4>Astuce</h4>
                <p>Utilisez Firefox DevTools pour visualiser vos grilles CSS !</p>
            </div>
        </aside>

        <main class="main-content">
            <!-- Section démonstration de base -->
            <section id="basics" class="section">
                <h2>Démonstrations Grid</h2>
                
                <!-- Grille simple -->
                <div class="demo-container">
                    <h3>Grille simple 3x3</h3>
                    <div class="demo-grid basic-grid">
                        <div class="demo-item">1</div>
                        <div class="demo-item">2</div>
                        <div class="demo-item">3</div>
                        <div class="demo-item">4</div>
                        <div class="demo-item">5</div>
                        <div class="demo-item">6</div>
                        <div class="demo-item">7</div>
                        <div class="demo-item">8</div>
                        <div class="demo-item">9</div>
                    </div>
                </div>

                <!-- Grille avec areas -->
                <div class="demo-container">
                    <h3>Layout avec grid-template-areas</h3>
                    <div class="demo-grid areas-grid">
                        <div class="demo-header">Header</div>
                        <div class="demo-nav">Nav</div>
                        <div class="demo-main">Main Content</div>
                        <div class="demo-aside">Aside</div>
                        <div class="demo-footer">Footer</div>
                    </div>
                </div>

                <!-- Grille responsive -->
                <div class="demo-container">
                    <h3>Grille responsive (auto-fit)</h3>
                    <div class="demo-grid responsive-grid">
                        <div class="demo-card">
                            <h4>Card 1</h4>
                            <p>Contenu de la première carte</p>
                        </div>
                        <div class="demo-card">
                            <h4>Card 2</h4>
                            <p>Contenu de la deuxième carte</p>
                        </div>
                        <div class="demo-card">
                            <h4>Card 3</h4>
                            <p>Contenu de la troisième carte</p>
                        </div>
                        <div class="demo-card">
                            <h4>Card 4</h4>
                            <p>Contenu de la quatrième carte</p>
                        </div>
                        <div class="demo-card">
                            <h4>Card 5</h4>
                            <p>Contenu de la cinquième carte</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Section avancée -->
            <section id="advanced" class="section">
                <h2>Techniques avancées</h2>
                
                <!-- Superposition -->
                <div class="demo-container">
                    <h3>Superposition d'éléments</h3>
                    <div class="overlay-demo">
                        <div class="overlay-background">
                            <img src="https://picsum.photos/400/300" alt="Image de fond">
                        </div>
                        <div class="overlay-content">
                            <h4>Contenu superposé</h4>
                            <p>Ce texte est au-dessus de l'image</p>
                            <button class="btn">Action</button>
                        </div>
                    </div>
                </div>

                <!-- Grille complexe -->
                <div class="demo-container">
                    <h3>Layout complexe</h3>
                    <div class="complex-grid">
                        <div class="featured-item">
                            <h4>Article principal</h4>
                            <p>Cet article occupe plus d'espace dans la grille</p>
                        </div>
                        <div class="regular-item">Article 1</div>
                        <div class="regular-item">Article 2</div>
                        <div class="regular-item">Article 3</div>
                        <div class="regular-item">Article 4</div>
                        <div class="wide-item">
                            <h4>Article large</h4>
                            <p>Cet article s'étend sur plusieurs colonnes</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Section exemples pratiques -->
            <section id="examples" class="section">
                <h2>Exemples pratiques</h2>
                
                <!-- Galerie d'images -->
                <div class="demo-container">
                    <h3>Galerie d'images responsive</h3>
                    <div class="gallery-grid">
                        <div class="gallery-item large">
                            <img src="https://picsum.photos/400/600" alt="Image 1">
                        </div>
                        <div class="gallery-item">
                            <img src="https://picsum.photos/400/400" alt="Image 2">
                        </div>
                        <div class="gallery-item">
                            <img src="https://picsum.photos/400/400" alt="Image 3">
                        </div>
                        <div class="gallery-item wide">
                            <img src="https://picsum.photos/800/400" alt="Image 4">
                        </div>
                        <div class="gallery-item">
                            <img src="https://picsum.photos/400/400" alt="Image 5">
                        </div>
                        <div class="gallery-item">
                            <img src="https://picsum.photos/400/400" alt="Image 6">
                        </div>
                    </div>
                </div>

                <!-- Dashboard */
                <div class="demo-container">
                    <h3>Dashboard layout</h3>
                    <div class="dashboard-grid">
                        <div class="dashboard-item stats">
                            <h4>Statistiques</h4>
                            <div class="stats-row">
                                <span>Visiteurs: 1,234</span>
                                <span>Ventes: 567€</span>
                            </div>
                        </div>
                        <div class="dashboard-item chart">
                            <h4>Graphique</h4>
                            <div class="fake-chart"></div>
                        </div>
                        <div class="dashboard-item recent">
                            <h4>Activité récente</h4>
                            <ul>
                                <li>Nouvelle commande</li>
                                <li>Utilisateur inscrit</li>
                                <li>Message reçu</li>
                            </ul>
                        </div>
                        <div class="dashboard-item tasks">
                            <h4>Tâches</h4>
                            <ul>
                                <li>✓ Répondre aux emails</li>
                                <li>○ Préparer présentation</li>
                                <li>○ Mettre à jour site</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>
        </main>

        <footer class="footer">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>CSS Grid</h4>
                    <p>Layout bidimensionnel puissant</p>
                </div>
                <div class="footer-section">
                    <h4>Ressources</h4>
                    <ul>
                        <li><a href="#">MDN Grid</a></li>
                        <li><a href="#">Grid Garden</a></li>
                        <li><a href="#">CSS Grid Generator</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2024 CSS Grid Mastery</p>
            </div>
        </footer>
    </div>

    <!-- Contrôles interactifs -->
    <div class="controls-panel">
        <h4>Contrôles Grid</h4>
        <div class="control-group">
            <label>Colonnes:</label>
            <button onclick="changeColumns('repeat(2, 1fr)')">2 cols</button>
            <button onclick="changeColumns('repeat(3, 1fr)')">3 cols</button>
            <button onclick="changeColumns('repeat(4, 1fr)')">4 cols</button>
        </div>
        <div class="control-group">
            <label>Gap:</label>
            <button onclick="changeGap('10px')">10px</button>
            <button onclick="changeGap('20px')">20px</button>
            <button onclick="changeGap('30px')">30px</button>
        </div>
    </div>

    <script>
        function changeColumns(value) {
            document.querySelector('.responsive-grid').style.gridTemplateColumns = value;
        }
        
        function changeGap(value) {
            document.querySelector('.responsive-grid').style.gap = value;
        }
    </script>
</body>
</html>
```

**CSS :**
```css
/* Variables et reset */
:root {
    --primary: #667eea;
    --secondary: #764ba2;
    --accent: #f093fb;
    --text: #333;
    --text-light: #666;
    --background: #f8f9fa;
    --white: #ffffff;
    --border: #e9ecef;
    --shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    --gradient: linear-gradient(135deg, var(--primary), var(--secondary));
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: var(--text);
    background: var(--background);
}

/* Layout principal avec CSS Grid */
.page-grid {
    display: grid;
    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
    grid-template-columns: 280px 1fr;
    grid-template-rows: auto 1fr auto;
    min-height: 100vh;
    gap: 0;
}

/* Header */
.header {
    grid-area: header;
    background: var(--gradient);
    color: white;
    box-shadow: var(--shadow);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.header-content {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: center;
    padding: 1rem 2rem;
    max-width: 1400px;
    margin: 0 auto;
}

.header h1 {
    font-size: 1.8rem;
    font-weight: 700;
}

.nav {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
}

.nav a {
    color: white;
    text-decoration: none;
    font-weight: 500;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    transition: background 0.3s;
    text-align: center;
}

.nav a:hover {
    background: rgba(255, 255, 255, 0.2);
}

/* Sidebar */
.sidebar {
    grid-area: sidebar;
    background: var(--white);
    padding: 2rem;
    border-right: 1px solid var(--border);
    overflow-y: auto;
    height: calc(100vh - 80px);
    position: sticky;
    top: 80px;
}

.sidebar h3 {
    color: var(--primary);
    margin-bottom: 1rem;
    font-size: 1.3rem;
}

.sidebar-menu {
    list-style: none;
    margin-bottom: 2rem;
}

.sidebar-menu li {
    margin-bottom: 0.5rem;
}

.sidebar-menu a {
    color: var(--text-light);
    text-decoration: none;
    padding: 0.5rem 0;
    display: block;
    border-radius: 5px;
    transition: all 0.3s;
}

.sidebar-menu a:hover {
    color: var(--primary);
    padding-left: 1rem;
}

.sidebar-widget {
    background: var(--gradient);
    color: white;
    padding: 1.5rem;
    border-radius: 10px;
    margin-top: 2rem;
}

.sidebar-widget h4 {
    margin-bottom: 0.5rem;
}

/* Contenu principal */
.main-content {
    grid-area: main;
    padding: 2rem;
    overflow-x: hidden;
}

.section {
    background: var(--white);
    margin-bottom: 2rem;
    padding: 2rem;
    border-radius: 15px;
    box-shadow: var(--shadow);
}

.section h2 {
    color: var(--primary);
    font-size: 2.2rem;
    margin-bottom: 2rem;
    text-align: center;
}

/* Conteneurs de démonstration */
.demo-container {
    margin-bottom: 3rem;
}

.demo-container h3 {
    color: var(--secondary);
    margin-bottom: 1rem;
    font-size: 1.4rem;
}

/* Grilles de démonstration */
.demo-grid {
    border: 2px solid var(--border);
    border-radius: 10px;
    padding: 1rem;
    background: var(--background);
}

/* Grille de base 3x3 */
.basic-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 80px);
    gap: 10px;
}

.demo-item {
    background: var(--gradient);
    color: white;
    display: grid;
    place-items: center;
    border-radius: 8px;
    font-weight: bold;
    font-size: 1.2rem;
}

/* Grille avec areas */
.areas-grid {
    display: grid;
    grid-template-columns: 200px 1fr 150px;
    grid-template-rows: 60px 200px 50px;
    grid-template-areas:
        "header header header"
        "nav main aside"
        "footer footer footer";
    gap: 10px;
}

.demo-header {
    grid-area: header;
    background: var(--primary);
    color: white;
    display: grid;
    place-items: center;
    border-radius: 8px;
    font-weight: bold;
}

.demo-nav {
    grid-area: nav;
    background: var(--secondary);
    color: white;
    display: grid;
    place-items: center;
    border-radius: 8px;
    font-weight: bold;
}

.demo-main {
    grid-area: main;
    background: var(--accent);
    color: white;
    display: grid;
    place-items: center;
    border-radius: 8px;
    font-weight: bold;
}

.demo-aside {
    grid-area: aside;
    background: #4ecdc4;
    color: white;
    display: grid;
    place-items: center;
    border-radius: 8px;
    font-weight: bold;
}

.demo-footer {
    grid-area: footer;
    background: #95a5a6;
    color: white;
    display: grid;
    place-items: center;
    border-radius: 8px;
    font-weight: bold;
}

/* Grille responsive */
.responsive-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

.demo-card {
    background: var(--white);
    padding: 1.5rem;
    border-radius: 10px;
    box-shadow: var(--shadow);
    border: 1px solid var(--border);
}

.demo-card h4 {
    color: var(--primary);
    margin-bottom: 0.5rem;
}

/* Superposition */
.overlay-demo {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
    height: 300px;
    border-radius: 15px;
    overflow: hidden;
}

.overlay-background {
    grid-column: 1;
    grid-row: 1;
    z-index: 1;
}

.overlay-background img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.overlay-content {
    grid-column: 1;
    grid-row: 1;
    z-index: 2;
    background: rgba(0, 0, 0, 0.7);
    color: white;
    display: grid;
    place-items: center;
    text-align: center;
    padding: 2rem;
}

.overlay-content h4 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
}

.btn {
    background: var(--gradient);
    color: white;
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 25px;
    cursor: pointer;
    font-weight: 500;
    transition: transform 0.3s;
}

.btn:hover {
    transform: translateY(-2px);
}

/* Grille complexe */
.complex-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: 150px;
    gap: 15px;
}

.featured-item {
    grid-column: span 2;
    grid-row: span 2;
    background: var(--gradient);
    color: white;
    padding: 2rem;
    border-radius: 15px;
    display: grid;
    place-content: center;
    text-align: center;
}

.regular-item {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: 10px;
    display: grid;
    place-items: center;
    font-weight: 500;
    box-shadow: var(--shadow);
}

.wide-item {
    grid-column: span 2;
    background: var(--accent);
    color: white;
    padding: 1.5rem;
    border-radius: 10px;
    display: grid;
    place-content: center;
    text-align: center;
}

/* Galerie */
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-auto-rows: 200px;
    gap: 15px;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
}

.gallery-item.large {
    grid-row: span 2;
}

.gallery-item.wide {
    grid-column: span 2;
}

/* Dashboard */
.dashboard-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    grid-auto-rows: minmax(200px, auto);
    gap: 20px;
}

.dashboard-item {
    background: var(--white);
    padding: 1.5rem;
    border-radius: 15px;
    box-shadow: var(--shadow);
    border: 1px solid var(--border);
}

.dashboard-item h4 {
    color: var(--primary);
    margin-bottom: 1rem;
    font-size: 1.2rem;
}

.stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    margin-top: 1rem;
}

.stats-row span {
    background: var(--background);
    padding: 0.5rem;
    border-radius: 5px;
    text-align: center;
    font-weight: 500;
}

.fake-chart {
    height: 120px;
    background: var(--gradient);
    border-radius: 10px;
    position: relative;
    overflow: hidden;
}

.fake-chart::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 60%;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 10px 10px 0 0;
}

.dashboard-item ul {
    list-style: none;
}

.dashboard-item li {
    padding: 0.5rem 0;
    border-bottom: 1px solid var(--border);
}

.dashboard-item li:last-child {
    border-bottom: none;
}

/* Footer */
.footer {
    grid-area: footer;
    background: var(--secondary);
    color: white;
    padding: 2rem;
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    max-width: 1400px;
    margin: 0 auto;
}

.footer-section h4 {
    margin-bottom: 1rem;
    color: white;
}

.footer-section ul {
    list-style: none;
}

.footer-section li {
    margin-bottom: 0.5rem;
}

.footer-section a {
    color: rgba(255, 255, 255, 0.8);
    text-decoration: none;
    transition: color 0.3s;
}

.footer-section a:hover {
    color: white;
}

.footer-bottom {
    text-align: center;
    margin-top: 2rem;
    padding-top: 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.2);
    color: rgba(255, 255, 255, 0.8);
}

/* Panneau de contrôles */
.controls-panel {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    background: var(--white);
    padding: 1.5rem;
    border-radius: 15px;
    box-shadow: var(--shadow);
    border: 1px solid var(--border);
    z-index: 1000;
}

.controls-panel h4 {
    color: var(--primary);
    margin-bottom: 1rem;
    text-align: center;
}

.control-group {
    margin-bottom: 1rem;
}

.control-group label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: var(--text);
}

.control-group button {
    background: var(--background);
    border: 1px solid var(--border);
    padding: 0.5rem 1rem;
    margin-right: 0.5rem;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s;
    font-size: 0.9rem;
}

.control-group button:hover {
    background: var(--primary);
    color: white;
}

/* Responsive */
@media (max-width: 1024px) {
    .page-grid {
        grid-template-areas:
            "header"
            "main"
            "footer";
        grid-template-columns: 1fr;
    }
    
    .sidebar {
        display: none;
    }
    
    .header-content {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 1rem;
    }
    
    .nav {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media (max-width: 768px) {
    .main-content {
        padding: 1rem;
    }
    
    .section {
        padding: 1.5rem;
    }
    
    .areas-grid {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "nav"
            "main"
            "aside"
            "footer";
    }
    
    .complex-grid {
        grid-template-columns: repeat(2, 1fr);
    }
    
    .featured-item {
        grid-column: span 2;
        grid-row: span 1;
    }
    
    .wide-item {
        grid-column: span 2;
    }
    
    .controls-panel {
        position: static;
        margin: 2rem 1rem;
    }
    
    .nav {
        grid-template-columns: 1fr;
        gap: 0.5rem;
    }
}

@media (max-width: 480px) {
    .complex-grid {
        grid-template-columns: 1fr;
    }
    
    .featured-item,
    .wide-item {
        grid-column: 1;
    }
    
    .gallery-grid {
        grid-template-columns: 1fr;
    }
    
    .gallery-item.wide,
    .gallery-item.large {
        grid-column: 1;
        grid-row: span 1;
    }
}

/* Animations */
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.section {
    animation: fadeInUp 0.6s ease-out;
}

/* États de focus */
button:focus,
a:focus {
    outline: 2px solid var(--primary);
    outline-offset: 2px;
}

/* Mode sombre */
@media (prefers-color-scheme: dark) {
    :root {
        --text: #e0e0e0;
        --text-light: #b0b0b0;
        --background: #1a1a1a;
        --white: #2d2d2d;
        --border: #404040;
    }
}

/* Préférences de mouvement */
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}
```

## ✅ Exercice pratique

1. Créez un layout complet avec :
   - Header, sidebar, main, footer avec grid-template-areas
   - Grille responsive de cartes
   - Galerie d'images avec éléments de tailles différentes
   - Dashboard avec widgets

2. Implémentez :
   - Superposition d'éléments
   - Grilles imbriquées
   - Auto-placement intelligent
   - Contrôles interactifs

3. Optimisez pour :
   - Responsive design
   - Performance
   - Accessibilité

## 🔍 Bonnes pratiques

- **Utilisez Grid** pour les layouts 2D complexes
- **Combinez avec Flexbox** pour les détails
- **Nommez vos zones** avec grid-template-areas
- **Utilisez minmax()** pour la flexibilité
- **Testez sur différents écrans**

## 🔗 Ressources supplémentaires

- [CSS Grid Garden](https://cssgridgarden.com/)
- [Grid by Example](https://gridbyexample.com/)
- [CSS Grid Generator](https://css-grid-generator.netlify.app/)
- [MDN CSS Grid](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Grid_Layout)

---

**Temps estimé :** 4.5 heures  
**Prochaine étape :** [Module 9 - Design responsive](../09-responsive/)