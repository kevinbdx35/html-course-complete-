# Module 7 : Flexbox - Layout flexible

## 🎯 Objectifs du module

- Comprendre le concept de Flexbox
- Maîtriser les propriétés du conteneur flex
- Utiliser les propriétés des éléments flex
- Créer des layouts responsives avec Flexbox

## 📐 Introduction à Flexbox

### Qu'est-ce que Flexbox ?

Flexbox (Flexible Box Layout) est un système de layout CSS qui permet de :
- Aligner facilement les éléments
- Distribuer l'espace disponible
- Créer des layouts responsives
- Gérer l'ordre des éléments

### Concepts de base

```css
/* Conteneur flex */
.flex-container {
    display: flex;
}

/* Éléments flex */
.flex-item {
    /* Propriétés automatiques */
    flex: 1; /* Grandit pour remplir l'espace */
}
```

## 🏗️ Propriétés du conteneur flex

### Display

```css
/* Conteneur flex en bloc */
.flex-container {
    display: flex;
}

/* Conteneur flex en ligne */
.inline-flex {
    display: inline-flex;
}
```

### Flex-direction

```css
/* Direction horizontale (défaut) */
.flex-row {
    display: flex;
    flex-direction: row;
}

/* Direction horizontale inversée */
.flex-row-reverse {
    display: flex;
    flex-direction: row-reverse;
}

/* Direction verticale */
.flex-column {
    display: flex;
    flex-direction: column;
}

/* Direction verticale inversée */
.flex-column-reverse {
    display: flex;
    flex-direction: column-reverse;
}
```

### Flex-wrap

```css
/* Pas de retour à la ligne (défaut) */
.no-wrap {
    display: flex;
    flex-wrap: nowrap;
}

/* Retour à la ligne */
.wrap {
    display: flex;
    flex-wrap: wrap;
}

/* Retour à la ligne inversé */
.wrap-reverse {
    display: flex;
    flex-wrap: wrap-reverse;
}

/* Raccourci flex-flow */
.flex-flow {
    display: flex;
    flex-flow: row wrap; /* direction + wrap */
}
```

### Justify-content (axe principal)

```css
/* Alignement au début (défaut) */
.justify-start {
    display: flex;
    justify-content: flex-start;
}

/* Alignement à la fin */
.justify-end {
    display: flex;
    justify-content: flex-end;
}

/* Alignement centré */
.justify-center {
    display: flex;
    justify-content: center;
}

/* Espacement égal entre les éléments */
.justify-between {
    display: flex;
    justify-content: space-between;
}

/* Espacement égal autour des éléments */
.justify-around {
    display: flex;
    justify-content: space-around;
}

/* Espacement égal partout */
.justify-evenly {
    display: flex;
    justify-content: space-evenly;
}
```

### Align-items (axe transversal)

```css
/* Étirement (défaut) */
.align-stretch {
    display: flex;
    align-items: stretch;
}

/* Alignement au début */
.align-start {
    display: flex;
    align-items: flex-start;
}

/* Alignement à la fin */
.align-end {
    display: flex;
    align-items: flex-end;
}

/* Alignement centré */
.align-center {
    display: flex;
    align-items: center;
}

/* Alignement sur la baseline */
.align-baseline {
    display: flex;
    align-items: baseline;
}
```

### Align-content (lignes multiples)

```css
/* Pour les conteneurs avec wrap */
.align-content-center {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}

.align-content-between {
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
}

.align-content-around {
    display: flex;
    flex-wrap: wrap;
    align-content: space-around;
}
```

## 🎨 Propriétés des éléments flex

### Flex-grow

```css
/* Facteur de croissance */
.flex-item {
    flex-grow: 1; /* Prend l'espace disponible */
}

.flex-item-2x {
    flex-grow: 2; /* Prend 2x plus d'espace */
}

.flex-item-no-grow {
    flex-grow: 0; /* Ne grandit pas */
}
```

### Flex-shrink

```css
/* Facteur de rétrécissement */
.flex-item {
    flex-shrink: 1; /* Peut rétrécir (défaut) */
}

.flex-item-no-shrink {
    flex-shrink: 0; /* Ne rétrécit pas */
}

.flex-item-shrink-2x {
    flex-shrink: 2; /* Rétrécit 2x plus */
}
```

### Flex-basis

