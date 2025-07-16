# Module 9 : Design responsive

## 🎯 Objectifs du module

- Comprendre les principes du design responsive
- Maîtriser les media queries
- Utiliser les unités relatives et viewport
- Créer des layouts adaptatifs avec Flexbox et Grid

## 📱 Introduction au responsive design

### Qu'est-ce que le responsive design ?

Le design responsive permet aux sites web de s'adapter automatiquement à tous les types d'écrans et appareils :
- Smartphones (320px - 768px)
- Tablettes (768px - 1024px)
- Ordinateurs de bureau (1024px+)
- Écrans ultra-larges (1440px+)

### Approche mobile-first

```css
/* Mobile-first : styles de base pour mobile */
.container {
    padding: 1rem;
    font-size: 14px;
}

/* Tablette et plus */
@media (min-width: 768px) {
    .container {
        padding: 2rem;
        font-size: 16px;
    }
}

/* Desktop et plus */
@media (min-width: 1024px) {
    .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 3rem;
    }
}
```

## 📐 Viewport et métadonnées

### Balise viewport

```html
<!-- Essentiel pour le responsive -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Contrôles avancés -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
```

### Unités viewport

```css
/* Unités viewport */
.full-screen {
    width: 100vw;    /* 100% de la largeur viewport */
    height: 100vh;   /* 100% de la hauteur viewport */
}

.responsive-text {
    font-size: 4vw;  /* 4% de la largeur viewport */
}

.min-dimension {
    width: 50vmin;   /* 50% de la plus petite dimension */
}

.max-dimension {
    width: 30vmax;   /* 30% de la plus grande dimension */
}
```

## 📱 Media queries

### Syntaxe de base

```css
/* Media query simple */
@media screen and (max-width: 768px) {
    .mobile-only {
        display: block;
    }
}

/* Media query pour impression */
@media print {
    .no-print {
        display: none;
    }
}

/* Orientation */
@media (orientation: landscape) {
    .landscape-layout {
        flex-direction: row;
    }
}

@media (orientation: portrait) {
    .portrait-layout {
        flex-direction: column;
    }
}
```

### Breakpoints courants

```css
/* Variables pour les breakpoints */
:root {
    --mobile: 480px;
    --tablet: 768px;
    --desktop: 1024px;
    --large: 1440px;
}

/* Mobile-first approach */
/* Mobile (défaut) */
.container {
    padding: 1rem;
}

/* Tablette */
@media (min-width: 768px) {
    .container {
        padding: 2rem;
        max-width: 750px;
        margin: 0 auto;
    }
}

/* Desktop */
@media (min-width: 1024px) {
    .container {
        max-width: 1000px;
        padding: 3rem;
    }
}

/* Large screens */
@media (min-width: 1440px) {
    .container {
        max-width: 1200px;
    }
}
```

### Media queries avancées

```css
/* Résolution écran */
@media (min-resolution: 2dppx) {
    .high-res-image {
        background-image: url('image@2x.jpg');
    }
}

/* Préférences utilisateur */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a1a;
        color: #e0e0e0;
    }
}

@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}

/* Capacités d'interaction */
@media (hover: hover) {
    .button:hover {
        background: blue;
    }
}

@media (pointer: coarse) {
    .touch-target {
        min-height: 44px;
        min-width: 44px;
    }
}
```

## 📏 Unités responsives

### Unités relatives

```css
/* Em - relatif au parent */
.em-example {
    font-size: 18px;
}

.em-child {
    font-size: 1.2em; /* 18px × 1.2 = 21.6px */
    margin: 0.5em;    /* 21.6px × 0.5 = 10.8px */
}

/* Rem - relatif à la racine */
html {
    font-size: 16px; /* Base */
}

.rem-element {
    font-size: 1.5rem;  /* 16px × 1.5 = 24px */
    padding: 1rem;      /* 16px */
    margin: 2rem 0;     /* 32px 0 */
}

/* Pourcentages */
.percentage {
    width: 50%;         /* 50% du parent */
    height: 75%;        /* 75% du parent */
    font-size: 120%;    /* 120% de la police héritée */
}
```

### Calculs dynamiques

