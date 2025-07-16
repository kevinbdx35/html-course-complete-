# Module 4 : Couleurs et arrière-plans

## 🎯 Objectifs du module

- Maîtriser les différents formats de couleurs
- Créer des arrière-plans attractifs
- Utiliser les dégradés et les images de fond
- Comprendre l'accessibilité des couleurs

## 🎨 Formats de couleurs

### Couleurs nommées

```css
/* Couleurs de base */
.rouge { color: red; }
.bleu { color: blue; }
.vert { color: green; }

/* Couleurs étendues */
.saumon { color: salmon; }
.turquoise { color: turquoise; }
.violet { color: mediumorchid; }

/* Couleurs système */
.transparent { background: transparent; }
.actuelle { color: currentColor; }
```

### Couleurs hexadécimales

```css
/* Format complet */
.hex-complet { color: #ff0000; }
.hex-bleu { color: #0066cc; }

/* Format court */
.hex-court { color: #f00; }
.hex-gris { color: #ccc; }

/* Avec transparence (8 caractères) */
.hex-alpha { background: #ff000080; }
```

### Couleurs RGB et RGBA

```css
/* RGB - valeurs 0-255 */
.rgb-rouge { color: rgb(255, 0, 0); }
.rgb-bleu { color: rgb(0, 102, 204); }

/* RGBA - avec transparence */
.rgba-semi { background: rgba(255, 0, 0, 0.5); }
.rgba-leger { background: rgba(0, 0, 0, 0.1); }

/* RGB moderne avec alpha */
.rgb-moderne { color: rgb(255 0 0 / 0.5); }
```

### Couleurs HSL et HSLA

```css
/* HSL - Teinte, Saturation, Luminosité */
.hsl-rouge { color: hsl(0, 100%, 50%); }
.hsl-bleu { color: hsl(210, 100%, 50%); }

/* HSLA - avec transparence */
.hsla-vert { background: hsla(120, 100%, 50%, 0.3); }

/* HSL moderne */
.hsl-moderne { color: hsl(210 100% 50% / 0.8); }
```

## 🖼️ Arrière-plans de base

### Couleur d'arrière-plan

```css
/* Couleur unie */
.bg-rouge { background-color: #e74c3c; }
.bg-bleu { background-color: #3498db; }
.bg-transparent { background-color: transparent; }

/* Avec transparence */
.bg-semi { background-color: rgba(231, 76, 60, 0.2); }
```

### Images d'arrière-plan

```css
/* Image simple */
.bg-image {
    background-image: url('image.jpg');
}

/* Propriétés d'image */
.bg-complete {
    background-image: url('pattern.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}

/* Propriété raccourcie */
.bg-shorthand {
    background: url('hero.jpg') center/cover no-repeat;
}
```

### Contrôle des images

```css
/* Répétition */
.bg-repeat { background-repeat: repeat; }
.bg-no-repeat { background-repeat: no-repeat; }
.bg-repeat-x { background-repeat: repeat-x; }
.bg-repeat-y { background-repeat: repeat-y; }

/* Position */
.bg-center { background-position: center; }
.bg-top-left { background-position: top left; }
.bg-custom { background-position: 20% 80%; }
.bg-pixels { background-position: 50px 100px; }

/* Taille */
.bg-cover { background-size: cover; }
.bg-contain { background-size: contain; }
.bg-auto { background-size: auto; }
.bg-custom-size { background-size: 200px 300px; }

/* Attachement */
.bg-fixed { background-attachment: fixed; }
.bg-scroll { background-attachment: scroll; }
```

## 🌈 Dégradés CSS

### Dégradé linéaire

```css
/* Dégradé simple */
.gradient-simple {
    background: linear-gradient(to right, #ff0000, #0000ff);
}

/* Avec direction */
.gradient-direction {
    background: linear-gradient(45deg, #e74c3c, #3498db);
}

/* Plusieurs couleurs */
.gradient-multiple {
    background: linear-gradient(
        to bottom,
        #ff0000 0%,
        #ffff00 50%,
        #0000ff 100%
    );
}

/* Dégradé complexe */
.gradient-complexe {
    background: linear-gradient(
        135deg,
        #667eea 0%,
        #764ba2 100%
    );
}
```

### Dégradé radial

```css
/* Dégradé radial simple */
.radial-simple {
    background: radial-gradient(circle, #ff0000, #0000ff);
}

/* Avec position */
.radial-position {
    background: radial-gradient(
        circle at top left,
        #e74c3c,
        #3498db
    );
}

/* Ellipse avec taille */
.radial-ellipse {
    background: radial-gradient(
        ellipse 200px 100px at center,
        #ff0000 0%,
        #0000ff 100%
    );
}
```

### Dégradé conique

```css
/* Dégradé conique */
.conic-gradient {
    background: conic-gradient(
        from 0deg,
        #ff0000,
        #ffff00,
        #00ff00,
        #00ffff,
        #0000ff,
        #ff00ff,
        #ff0000
    );
}

/* Avec position */
.conic-position {
    background: conic-gradient(
        from 45deg at 25% 25%,
        #e74c3c,
        #3498db,
        #2ecc71
    );
}
```