```css
/* Taille de base */
.flex-item {
    flex-basis: 200px; /* Taille initiale */
}

.flex-item-auto {
    flex-basis: auto; /* Basé sur le contenu */
}

.flex-item-percentage {
    flex-basis: 33.333%; /* En pourcentage */
}
```

### Flex (raccourci)

```css
/* Raccourci flex: grow shrink basis */
.flex-1 {
    flex: 1; /* flex: 1 1 0% */
}

.flex-auto {
    flex: auto; /* flex: 1 1 auto */
}

.flex-none {
    flex: none; /* flex: 0 0 auto */
}

.flex-custom {
    flex: 2 1 200px; /* grow: 2, shrink: 1, basis: 200px */
}
```

### Align-self

```css
/* Alignement individuel */
.flex-item-start {
    align-self: flex-start;
}

.flex-item-center {
    align-self: center;
}

.flex-item-end {
    align-self: flex-end;
}

.flex-item-stretch {
    align-self: stretch;
}
```

### Order

```css
/* Ordre d'affichage */
.first {
    order: -1; /* Affiché en premier */
}

.last {
    order: 1; /* Affiché en dernier */
}

.middle {
    order: 0; /* Ordre normal (défaut) */
}
```

## 🎯 Patterns courants avec Flexbox

### Centrage parfait

```css
.center-perfect {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
```

### Navigation horizontale

```css
.nav-horizontal {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
}

.nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
}
```

### Cartes flexibles

```css
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}

.card {
    flex: 1 1 300px; /* Grandit, rétrécit, base 300px */
    min-width: 0; /* Évite le débordement */
}
```

### Layout sidebar

```css
.layout {
    display: flex;
    min-height: 100vh;
}

.sidebar {
    flex: 0 0 250px; /* Largeur fixe */
}

.main-content {
    flex: 1; /* Prend le reste */
}
```

### Footer collant