```css
/* Fonction calc() */
.calc-example {
    width: calc(100% - 2rem);
    height: calc(100vh - 80px);
    font-size: calc(1rem + 0.5vw);
    margin: calc(2rem + 1vw) auto;
}

/* Fonctions min/max/clamp */
.responsive-sizing {
    /* Minimum 300px, maximum 50% */
    width: min(50%, 300px);
    
    /* Minimum 1rem, maximum 3rem */
    font-size: max(1rem, 3vw);
    
    /* Entre 1rem et 3rem, idéal 2.5vw */
    font-size: clamp(1rem, 2.5vw, 3rem);
}
```

## 🎨 Layouts responsives

### Flexbox responsive

```css
/* Navigation responsive */
.nav {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: space-between;
}

.nav-item {
    flex: 1 1 auto;
    min-width: 120px;
}

@media (max-width: 768px) {
    .nav {
        flex-direction: column;
        text-align: center;
    }
}

/* Cartes flexibles */
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
}

.card {
    flex: 1 1 300px;
    min-width: 0; /* Évite le débordement */
}
```

### Grid responsive

```css
/* Grille auto-responsive */
.grid-auto {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
}

/* Grille avec breakpoints */
.grid-responsive {
    display: grid;
    gap: 1rem;
    
    /* Mobile: 1 colonne */
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .grid-responsive {
        /* Tablette: 2 colonnes */
        grid-template-columns: repeat(2, 1fr);
        gap: 2rem;
    }
}

@media (min-width: 1024px) {
    .grid-responsive {
        /* Desktop: 3 colonnes */
        grid-template-columns: repeat(3, 1fr);
        gap: 3rem;
    }
}
```

## 🖼️ Images responsives

### Images adaptatives

```html
<!-- Image responsive simple -->
<img src="image.jpg" alt="Description" style="max-width: 100%; height: auto;">

<!-- Images avec srcset -->
<img src="image-400.jpg" 
     srcset="image-400.jpg 400w,
             image-800.jpg 800w,
             image-1200.jpg 1200w"
     sizes="(max-width: 600px) 400px,
            (max-width: 1000px) 800px,
            1200px"
     alt="Image responsive">

<!-- Element picture -->
<picture>
    <source media="(max-width: 600px)" srcset="image-mobile.jpg">
    <source media="(max-width: 1200px)" srcset="image-tablet.jpg">
    <img src="image-desktop.jpg" alt="Image adaptative">
</picture>
```

### CSS pour images