## 🔧 Techniques avancées

### Arrière-plans multiples

```css
.bg-multiple {
    background:
        url('overlay.png') center/cover no-repeat,
        linear-gradient(45deg, #ff0000, #0000ff),
        url('texture.jpg') center/cover;
}

/* Avec propriétés séparées */
.bg-layers {
    background-image: 
        url('top-layer.png'),
        url('bottom-layer.jpg');
    background-position: 
        center top,
        center bottom;
    background-repeat: 
        no-repeat,
        repeat;
}
```

### Clip-path et masques

```css
/* Découpage avec clip-path */
.clip-path {
    background: linear-gradient(45deg, #ff0000, #0000ff);
    clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
}

/* Masque */
.mask {
    background: linear-gradient(45deg, #ff0000, #0000ff);
    mask: radial-gradient(circle, transparent 30%, black 70%);
}
```

### Filtres CSS

```css
/* Filtres sur arrière-plan */
.filter-blur {
    background: url('image.jpg') center/cover;
    filter: blur(5px);
}

.filter-grayscale {
    background: url('image.jpg') center/cover;
    filter: grayscale(100%);
}

.filter-multiple {
    background: url('image.jpg') center/cover;
    filter: brightness(0.8) contrast(1.2) saturate(1.1);
}
```

## 🎯 Variables CSS pour couleurs

```css
/* Définition des variables */
:root {
    --color-primary: #3498db;
    --color-secondary: #e74c3c;
    --color-success: #2ecc71;
    --color-warning: #f39c12;
    --color-danger: #e74c3c;
    
    --gradient-primary: linear-gradient(135deg, #667eea, #764ba2);
    --gradient-sunset: linear-gradient(45deg, #ff9a9e, #fecfef);
    
    --shadow-light: 0 2px 10px rgba(0, 0, 0, 0.1);
    --shadow-dark: 0 4px 20px rgba(0, 0, 0, 0.3);
}

/* Utilisation */
.btn-primary {
    background: var(--color-primary);
    box-shadow: var(--shadow-light);
}

.hero-section {
    background: var(--gradient-primary);
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
    <title>Couleurs et Arrière-plans</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header class="hero">
        <div class="hero-content">
            <h1>Maîtrise des Couleurs</h1>
            <p>Découvrez la puissance des couleurs et arrière-plans CSS</p>
            <button class="btn btn-primary">Commencer</button>
        </div>
    </header>

    <main>
        <section class="color-showcase">
            <h2>Palette de couleurs</h2>
            <div class="color-grid">
                <div class="color-card primary">
                    <h3>Primaire</h3>
                    <p>#3498db</p>
                </div>
                <div class="color-card secondary">
                    <h3>Secondaire</h3>
                    <p>#e74c3c</p>
                </div>
                <div class="color-card success">
                    <h3>Succès</h3>
                    <p>#2ecc71</p>
                </div>
                <div class="color-card warning">
                    <h3>Attention</h3>
                    <p>#f39c12</p>
                </div>
            </div>
        </section>

        <section class="gradient-showcase">
            <h2>Dégradés</h2>
            <div class="gradient-grid">
                <div class="gradient-card linear">
                    <h3>Linéaire</h3>
                </div>
                <div class="gradient-card radial">
                    <h3>Radial</h3>
                </div>
                <div class="gradient-card conic">
                    <h3>Conique</h3>
                </div>
            </div>
        </section>

        <section class="background-showcase">
            <div class="bg-pattern">
                <h2>Arrière-plans créatifs</h2>
                <p>Combinaison d'images, couleurs et dégradés</p>
            </div>
        </section>
    </main>

    <footer class="footer">
        <p>&copy; 2024 - Cours CSS Avancé</p>
    </footer>
</body>
</html>
```