```css
.page {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

.header, .footer {
    flex: none; /* Taille basée sur le contenu */
}

.main {
    flex: 1; /* Prend l'espace restant */
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
    <title>Flexbox - Layout moderne</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="page">
        <!-- Header avec navigation flex -->
        <header class="header">
            <div class="container">
                <nav class="nav">
                    <div class="nav-brand">
                        <h1>FlexSite</h1>
                    </div>
                    <ul class="nav-links">
                        <li><a href="#home">Accueil</a></li>
                        <li><a href="#about">À propos</a></li>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                    <div class="nav-actions">
                        <button class="btn btn-primary">Connexion</button>
                    </div>
                </nav>
            </div>
        </header>

        <!-- Contenu principal -->
        <main class="main">
            <div class="container">
                <!-- Section hero avec centrage parfait -->
                <section class="hero">
                    <div class="hero-content">
                        <h2>Maîtrisez Flexbox</h2>
                        <p>Créez des layouts modernes et responsives facilement</p>
                        <div class="hero-actions">
                            <button class="btn btn-primary">Commencer</button>
                            <button class="btn btn-secondary">En savoir plus</button>
                        </div>
                    </div>
                </section>

                <!-- Démonstration des propriétés -->
                <section class="demo-section">
                    <h2>Démonstrations Flexbox</h2>
                    
                    <!-- Justify-content -->
                    <div class="demo-container">
                        <h3>justify-content</h3>
                        <div class="demo-controls">
                            <button onclick="changeJustify('flex-start')">flex-start</button>
                            <button onclick="changeJustify('center')">center</button>
                            <button onclick="changeJustify('flex-end')">flex-end</button>
                            <button onclick="changeJustify('space-between')">space-between</button>
                            <button onclick="changeJustify('space-around')">space-around</button>
                            <button onclick="changeJustify('space-evenly')">space-evenly</button>
                        </div>
                        <div class="demo-flex" id="justify-demo">
                            <div class="demo-item">1</div>
                            <div class="demo-item">2</div>
                            <div class="demo-item">3</div>
                        </div>
                    </div>

                    <!-- Align-items -->
                    <div class="demo-container">
                        <h3>align-items</h3>
                        <div class="demo-controls">
                            <button onclick="changeAlign('stretch')">stretch</button>
                            <button onclick="changeAlign('flex-start')">flex-start</button>
                            <button onclick="changeAlign('center')">center</button>
                            <button onclick="changeAlign('flex-end')">flex-end</button>
                            <button onclick="changeAlign('baseline')">baseline</button>
                        </div>
                        <div class="demo-flex tall" id="align-demo">
                            <div class="demo-item">1</div>
                            <div class="demo-item large">2</div>
                            <div class="demo-item">3</div>
                        </div>
                    </div>

                    <!-- Flex-direction -->
                    <div class="demo-container">
                        <h3>flex-direction</h3>
                        <div class="demo-controls">
                            <button onclick="changeDirection('row')">row</button>
                            <button onclick="changeDirection('row-reverse')">row-reverse</button>
                            <button onclick="changeDirection('column')">column</button>
                            <button onclick="changeDirection('column-reverse')">column-reverse</button>
                        </div>
                        <div class="demo-flex" id="direction-demo">
                            <div class="demo-item">1</div>
                            <div class="demo-item">2</div>
                            <div class="demo-item">3</div>
                        </div>
                    </div>
                </section>

                <!-- Grille de cartes responsives -->
                <section class="cards-section">
                    <h2>Cartes flexibles</h2>
                    <div class="cards-container">
                        <div class="card">
                            <div class="card-header">
                                <h3>Flex-grow</h3>
                            </div>
                            <div class="card-body">
                                <p>Contrôle la croissance des éléments flex pour remplir l'espace disponible.</p>
                            </div>
                            <div class="card-footer">
                                <button class="btn btn-outline">Apprendre</button>
                            </div>
                        </div>
                        <div class="card">
                            <div class="card-header">
                                <h3>Flex-shrink</h3>
                            </div>
                            <div class="card-body">
                                <p>Détermine comment les éléments rétrécissent quand l'espace est insuffisant.</p>
                            </div>
                            <div class="card-footer">
                                <button class="btn btn-outline">Apprendre</button>
                            </div>
                        </div>
                        <div class="card">
                            <div class="card-header">
                                <h3>Flex-basis</h3>
                            </div>
                            <div class="card-body">
                                <p>Définit la taille de base d'un élément avant la distribution de l'espace.</p>
                            </div>
                            <div class="card-footer">
                                <button class="btn btn-outline">Apprendre</button>
                            </div>
                        </div>
                        <div class="card">
                            <div class="card-header">
                                <h3>Align-self</h3>
                            </div>
                            <div class="card-body">
                                <p>Permet l'alignement individuel d'un élément flex.</p>
                            </div>
                            <div class="card-footer">
                                <button class="btn btn-outline">Apprendre</button>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Layout avec sidebar -->
                <section class="layout-section">
                    <h2>Layout avec sidebar</h2>
                    <div class="layout-demo">
                        <aside class="sidebar">
                            <h3>Sidebar</h3>
                            <ul class="sidebar-menu">
                                <li><a href="#">Accueil</a></li>
                                <li><a href="#">Profil</a></li>
                                <li><a href="#">Paramètres</a></li>
                                <li><a href="#">Aide</a></li>
                            </ul>
                        </aside>
                        <div class="content">
                            <h3>Contenu principal</h3>
                            <p>Cette zone prend tout l'espace restant grâce à <code>flex: 1</code>.</p>
                            <p>Le layout s'adapte automatiquement à la largeur de la sidebar.</p>
                        </div>
                    </div>
                </section>
            </div>
        </main>

        <!-- Footer -->
        <footer class="footer">
            <div class="container">
                <div class="footer-content">
                    <div class="footer-section">
                        <h4>À propos</h4>
                        <p>Apprenez Flexbox avec des exemples pratiques.</p>
                    </div>
                    <div class="footer-section">
                        <h4>Liens rapides</h4>
                        <ul>
                            <li><a href="#">Documentation</a></li>
                            <li><a href="#">Exercices</a></li>
                            <li><a href="#">Ressources</a></li>
                        </ul>
                    </div>
                    <div class="footer-section">
                        <h4>Contact</h4>
                        <p>contact@flexsite.com</p>
                    </div>
                </div>
                <div class="footer-bottom">
                    <p>&copy; 2024 FlexSite. Tous droits réservés.</p>
                </div>
            </div>
        </footer>
    </div>

    <script>
        function changeJustify(value) {
            document.getElementById('justify-demo').style.justifyContent = value;
        }
        
        function changeAlign(value) {
            document.getElementById('align-demo').style.alignItems = value;
        }
        
        function changeDirection(value) {
            document.getElementById('direction-demo').style.flexDirection = value;
        }
    </script>
</body>
</html>
```