```css
/* Images responsives par défaut */
img {
    max-width: 100%;
    height: auto;
}

/* Image d'arrière-plan responsive */
.bg-responsive {
    background-image: url('image-mobile.jpg');
    background-size: cover;
    background-position: center;
}

@media (min-width: 768px) {
    .bg-responsive {
        background-image: url('image-desktop.jpg');
    }
}

/* Object-fit pour contrôler le redimensionnement */
.image-fit {
    width: 100%;
    height: 200px;
    object-fit: cover;
    object-position: center;
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
    <title>Design Responsive - Exemple complet</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Header responsive -->
    <header class="header">
        <div class="container">
            <nav class="nav">
                <div class="nav-brand">
                    <h1>ResponsiveSite</h1>
                </div>
                <button class="nav-toggle" aria-label="Menu mobile">
                    <span></span>
                    <span></span>
                    <span></span>
                </button>
                <ul class="nav-menu">
                    <li><a href="#home">Accueil</a></li>
                    <li><a href="#about">À propos</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#portfolio">Portfolio</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero section responsive -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h2 class="hero-title">Design Responsive Moderne</h2>
                <p class="hero-subtitle">Créez des expériences exceptionnelles sur tous les appareils</p>
                <div class="hero-actions">
                    <button class="btn btn-primary">Commencer</button>
                    <button class="btn btn-secondary">En savoir plus</button>
                </div>
            </div>
            <div class="hero-image">
                <picture>
                    <source media="(max-width: 768px)" srcset="https://picsum.photos/400/300">
                    <source media="(max-width: 1200px)" srcset="https://picsum.photos/600/400">
                    <img src="https://picsum.photos/800/500" alt="Hero image">
                </picture>
            </div>
        </div>
    </section>

    <!-- Section features avec grille responsive -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">Fonctionnalités</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">📱</div>
                    <h3>Mobile-First</h3>
                    <p>Conception optimisée pour les appareils mobiles en priorité</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <h3>Performance</h3>
                    <p>Chargement rapide et optimisé pour tous les appareils</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎨</div>
                    <h3>Design adaptatif</h3>
                    <p>Interface qui s'adapte parfaitement à chaque écran</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">♿</div>
                    <h3>Accessibilité</h3>
                    <p>Accessible à tous les utilisateurs et technologies d'assistance</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔧</div>
                    <h3>Flexibilité</h3>
                    <p>Layout flexible qui s'adapte au contenu</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🌐</div>
                    <h3>Cross-browser</h3>
                    <p>Compatible avec tous les navigateurs modernes</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Section portfolio avec images responsives -->
    <section class="portfolio">
        <div class="container">
            <h2 class="section-title">Portfolio</h2>
            <div class="portfolio-grid">
                <div class="portfolio-item large">
                    <img src="https://picsum.photos/600/400" alt="Projet 1">
                    <div class="portfolio-overlay">
                        <h3>Projet principal</h3>
                        <p>Description du projet principal</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <img src="https://picsum.photos/400/300" alt="Projet 2">
                    <div class="portfolio-overlay">
                        <h3>Projet 2</h3>
                        <p>Description du projet</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <img src="https://picsum.photos/400/300" alt="Projet 3">
                    <div class="portfolio-overlay">
                        <h3>Projet 3</h3>
                        <p>Description du projet</p>
                    </div>
                </div>
                <div class="portfolio-item wide">
                    <img src="https://picsum.photos/800/300" alt="Projet 4">
                    <div class="portfolio-overlay">
                        <h3>Projet large</h3>
                        <p>Description du projet large</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <img src="https://picsum.photos/400/300" alt="Projet 5">
                    <div class="portfolio-overlay">
                        <h3>Projet 5</h3>
                        <p>Description du projet</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section stats responsive -->
    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number">150+</div>
                    <div class="stat-label">Projets réalisés</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">98%</div>
                    <div class="stat-label">Clients satisfaits</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">5+</div>
                    <div class="stat-label">Années d'expérience</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">24/7</div>
                    <div class="stat-label">Support disponible</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section contact avec formulaire responsive -->
    <section class="contact">
        <div class="container">
            <h2 class="section-title">Contact</h2>
            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Parlons de votre projet</h3>
                    <p>Nous serions ravis de discuter de vos besoins et de voir comment nous pouvons vous aider.</p>
                    <div class="contact-details">
                        <div class="contact-item">
                            <strong>Email:</strong> contact@example.com
                        </div>
                        <div class="contact-item">
                            <strong>Téléphone:</strong> +33 1 23 45 67 89
                        </div>
                        <div class="contact-item">
                            <strong>Adresse:</strong> 123 Rue de la Tech, 75001 Paris
                        </div>
                    </div>
                </div>
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Nom</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Sujet</label>
                        <input type="text" id="subject" name="subject" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary full-width">Envoyer le message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer responsive -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>ResponsiveSite</h4>
                    <p>Créateur d'expériences web exceptionnelles</p>
                    <div class="social-links">
                        <a href="#" aria-label="Facebook">📘</a>
                        <a href="#" aria-label="Twitter">🐦</a>
                        <a href="#" aria-label="LinkedIn">💼</a>
                        <a href="#" aria-label="Instagram">📷</a>
                    </div>
                </div>
                <div class="footer-section">
                    <h4>Services</h4>
                    <ul>
                        <li><a href="#">Design web</a></li>
                        <li><a href="#">Développement</a></li>
                        <li><a href="#">Responsive design</a></li>
                        <li><a href="#">Optimisation mobile</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Ressources</h4>
                    <ul>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Documentation</a></li>
                        <li><a href="#">Guides</a></li>
                        <li><a href="#">Support</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Newsletter</h4>
                    <p>Restez informé de nos dernières actualités</p>
                    <form class="newsletter-form">
                        <input type="email" placeholder="Votre email" required>
                        <button type="submit">S'abonner</button>
                    </form>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2024 ResponsiveSite. Tous droits réservés.</p>
            </div>
        </div>
    </footer>

    <script>
        // Toggle menu mobile
        const navToggle = document.querySelector('.nav-toggle');
        const navMenu = document.querySelector('.nav-menu');
        
        navToggle.addEventListener('click', () => {
            navMenu.classList.toggle('active');
            navToggle.classList.toggle('active');
        });
        
        // Fermer le menu en cliquant sur un lien
        document.querySelectorAll('.nav-menu a').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
                navToggle.classList.remove('active');
            });
        });
    </script>
</body>
</html>
```