**CSS :**
```css
/* Variables de couleurs */
:root {
    --primary: #3498db;
    --secondary: #e74c3c;
    --success: #2ecc71;
    --warning: #f39c12;
    --dark: #2c3e50;
    --light: #ecf0f1;
    
    --gradient-hero: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    --gradient-sunset: linear-gradient(45deg, #ff9a9e 0%, #fecfef 100%);
    --gradient-ocean: linear-gradient(120deg, #89f7fe 0%, #66a6ff 100%);
    
    --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.1);
    --shadow-md: 0 4px 8px rgba(0, 0, 0, 0.15);
    --shadow-lg: 0 8px 16px rgba(0, 0, 0, 0.2);
}

/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: var(--dark);
}

/* Hero Section */
.hero {
    height: 100vh;
    background: var(--gradient-hero);
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
    position: relative;
    overflow: hidden;
}

.hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: 
        radial-gradient(circle at 20% 50%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
        radial-gradient(circle at 80% 20%, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
    animation: float 6s ease-in-out infinite;
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
}

.hero-content {
    z-index: 1;
    max-width: 800px;
    padding: 2rem;
}

.hero h1 {
    font-size: 3.5rem;
    margin-bottom: 1rem;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.hero p {
    font-size: 1.2rem;
    margin-bottom: 2rem;
    opacity: 0.9;
}

/* Boutons */
.btn {
    display: inline-block;
    padding: 12px 30px;
    border: none;
    border-radius: 50px;
    font-size: 1rem;
    font-weight: 600;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: var(--shadow-md);
}

.btn-primary {
    background: white;
    color: var(--primary);
}

.btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: var(--shadow-lg);
}

/* Sections */
main {
    padding: 4rem 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

section {
    margin-bottom: 4rem;
}

section h2 {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: var(--dark);
}

/* Showcase couleurs */
.color-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
}

.color-card {
    padding: 2rem;
    border-radius: 15px;
    text-align: center;
    color: white;
    box-shadow: var(--shadow-md);
    transition: transform 0.3s ease;
}

.color-card:hover {
    transform: translateY(-5px);
}

.color-card h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
}

.color-card.primary { background: var(--primary); }
.color-card.secondary { background: var(--secondary); }
.color-card.success { background: var(--success); }
.color-card.warning { background: var(--warning); }

/* Showcase dégradés */
.gradient-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.gradient-card {
    height: 200px;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 1.5rem;
    font-weight: bold;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
    box-shadow: var(--shadow-md);
    transition: transform 0.3s ease;
}

.gradient-card:hover {
    transform: scale(1.05);
}

.gradient-card.linear {
    background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
}

.gradient-card.radial {
    background: radial-gradient(circle, #ff9a9e, #fecfef);
}

.gradient-card.conic {
    background: conic-gradient(
        from 0deg,
        #ff6b6b,
        #4ecdc4,
        #45b7d1,
        #96ceb4,
        #ffeaa7,
        #ff6b6b
    );
}

/* Arrière-plans créatifs */
.background-showcase {
    margin-top: 4rem;
}

.bg-pattern {
    height: 300px;
    background: 
        linear-gradient(45deg, rgba(52, 152, 219, 0.8), rgba(155, 89, 182, 0.8)),
        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="2" fill="white" opacity="0.3"/></svg>');
    background-size: 50px 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
    border-radius: 15px;
    box-shadow: var(--shadow-lg);
}

.bg-pattern h2 {
    color: white;
    margin-bottom: 1rem;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

/* Footer */
.footer {
    background: var(--dark);
    color: white;
    text-align: center;
    padding: 2rem;
    margin-top: 4rem;
}

/* Responsive */
@media (max-width: 768px) {
    .hero h1 {
        font-size: 2.5rem;
    }
    
    .color-grid,
    .gradient-grid {
        grid-template-columns: 1fr;
    }
    
    main {
        padding: 2rem 1rem;
    }
}

/* Accessibilité */
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}

/* Mode sombre */
@media (prefers-color-scheme: dark) {
    :root {
        --dark: #ecf0f1;
        --light: #2c3e50;
    }
    
    body {
        background: #1a1a1a;
        color: var(--dark);
    }
}
```

## ♿ Accessibilité des couleurs

### Contraste suffisant

```css
/* Bon contraste */
.good-contrast {
    background: #000000;
    color: #ffffff; /* Ratio 21:1 */
}

/* Contraste insuffisant */
.bad-contrast {
    background: #cccccc;
    color: #dddddd; /* Ratio trop faible */
}
```

### Test de contraste

```css
/* Utiliser des outils comme WebAIM Contrast Checker */
.accessible-button {
    background: #1976d2;
    color: #ffffff; /* Ratio 4.5:1 minimum */
    border: 2px solid transparent;
}

.accessible-button:focus {
    outline: 2px solid #ff4081;
    outline-offset: 2px;
}
```

## ✅ Exercice pratique

1. Créez une page showcasant :
   - Palette de couleurs cohérente
   - Dégradés linéaires et radiaux
   - Arrière-plans avec images
   - Effets de hover et transitions

2. Utilisez :
   - Variables CSS pour les couleurs
   - Différents formats de couleurs
   - Arrière-plans multiples
   - Dégradés créatifs

3. Testez l'accessibilité des contrastes

## 🔍 Bonnes pratiques

- **Créez une palette cohérente** avec variables CSS
- **Testez les contrastes** pour l'accessibilité
- **Optimisez les performances** (évitez les images trop lourdes)
- **Pensez au mode sombre** avec prefers-color-scheme
- **Utilisez des fallbacks** pour les navigateurs anciens

## 🔗 Ressources supplémentaires

- [Adobe Color](https://color.adobe.com/)
- [Coolors](https://coolors.co/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Gradient Generator](https://cssgradient.io/)

---

**Temps estimé :** 3 heures  
**Prochaine étape :** [Module 5 - Modèle de boîte](../05-boite-modele/)