**CSS :**
```css
/* Reset et variables */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --primary-color: #3498db;
    --secondary-color: #2c3e50;
    --success-color: #2ecc71;
    --background-color: #f8f9fa;
    --text-color: #333;
    --border-color: #e9ecef;
    --shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: var(--text-color);
    background: var(--background-color);
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
}

/* Layout principal avec flexbox */
.page {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

/* Header */
.header {
    background: white;
    box-shadow: var(--shadow);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 0;
}

.nav-brand h1 {
    color: var(--primary-color);
    font-size: 1.5rem;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-links a {
    color: var(--text-color);
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s;
}

.nav-links a:hover {
    color: var(--primary-color);
}

.nav-actions {
    display: flex;
    gap: 1rem;
}

/* Main content */
.main {
    flex: 1;
    padding: 2rem 0;
}

/* Hero section */
.hero {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 60vh;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    text-align: center;
    border-radius: 15px;
    margin-bottom: 3rem;
}

.hero-content h2 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.hero-content p {
    font-size: 1.2rem;
    margin-bottom: 2rem;
    opacity: 0.9;
}

.hero-actions {
    display: flex;
    justify-content: center;
    gap: 1rem;
    flex-wrap: wrap;
}

/* Boutons */
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 0.75rem 1.5rem;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    font-weight: 500;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s;
}

.btn-primary {
    background: var(--primary-color);
    color: white;
}

.btn-primary:hover {
    background: #2980b9;
    transform: translateY(-2px);
}

.btn-secondary {
    background: transparent;
    color: white;
    border: 2px solid white;
}

.btn-secondary:hover {
    background: white;
    color: var(--primary-color);
}

.btn-outline {
    background: transparent;
    color: var(--primary-color);
    border: 2px solid var(--primary-color);
}

.btn-outline:hover {
    background: var(--primary-color);
    color: white;
}

/* Sections de démonstration */
.demo-section {
    background: white;
    padding: 3rem 2rem;
    margin-bottom: 2rem;
    border-radius: 10px;
    box-shadow: var(--shadow);
}

.demo-section h2 {
    color: var(--secondary-color);
    margin-bottom: 2rem;
    text-align: center;
    font-size: 2.5rem;
}

.demo-container {
    margin-bottom: 3rem;
}

.demo-container h3 {
    color: var(--secondary-color);
    margin-bottom: 1rem;
    font-size: 1.5rem;
}

.demo-controls {
    display: flex;
    gap: 0.5rem;
    margin-bottom: 1rem;
    flex-wrap: wrap;
}

.demo-controls button {
    background: var(--background-color);
    border: 1px solid var(--border-color);
    padding: 0.5rem 1rem;
    border-radius: 5px;
    cursor: pointer;
    font-size: 0.9rem;
    transition: all 0.3s;
}

.demo-controls button:hover {
    background: var(--primary-color);
    color: white;
}

/* Démo flex */
.demo-flex {
    display: flex;
    background: #f8f9fa;
    border: 2px solid var(--border-color);
    border-radius: 5px;
    padding: 1rem;
    min-height: 80px;
}

.demo-flex.tall {
    height: 150px;
}

.demo-item {
    background: var(--primary-color);
    color: white;
    padding: 1rem;
    margin: 0.25rem;
    border-radius: 5px;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: center;
    min-width: 60px;
}

.demo-item.large {
    font-size: 1.5rem;
    padding: 1.5rem;
}

/* Grille de cartes */
.cards-section {
    background: white;
    padding: 3rem 2rem;
    margin-bottom: 2rem;
    border-radius: 10px;
    box-shadow: var(--shadow);
}

.cards-section h2 {
    color: var(--secondary-color);
    margin-bottom: 2rem;
    text-align: center;
    font-size: 2.5rem;
}

.cards-container {
    display: flex;
    gap: 2rem;
    flex-wrap: wrap;
}

.card {
    flex: 1 1 300px;
    min-width: 0;
    background: white;
    border: 1px solid var(--border-color);
    border-radius: 10px;
    box-shadow: var(--shadow);
    overflow: hidden;
    transition: transform 0.3s;
    display: flex;
    flex-direction: column;
}

.card:hover {
    transform: translateY(-5px);
}

.card-header {
    padding: 1.5rem;
    background: var(--background-color);
    border-bottom: 1px solid var(--border-color);
}

.card-header h3 {
    color: var(--secondary-color);
    font-size: 1.3rem;
}

.card-body {
    padding: 1.5rem;
    flex: 1;
}

.card-body p {
    color: #666;
    line-height: 1.6;
}

.card-footer {
    padding: 1.5rem;
    background: var(--background-color);
    border-top: 1px solid var(--border-color);
    text-align: center;
}

/* Layout avec sidebar */
.layout-section {
    background: white;
    padding: 3rem 2rem;
    margin-bottom: 2rem;
    border-radius: 10px;
    box-shadow: var(--shadow);
}

.layout-section h2 {
    color: var(--secondary-color);
    margin-bottom: 2rem;
    text-align: center;
    font-size: 2.5rem;
}

.layout-demo {
    display: flex;
    gap: 2rem;
    background: var(--background-color);
    border-radius: 10px;
    overflow: hidden;
    min-height: 300px;
}

.sidebar {
    flex: 0 0 250px;
    background: var(--secondary-color);
    color: white;
    padding: 2rem;
}

.sidebar h3 {
    margin-bottom: 1rem;
    color: white;
}

.sidebar-menu {
    list-style: none;
}

.sidebar-menu li {
    margin-bottom: 0.5rem;
}

.sidebar-menu a {
    color: #bdc3c7;
    text-decoration: none;
    padding: 0.5rem 0;
    display: block;
    transition: color 0.3s;
}

.sidebar-menu a:hover {
    color: white;
}

.content {
    flex: 1;
    padding: 2rem;
    background: white;
}

.content h3 {
    color: var(--secondary-color);
    margin-bottom: 1rem;
}

.content code {
    background: var(--background-color);
    padding: 0.25rem 0.5rem;
    border-radius: 3px;
    font-family: 'Courier New', monospace;
    color: var(--primary-color);
}

/* Footer */
.footer {
    background: var(--secondary-color);
    color: white;
    padding: 3rem 0 1rem;
}

.footer-content {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 2rem;
    margin-bottom: 2rem;
}

.footer-section {
    flex: 1;
    min-width: 250px;
}

.footer-section h4 {
    margin-bottom: 1rem;
    color: white;
}

.footer-section ul {
    list-style: none;
}

.footer-section ul li {
    margin-bottom: 0.5rem;
}

.footer-section a {
    color: #bdc3c7;
    text-decoration: none;
    transition: color 0.3s;
}

.footer-section a:hover {
    color: white;
}

.footer-bottom {
    text-align: center;
    padding-top: 2rem;
    border-top: 1px solid #34495e;
    color: #bdc3c7;
}

/* Responsive */
@media (max-width: 768px) {
    .nav {
        flex-direction: column;
        gap: 1rem;
    }

    .nav-links {
        flex-direction: column;
        gap: 1rem;
    }

    .hero-content h2 {
        font-size: 2rem;
    }

    .hero-actions {
        flex-direction: column;
        align-items: center;
    }

    .demo-controls {
        justify-content: center;
    }

    .layout-demo {
        flex-direction: column;
    }

    .sidebar {
        flex: none;
    }

    .footer-content {
        flex-direction: column;
        text-align: center;
    }

    .container {
        padding: 0 1rem;
    }
}

@media (max-width: 480px) {
    .demo-flex {
        flex-direction: column;
        align-items: center;
    }

    .demo-item {
        width: 100%;
        max-width: 200px;
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

.demo-section,
.cards-section,
.layout-section {
    animation: fadeInUp 0.6s ease-out;
}

/* Accessibilité */
button:focus,
.btn:focus {
    outline: 2px solid var(--primary-color);
    outline-offset: 2px;
}

/* Préférences utilisateur */
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
   - Navigation horizontale avec Flexbox
   - Section hero centrée
   - Grille de cartes responsives
   - Layout avec sidebar flexible
   - Footer avec colonnes

2. Implementez :
   - Boutons de démonstration pour changer les propriétés
   - Animations et transitions
   - Design responsive avec Flexbox
   - Accessibilité au clavier

3. Testez différentes combinaisons de propriétés

## 🔍 Bonnes pratiques

- **Utilisez Flexbox** pour les layouts 1D (ligne ou colonne)
- **Combinez** avec CSS Grid pour les layouts complexes
- **Pensez mobile-first** avec flex-wrap
- **Utilisez gap** pour l'espacement uniforme
- **Évitez les hauteurs fixes** quand possible

## 🔗 Ressources supplémentaires

- [Flexbox Froggy](https://flexboxfroggy.com/)
- [CSS-Tricks Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [MDN Flexbox](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Flexible_Box_Layout)

---

**Temps estimé :** 4 heures  
**Prochaine étape :** [Module 8 - CSS Grid](../08-grid/)