**CSS :**
```css
/* Variables CSS pour le responsive */
:root {
    /* Breakpoints */
    --mobile: 480px;
    --tablet: 768px;
    --desktop: 1024px;
    --large: 1440px;
    
    /* Couleurs */
    --primary: #667eea;
    --secondary: #764ba2;
    --accent: #f093fb;
    --text: #333;
    --text-light: #666;
    --background: #ffffff;
    --surface: #f8f9fa;
    --border: #e9ecef;
    
    /* Espacement */
    --space-xs: 0.5rem;
    --space-sm: 1rem;
    --space-md: 2rem;
    --space-lg: 3rem;
    --space-xl: 4rem;
    
    /* Typographie responsive */
    --font-size-sm: clamp(0.875rem, 0.8rem + 0.3vw, 1rem);
    --font-size-base: clamp(1rem, 0.9rem + 0.4vw, 1.125rem);
    --font-size-lg: clamp(1.125rem, 1rem + 0.5vw, 1.25rem);
    --font-size-xl: clamp(1.25rem, 1.1rem + 0.6vw, 1.5rem);
    --font-size-2xl: clamp(1.5rem, 1.3rem + 0.8vw, 2rem);
    --font-size-3xl: clamp(2rem, 1.5rem + 1.5vw, 3rem);
}

/* Reset et base */
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
    font-size: var(--font-size-base);
}

/* Container responsive */
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--space-sm);
}

@media (min-width: 768px) {
    .container {
        padding: 0 var(--space-md);
    }
}

@media (min-width: 1024px) {
    .container {
        padding: 0 var(--space-lg);
    }
}

/* Navigation responsive */
.header {
    background: var(--background);
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: var(--space-sm) 0;
    position: relative;
}

.nav-brand h1 {
    color: var(--primary);
    font-size: var(--font-size-xl);
}

.nav-toggle {
    display: none;
    flex-direction: column;
    background: none;
    border: none;
    cursor: pointer;
    padding: var(--space-xs);
}

.nav-toggle span {
    width: 25px;
    height: 3px;
    background: var(--text);
    margin: 3px 0;
    transition: 0.3s;
    border-radius: 2px;
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: var(--space-md);
}

.nav-menu a {
    color: var(--text);
    text-decoration: none;
    font-weight: 500;
    padding: var(--space-xs) var(--space-sm);
    border-radius: 5px;
    transition: all 0.3s;
}

.nav-menu a:hover {
    color: var(--primary);
    background: var(--surface);
}

/* Navigation mobile */
@media (max-width: 767px) {
    .nav-toggle {
        display: flex;
    }
    
    .nav-menu {
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: var(--background);
        flex-direction: column;
        padding: var(--space-sm);
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        transform: translateY(-100%);
        opacity: 0;
        visibility: hidden;
        transition: all 0.3s;
        gap: 0;
    }
    
    .nav-menu.active {
        transform: translateY(0);
        opacity: 1;
        visibility: visible;
    }
    
    .nav-menu a {
        display: block;
        padding: var(--space-sm);
        border-bottom: 1px solid var(--border);
    }
    
    .nav-toggle.active span:nth-child(1) {
        transform: rotate(-45deg) translate(-5px, 6px);
    }
    
    .nav-toggle.active span:nth-child(2) {
        opacity: 0;
    }
    
    .nav-toggle.active span:nth-child(3) {
        transform: rotate(45deg) translate(-5px, -6px);
    }
}

/* Hero section responsive */
.hero {
    background: linear-gradient(135deg, var(--primary), var(--secondary));
    color: white;
    padding: var(--space-xl) 0;
    min-height: 70vh;
    display: flex;
    align-items: center;
}

.hero .container {
    display: grid;
    gap: var(--space-lg);
    align-items: center;
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .hero .container {
        grid-template-columns: 1fr 1fr;
    }
}

.hero-title {
    font-size: var(--font-size-3xl);
    font-weight: 700;
    margin-bottom: var(--space-sm);
    line-height: 1.2;
}

.hero-subtitle {
    font-size: var(--font-size-lg);
    margin-bottom: var(--space-md);
    opacity: 0.9;
}

.hero-actions {
    display: flex;
    gap: var(--space-sm);
    flex-wrap: wrap;
}

.hero-image img {
    width: 100%;
    height: auto;
    border-radius: 10px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

/* Boutons responsives */
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: var(--space-sm) var(--space-md);
    border: none;
    border-radius: 5px;
    font-size: var(--font-size-base);
    font-weight: 500;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s;
    min-width: 120px;
}

.btn-primary {
    background: var(--accent);
    color: white;
}

.btn-primary:hover {
    background: #e085f0;
    transform: translateY(-2px);
}

.btn-secondary {
    background: transparent;
    color: white;
    border: 2px solid white;
}

.btn-secondary:hover {
    background: white;
    color: var(--primary);
}

.full-width {
    width: 100%;
}

/* Sections */
section {
    padding: var(--space-xl) 0;
}

.section-title {
    font-size: var(--font-size-2xl);
    text-align: center;
    margin-bottom: var(--space-lg);
    color: var(--text);
}

/* Features grid responsive */
.features {
    background: var(--surface);
}

.features-grid {
    display: grid;
    gap: var(--space-md);
    grid-template-columns: 1fr;
}

@media (min-width: 480px) {
    .features-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 768px) {
    .features-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}

.feature-card {
    background: var(--background);
    padding: var(--space-md);
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s;
}

.feature-card:hover {
    transform: translateY(-5px);
}

.feature-icon {
    font-size: 3rem;
    margin-bottom: var(--space-sm);
}

.feature-card h3 {
    font-size: var(--font-size-lg);
    margin-bottom: var(--space-sm);
    color: var(--text);
}

/* Portfolio grid responsive */
.portfolio-grid {
    display: grid;
    gap: var(--space-sm);
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .portfolio-grid {
        grid-template-columns: repeat(3, 1fr);
        gap: var(--space-md);
    }
}

.portfolio-item {
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    aspect-ratio: 4/3;
}

.portfolio-item.large {
    grid-row: span 2;
}

.portfolio-item.wide {
    grid-column: span 2;
}

@media (max-width: 767px) {
    .portfolio-item.large,
    .portfolio-item.wide {
        grid-column: 1;
        grid-row: span 1;
    }
}

.portfolio-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s;
}

.portfolio-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.8);
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: var(--space-md);
    opacity: 0;
    transition: opacity 0.3s;
}

.portfolio-item:hover .portfolio-overlay {
    opacity: 1;
}

.portfolio-item:hover img {
    transform: scale(1.1);
}

/* Stats responsive */
.stats {
    background: var(--primary);
    color: white;
}

.stats-grid {
    display: grid;
    gap: var(--space-md);
    grid-template-columns: 1fr;
    text-align: center;
}

@media (min-width: 480px) {
    .stats-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 768px) {
    .stats-grid {
        grid-template-columns: repeat(4, 1fr);
    }
}

.stat-number {
    font-size: var(--font-size-3xl);
    font-weight: 700;
    margin-bottom: var(--space-xs);
}

.stat-label {
    font-size: var(--font-size-base);
    opacity: 0.9;
}

/* Contact responsive */
.contact {
    background: var(--surface);
}

.contact-grid {
    display: grid;
    gap: var(--space-lg);
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .contact-grid {
        grid-template-columns: 1fr 1fr;
    }
}

.contact-info h3 {
    font-size: var(--font-size-xl);
    margin-bottom: var(--space-sm);
    color: var(--text);
}

.contact-details {
    margin-top: var(--space-md);
}

.contact-item {
    margin-bottom: var(--space-sm);
    padding: var(--space-sm);
    background: var(--background);
    border-radius: 5px;
}

/* Formulaire responsive */
.contact-form {
    background: var(--background);
    padding: var(--space-md);
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.form-group {
    margin-bottom: var(--space-sm);
}

.form-group label {
    display: block;
    margin-bottom: var(--space-xs);
    font-weight: 500;
    color: var(--text);
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: var(--space-sm);
    border: 1px solid var(--border);
    border-radius: 5px;
    font-size: var(--font-size-base);
    transition: border-color 0.3s;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: var(--primary);
}

/* Footer responsive */
.footer {
    background: var(--text);
    color: white;
    padding: var(--space-lg) 0 var(--space-md);
}

.footer-content {
    display: grid;
    gap: var(--space-md);
    grid-template-columns: 1fr;
    margin-bottom: var(--space-md);
}

@media (min-width: 480px) {
    .footer-content {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 768px) {
    .footer-content {
        grid-template-columns: repeat(4, 1fr);
    }
}

.footer-section h4 {
    margin-bottom: var(--space-sm);
    color: white;
}

.footer-section ul {
    list-style: none;
}

.footer-section li {
    margin-bottom: var(--space-xs);
}

.footer-section a {
    color: rgba(255, 255, 255, 0.8);
    text-decoration: none;
    transition: color 0.3s;
}

.footer-section a:hover {
    color: white;
}

.social-links {
    display: flex;
    gap: var(--space-sm);
    margin-top: var(--space-sm);
}

.social-links a {
    font-size: 1.5rem;
    transition: transform 0.3s;
}

.social-links a:hover {
    transform: scale(1.2);
}

.newsletter-form {
    display: flex;
    gap: var(--space-xs);
    margin-top: var(--space-sm);
}

.newsletter-form input {
    flex: 1;
    padding: var(--space-xs);
    border: none;
    border-radius: 5px;
}

.newsletter-form button {
    background: var(--primary);
    color: white;
    border: none;
    padding: var(--space-xs) var(--space-sm);
    border-radius: 5px;
    cursor: pointer;
    white-space: nowrap;
}

.footer-bottom {
    text-align: center;
    padding-top: var(--space-md);
    border-top: 1px solid rgba(255, 255, 255, 0.2);
    color: rgba(255, 255, 255, 0.8);
}

/* Utilitaires responsive */
.hidden-mobile {
    display: none;
}

@media (min-width: 768px) {
    .hidden-mobile {
        display: block;
    }
    
    .hidden-desktop {
        display: none;
    }
}

/* Animation et transitions */
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

section {
    animation: fadeInUp 0.6s ease-out;
}

/* États focus pour l'accessibilité */
button:focus,
input:focus,
textarea:focus,
a:focus {
    outline: 2px solid var(--primary);
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

@media (prefers-color-scheme: dark) {
    :root {
        --text: #e0e0e0;
        --text-light: #b0b0b0;
        --background: #1a1a1a;
        --surface: #2d2d2d;
        --border: #404040;
    }
}

/* Print styles */
@media print {
    .nav-toggle,
    .hero-actions,
    .btn,
    .contact-form {
        display: none;
    }
    
    body {
        color: black;
        background: white;
    }
    
    .hero {
        background: none;
        color: black;
    }
}
```

## ✅ Exercice pratique

1. Créez un site responsive complet avec :
   - Navigation mobile avec hamburger menu
   - Hero section adaptative
   - Grille de contenu responsive
   - Images responsives avec picture/srcset
   - Formulaire optimisé mobile

2. Implémentez :
   - Breakpoints cohérents
   - Typographie responsive avec clamp()
   - Touch targets appropriés (44px minimum)
   - Navigation au clavier

3. Testez sur :
   - Différentes tailles d'écran
   - Orientations portrait/paysage
   - Différents navigateurs

## 🔍 Bonnes pratiques

- **Mobile-first** toujours
- **Touch targets** de 44px minimum
- **Performance** : optimisez les images
- **Accessibilité** : navigation au clavier
- **Testez** sur de vrais appareils

## 🔗 Ressources supplémentaires

- [Responsive Design Checker](https://responsivedesignchecker.com/)
- [Can I Use](https://caniuse.com/)
- [Google Mobile-Friendly Test](https://search.google.com/test/mobile-friendly)
- [CSS Clamp Calculator](https://clamp.font-size.app/)

---

**Temps estimé :** 4 heures  
**Prochaine étape :** [Module 10 - Animations](../10-animations/)