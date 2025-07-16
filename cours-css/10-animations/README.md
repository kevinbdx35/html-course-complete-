# Module 10 : Transitions et animations CSS

## 🎯 Objectifs du module

- Maîtriser les transitions CSS
- Créer des animations avec @keyframes
- Utiliser les transforms 2D et 3D
- Optimiser les performances d'animation
- Respecter l'accessibilité

## ⚡ Transitions CSS

### Propriétés de transition

```css
/* Transition simple */
.element {
    background: blue;
    transition: background 0.3s ease;
}

.element:hover {
    background: red;
}

/* Transition multiple */
.element {
    width: 100px;
    height: 100px;
    background: blue;
    transform: scale(1);
    transition: 
        background 0.3s ease,
        transform 0.2s ease-in-out,
        width 0.5s linear;
}

.element:hover {
    background: red;
    transform: scale(1.1);
    width: 120px;
}

/* Transition sur toutes les propriétés */
.element {
    transition: all 0.3s ease;
}
```

### Propriétés de timing

```css
/* Différentes courbes d'animation */
.ease { transition: all 0.3s ease; }
.ease-in { transition: all 0.3s ease-in; }
.ease-out { transition: all 0.3s ease-out; }
.ease-in-out { transition: all 0.3s ease-in-out; }
.linear { transition: all 0.3s linear; }

/* Courbes personnalisées */
.custom {
    transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

/* Délai de transition */
.delayed {
    transition: background 0.3s ease 0.1s;
    /* propriété durée timing délai */
}
```

## 🎬 Animations avec @keyframes

### Création d'animations

```css
/* Définition de l'animation */
@keyframes slideIn {
    from {
        transform: translateX(-100%);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}

/* Animation avec pourcentages */
@keyframes bounce {
    0% {
        transform: translateY(0);
    }
    25% {
        transform: translateY(-20px);
    }
    50% {
        transform: translateY(0);
    }
    75% {
        transform: translateY(-10px);
    }
    100% {
        transform: translateY(0);
    }
}

/* Application de l'animation */
.slide-element {
    animation: slideIn 0.5s ease-out;
}

.bounce-element {
    animation: bounce 1s ease-in-out infinite;
}
```

### Propriétés d'animation

```css
.animated-element {
    animation-name: slideIn;
    animation-duration: 0.5s;
    animation-timing-function: ease-out;
    animation-delay: 0.2s;
    animation-iteration-count: 2;
    animation-direction: alternate;
    animation-fill-mode: both;
    animation-play-state: running;
}

/* Raccourci */
.animated-element {
    animation: slideIn 0.5s ease-out 0.2s 2 alternate both running;
    /* name duration timing delay iteration direction fill-mode play-state */
}
```

### Valeurs des propriétés

```css
/* Animation-iteration-count */
.once { animation-iteration-count: 1; }
.infinite { animation-iteration-count: infinite; }
.three-times { animation-iteration-count: 3; }

/* Animation-direction */
.normal { animation-direction: normal; }
.reverse { animation-direction: reverse; }
.alternate { animation-direction: alternate; }
.alternate-reverse { animation-direction: alternate-reverse; }

/* Animation-fill-mode */
.none { animation-fill-mode: none; }
.forwards { animation-fill-mode: forwards; }
.backwards { animation-fill-mode: backwards; }
.both { animation-fill-mode: both; }

/* Animation-play-state */
.running { animation-play-state: running; }
.paused { animation-play-state: paused; }
```

## 🔄 Transformations CSS

### Transforms 2D

```css
/* Translation */
.translate {
    transform: translate(50px, 100px);
    transform: translateX(50px);
    transform: translateY(100px);
}

/* Rotation */
.rotate {
    transform: rotate(45deg);
    transform: rotate(-90deg);
}

/* Échelle */
.scale {
    transform: scale(1.5);        /* Uniforme */
    transform: scale(2, 0.5);     /* X, Y différents */
    transform: scaleX(2);         /* Horizontal seulement */
    transform: scaleY(0.5);       /* Vertical seulement */
}

/* Inclinaison */
.skew {
    transform: skew(20deg, 10deg);
    transform: skewX(20deg);
    transform: skewY(10deg);
}

/* Transformations combinées */
.combined {
    transform: translate(50px, 100px) rotate(45deg) scale(1.2);
}
```

### Transforms 3D

```css
/* Perspective */
.perspective-container {
    perspective: 1000px;
    perspective-origin: center center;
}

/* Transformations 3D */
.transform-3d {
    transform: translateZ(50px);
    transform: translate3d(50px, 100px, 25px);
    transform: rotateX(45deg);
    transform: rotateY(45deg);
    transform: rotateZ(45deg);
    transform: rotate3d(1, 1, 0, 45deg);
    transform: scale3d(1.5, 1.5, 1.5);
}

/* Transform-style pour les enfants 3D */
.preserve-3d {
    transform-style: preserve-3d;
}

.flat {
    transform-style: flat;
}

/* Backface-visibility */
.hidden-back {
    backface-visibility: hidden;
}

.visible-back {
    backface-visibility: visible;
}
```

## 🎨 Animations pratiques

### Animation de chargement

```css
@keyframes spin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

.loader {
    width: 40px;
    height: 40px;
    border: 4px solid #f3f3f3;
    border-top: 4px solid #3498db;
    border-radius: 50%;
    animation: spin 1s linear infinite;
}

@keyframes pulse {
    0%, 100% {
        transform: scale(1);
        opacity: 1;
    }
    50% {
        transform: scale(1.1);
        opacity: 0.7;
    }
}

.pulse-loader {
    width: 40px;
    height: 40px;
    background: #3498db;
    border-radius: 50%;
    animation: pulse 2s ease-in-out infinite;
}
```

### Animation de texte

```css
@keyframes typewriter {
    from {
        width: 0;
    }
    to {
        width: 100%;
    }
}

@keyframes blink {
    50% {
        border-color: transparent;
    }
}

.typewriter {
    overflow: hidden;
    border-right: 2px solid orange;
    white-space: nowrap;
    margin: 0 auto;
    letter-spacing: 0.15em;
    animation: 
        typewriter 3.5s steps(40, end),
        blink 0.75s step-end infinite;
}

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

.fade-in-text {
    animation: fadeInUp 0.6s ease-out;
}
```

### Animation de cartes

```css
.card {
    transition: all 0.3s ease;
    transform-origin: center;
    cursor: pointer;
}

.card:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

/* Animation flip */
.flip-card {
    perspective: 1000px;
    width: 300px;
    height: 200px;
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.flip-card-back {
    transform: rotateY(180deg);
    background: #2c3e50;
    color: white;
}
```

## 🌟 Animations avancées

### Animation de particules

```css
@keyframes float {
    0%, 100% {
        transform: translateY(0) rotate(0deg);
    }
    33% {
        transform: translateY(-30px) rotate(120deg);
    }
    66% {
        transform: translateY(30px) rotate(240deg);
    }
}

.particle {
    position: absolute;
    width: 10px;
    height: 10px;
    background: #3498db;
    border-radius: 50%;
    animation: float 3s ease-in-out infinite;
}

.particle:nth-child(2) {
    animation-delay: 0.5s;
    left: 20%;
}

.particle:nth-child(3) {
    animation-delay: 1s;
    left: 40%;
}
```

### Animation de morphing

```css
@keyframes morph {
    0% {
        border-radius: 50%;
        background: #e74c3c;
    }
    25% {
        border-radius: 0;
        background: #f39c12;
    }
    50% {
        border-radius: 50% 0;
        background: #2ecc71;
    }
    75% {
        border-radius: 0 50%;
        background: #3498db;
    }
    100% {
        border-radius: 50%;
        background: #e74c3c;
    }
}

.morphing-shape {
    width: 100px;
    height: 100px;
    animation: morph 4s ease-in-out infinite;
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
    <title>Animations CSS - Showcase</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Header animé -->
    <header class="animated-header">
        <div class="container">
            <h1 class="logo slide-in-left">AnimationCSS</h1>
            <nav class="nav">
                <a href="#transitions" class="nav-link slide-in-right" style="--delay: 0.1s">Transitions</a>
                <a href="#keyframes" class="nav-link slide-in-right" style="--delay: 0.2s">Keyframes</a>
                <a href="#transforms" class="nav-link slide-in-right" style="--delay: 0.3s">Transforms</a>
                <a href="#examples" class="nav-link slide-in-right" style="--delay: 0.4s">Exemples</a>
            </nav>
        </div>
    </header>

    <!-- Hero avec animation de texte -->
    <section class="hero">
        <div class="container">
            <h2 class="hero-title typewriter">Maîtrisez les animations CSS</h2>
            <p class="hero-subtitle fade-in-up">Créez des expériences utilisateur exceptionnelles</p>
            <div class="hero-buttons fade-in-up" style="--delay: 0.5s">
                <button class="btn btn-primary animated-btn">Commencer</button>
                <button class="btn btn-secondary animated-btn">Voir les exemples</button>
            </div>
        </div>
        
        <!-- Particules animées -->
        <div class="particles">
            <div class="particle"></div>
            <div class="particle"></div>
            <div class="particle"></div>
            <div class="particle"></div>
            <div class="particle"></div>
        </div>
    </section>

    <!-- Section transitions -->
    <section id="transitions" class="section">
        <div class="container">
            <h2 class="section-title">Transitions</h2>
            <div class="demo-grid">
                <div class="demo-card">
                    <h3>Hover Effects</h3>
                    <div class="transition-examples">
                        <div class="transition-box hover-scale">Scale</div>
                        <div class="transition-box hover-rotate">Rotate</div>
                        <div class="transition-box hover-slide">Slide</div>
                        <div class="transition-box hover-color">Color</div>
                    </div>
                </div>
                
                <div class="demo-card">
                    <h3>Boutons animés</h3>
                    <div class="button-examples">
                        <button class="animated-btn btn-hover-fill">Fill Effect</button>
                        <button class="animated-btn btn-hover-bounce">Bounce</button>
                        <button class="animated-btn btn-hover-shake">Shake</button>
                        <button class="animated-btn btn-hover-glow">Glow</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section keyframes -->
    <section id="keyframes" class="section alternate">
        <div class="container">
            <h2 class="section-title">Animations Keyframes</h2>
            <div class="demo-grid">
                <div class="demo-card">
                    <h3>Loaders</h3>
                    <div class="loader-examples">
                        <div class="loader spinner"></div>
                        <div class="loader pulse"></div>
                        <div class="loader dots">
                            <div class="dot"></div>
                            <div class="dot"></div>
                            <div class="dot"></div>
                        </div>
                        <div class="loader wave">
                            <div class="bar"></div>
                            <div class="bar"></div>
                            <div class="bar"></div>
                            <div class="bar"></div>
                        </div>
                    </div>
                </div>
                
                <div class="demo-card">
                    <h3>Formes animées</h3>
                    <div class="shape-examples">
                        <div class="morphing-shape"></div>
                        <div class="floating-shape"></div>
                        <div class="rotating-cube">
                            <div class="face front">1</div>
                            <div class="face back">2</div>
                            <div class="face right">3</div>
                            <div class="face left">4</div>
                            <div class="face top">5</div>
                            <div class="face bottom">6</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section transforms -->
    <section id="transforms" class="section">
        <div class="container">
            <h2 class="section-title">Transformations 3D</h2>
            <div class="demo-grid">
                <div class="demo-card">
                    <h3>Carte flip</h3>
                    <div class="flip-card">
                        <div class="flip-card-inner">
                            <div class="flip-card-front">
                                <h4>Front</h4>
                                <p>Survolez pour voir l'effet flip</p>
                            </div>
                            <div class="flip-card-back">
                                <h4>Back</h4>
                                <p>Animation 3D réussie !</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="demo-card">
                    <h3>Galerie 3D</h3>
                    <div class="gallery-3d">
                        <div class="gallery-item">
                            <img src="https://picsum.photos/200/150?random=1" alt="Image 1">
                        </div>
                        <div class="gallery-item">
                            <img src="https://picsum.photos/200/150?random=2" alt="Image 2">
                        </div>
                        <div class="gallery-item">
                            <img src="https://picsum.photos/200/150?random=3" alt="Image 3">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section exemples avancés -->
    <section id="examples" class="section alternate">
        <div class="container">
            <h2 class="section-title">Exemples avancés</h2>
            <div class="advanced-examples">
                
                <!-- Animation on scroll -->
                <div class="scroll-animation-demo">
                    <h3>Animation au scroll</h3>
                    <div class="scroll-items">
                        <div class="scroll-item" data-animation="slideInLeft">Slide In Left</div>
                        <div class="scroll-item" data-animation="slideInRight">Slide In Right</div>
                        <div class="scroll-item" data-animation="fadeInUp">Fade In Up</div>
                        <div class="scroll-item" data-animation="zoomIn">Zoom In</div>
                    </div>
                </div>
                
                <!-- Microinteractions -->
                <div class="microinteractions-demo">
                    <h3>Microinteractions</h3>
                    <div class="micro-examples">
                        <button class="like-btn">
                            <span class="heart">♥</span>
                            <span class="text">Like</span>
                        </button>
                        <div class="toggle-switch">
                            <input type="checkbox" id="toggle">
                            <label for="toggle"></label>
                        </div>
                        <div class="progress-ring">
                            <svg width="100" height="100">
                                <circle cx="50" cy="50" r="40" stroke="#e6e6e6" stroke-width="8" fill="none"/>
                                <circle cx="50" cy="50" r="40" stroke="#3498db" stroke-width="8" fill="none" 
                                        stroke-dasharray="251.2" stroke-dashoffset="62.8" class="progress-circle"/>
                            </svg>
                            <span class="progress-text">75%</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Controls pour les animations -->
    <div class="animation-controls">
        <button id="pauseAll">⏸️ Pause All</button>
        <button id="playAll">▶️ Play All</button>
        <button id="resetAll">🔄 Reset All</button>
    </div>

    <script>
        // Animation controls
        const pauseBtn = document.getElementById('pauseAll');
        const playBtn = document.getElementById('playAll');
        const resetBtn = document.getElementById('resetAll');
        
        pauseBtn.addEventListener('click', () => {
            document.body.style.animationPlayState = 'paused';
            document.querySelectorAll('*').forEach(el => {
                el.style.animationPlayState = 'paused';
            });
        });
        
        playBtn.addEventListener('click', () => {
            document.body.style.animationPlayState = 'running';
            document.querySelectorAll('*').forEach(el => {
                el.style.animationPlayState = 'running';
            });
        });
        
        resetBtn.addEventListener('click', () => {
            window.location.reload();
        });
        
        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate');
                }
            });
        }, observerOptions);
        
        document.querySelectorAll('.scroll-item').forEach(item => {
            observer.observe(item);
        });
    </script>
</body>
</html>
```

**CSS :**
```css
/* Variables et base */
:root {
    --primary: #3498db;
    --secondary: #e74c3c;
    --success: #2ecc71;
    --warning: #f39c12;
    --dark: #2c3e50;
    --light: #ecf0f1;
    --white: #ffffff;
    
    --gradient-primary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    --gradient-secondary: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    
    --shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    --shadow-hover: 0 8px 25px rgba(0, 0, 0, 0.2);
    
    --animation-duration: 0.6s;
    --animation-easing: cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: var(--dark);
    background: var(--white);
    overflow-x: hidden;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
}

/* Animations de base */
@keyframes slideInLeft {
    from {
        opacity: 0;
        transform: translateX(-100px);
    }
    to {
        opacity: 1;
        transform: translateX(0);
    }
}

@keyframes slideInRight {
    from {
        opacity: 0;
        transform: translateX(100px);
    }
    to {
        opacity: 1;
        transform: translateX(0);
    }
}

@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(50px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes zoomIn {
    from {
        opacity: 0;
        transform: scale(0.5);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}

/* Classes d'animation */
.slide-in-left {
    animation: slideInLeft var(--animation-duration) var(--animation-easing);
    animation-delay: var(--delay, 0s);
}

.slide-in-right {
    animation: slideInRight var(--animation-duration) var(--animation-easing);
    animation-delay: var(--delay, 0s);
}

.fade-in-up {
    animation: fadeInUp var(--animation-duration) var(--animation-easing);
    animation-delay: var(--delay, 0s);
}

/* Header animé */
.animated-header {
    background: var(--gradient-primary);
    color: white;
    padding: 1rem 0;
    box-shadow: var(--shadow);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.animated-header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-size: 2rem;
    font-weight: bold;
}

.nav {
    display: flex;
    gap: 2rem;
}

.nav-link {
    color: white;
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.nav-link::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: rgba(255, 255, 255, 0.2);
    transition: left 0.3s ease;
}

.nav-link:hover::before {
    left: 0;
}

.nav-link:hover {
    transform: translateY(-2px);
}

/* Hero section */
.hero {
    min-height: 80vh;
    background: var(--gradient-secondary);
    color: white;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
}

.hero .container {
    text-align: center;
    z-index: 2;
}

/* Animation typewriter */
@keyframes typewriter {
    from { width: 0; }
    to { width: 100%; }
}

@keyframes blink {
    50% { border-color: transparent; }
}

.typewriter {
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 1rem;
    overflow: hidden;
    border-right: 3px solid white;
    white-space: nowrap;
    margin: 0 auto 1rem auto;
    letter-spacing: 0.1em;
    animation: 
        typewriter 2s steps(30, end),
        blink 0.75s step-end infinite;
    max-width: fit-content;
}

.hero-subtitle {
    font-size: 1.3rem;
    margin-bottom: 2rem;
    opacity: 0.9;
}

.hero-buttons {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
}

/* Boutons animés */
.btn {
    padding: 1rem 2rem;
    border: none;
    border-radius: 50px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
    z-index: 1;
}

.btn-primary {
    background: white;
    color: var(--primary);
}

.btn-secondary {
    background: transparent;
    color: white;
    border: 2px solid white;
}

.animated-btn {
    transform: perspective(1px) translateZ(0);
    transition: all 0.3s ease;
}

.animated-btn:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-hover);
}

.animated-btn:active {
    transform: translateY(0);
}

/* Particules */
.particles {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
}

@keyframes float {
    0%, 100% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
    }
    50% {
        transform: translateY(-100px) rotate(180deg);
        opacity: 0.5;
    }
}

.particle {
    position: absolute;
    width: 10px;
    height: 10px;
    background: rgba(255, 255, 255, 0.7);
    border-radius: 50%;
    animation: float 6s ease-in-out infinite;
}

.particle:nth-child(1) { left: 10%; animation-delay: 0s; }
.particle:nth-child(2) { left: 20%; animation-delay: 1s; }
.particle:nth-child(3) { left: 30%; animation-delay: 2s; }
.particle:nth-child(4) { left: 80%; animation-delay: 0.5s; }
.particle:nth-child(5) { left: 90%; animation-delay: 1.5s; }

/* Sections */
.section {
    padding: 4rem 0;
}

.section.alternate {
    background: var(--light);
}

.section-title {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 3rem;
    color: var(--dark);
}

.demo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: 2rem;
}

.demo-card {
    background: white;
    padding: 2rem;
    border-radius: 15px;
    box-shadow: var(--shadow);
    transition: transform 0.3s ease;
}

.demo-card:hover {
    transform: translateY(-5px);
}

.demo-card h3 {
    margin-bottom: 1.5rem;
    color: var(--dark);
    text-align: center;
}

/* Exemples de transitions */
.transition-examples {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
}

.transition-box {
    width: 100px;
    height: 100px;
    background: var(--primary);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    cursor: pointer;
    transition: all 0.3s ease;
    margin: 0 auto;
}

.hover-scale:hover { transform: scale(1.2); }
.hover-rotate:hover { transform: rotate(45deg); }
.hover-slide:hover { transform: translateX(20px); }
.hover-color:hover { background: var(--secondary); }

/* Boutons avec effets avancés */
.button-examples {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
}

.btn-hover-fill {
    background: var(--primary);
    color: white;
    position: relative;
    z-index: 1;
}

.btn-hover-fill::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 0;
    height: 100%;
    background: var(--secondary);
    transition: width 0.3s ease;
    z-index: -1;
}

.btn-hover-fill:hover::before {
    width: 100%;
}

@keyframes bounce {
    0%, 20%, 60%, 100% { transform: translateY(0); }
    40% { transform: translateY(-10px); }
    80% { transform: translateY(-5px); }
}

.btn-hover-bounce:hover {
    animation: bounce 0.6s ease;
}

@keyframes shake {
    0%, 100% { transform: translateX(0); }
    10%, 30%, 50%, 70%, 90% { transform: translateX(-5px); }
    20%, 40%, 60%, 80% { transform: translateX(5px); }
}

.btn-hover-shake:hover {
    animation: shake 0.6s ease;
}

@keyframes glow {
    0%, 100% { box-shadow: 0 0 5px var(--primary); }
    50% { box-shadow: 0 0 20px var(--primary), 0 0 30px var(--primary); }
}

.btn-hover-glow:hover {
    animation: glow 1.5s ease-in-out infinite;
}

/* Loaders */
.loader-examples {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
    text-align: center;
}

@keyframes spin {
    to { transform: rotate(360deg); }
}

.spinner {
    width: 40px;
    height: 40px;
    border: 4px solid var(--light);
    border-top: 4px solid var(--primary);
    border-radius: 50%;
    animation: spin 1s linear infinite;
    margin: 0 auto;
}

@keyframes pulse {
    0%, 100% {
        transform: scale(1);
        opacity: 1;
    }
    50% {
        transform: scale(1.1);
        opacity: 0.7;
    }
}

.pulse {
    width: 40px;
    height: 40px;
    background: var(--primary);
    border-radius: 50%;
    animation: pulse 2s ease-in-out infinite;
    margin: 0 auto;
}

.dots {
    display: flex;
    gap: 5px;
    justify-content: center;
}

@keyframes dot-bounce {
    0%, 80%, 100% { transform: scale(0); }
    40% { transform: scale(1); }
}

.dot {
    width: 10px;
    height: 10px;
    background: var(--primary);
    border-radius: 50%;
    animation: dot-bounce 1.4s ease-in-out infinite;
}

.dot:nth-child(1) { animation-delay: -0.32s; }
.dot:nth-child(2) { animation-delay: -0.16s; }

.wave {
    display: flex;
    gap: 3px;
    justify-content: center;
    align-items: end;
    height: 40px;
}

@keyframes wave-animation {
    0%, 40%, 100% { transform: scaleY(0.4); }
    20% { transform: scaleY(1); }
}

.bar {
    width: 6px;
    height: 100%;
    background: var(--primary);
    animation: wave-animation 1.2s ease-in-out infinite;
}

.bar:nth-child(1) { animation-delay: 0s; }
.bar:nth-child(2) { animation-delay: 0.1s; }
.bar:nth-child(3) { animation-delay: 0.2s; }
.bar:nth-child(4) { animation-delay: 0.3s; }

/* Formes animées */
.shape-examples {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
    min-height: 200px;
}

@keyframes morph {
    0% {
        border-radius: 50%;
        background: var(--primary);
        transform: rotate(0deg);
    }
    25% {
        border-radius: 0;
        background: var(--secondary);
        transform: rotate(90deg);
    }
    50% {
        border-radius: 50% 0;
        background: var(--success);
        transform: rotate(180deg);
    }
    75% {
        border-radius: 0 50%;
        background: var(--warning);
        transform: rotate(270deg);
    }
    100% {
        border-radius: 50%;
        background: var(--primary);
        transform: rotate(360deg);
    }
}

.morphing-shape {
    width: 80px;
    height: 80px;
    animation: morph 4s ease-in-out infinite;
}

@keyframes floating {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

.floating-shape {
    width: 80px;
    height: 80px;
    background: var(--gradient-primary);
    border-radius: 50%;
    animation: floating 3s ease-in-out infinite;
}

/* Cube 3D */
.rotating-cube {
    width: 80px;
    height: 80px;
    position: relative;
    transform-style: preserve-3d;
    animation: rotateCube 4s linear infinite;
}

@keyframes rotateCube {
    0% { transform: rotateX(0) rotateY(0); }
    100% { transform: rotateX(360deg) rotateY(360deg); }
}

.face {
    position: absolute;
    width: 80px;
    height: 80px;
    background: var(--primary);
    border: 2px solid var(--dark);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    color: white;
}

.front { transform: rotateY(0deg) translateZ(40px); }
.back { transform: rotateY(180deg) translateZ(40px); }
.right { transform: rotateY(90deg) translateZ(40px); }
.left { transform: rotateY(-90deg) translateZ(40px); }
.top { transform: rotateX(90deg) translateZ(40px); }
.bottom { transform: rotateX(-90deg) translateZ(40px); }

/* Flip card */
.flip-card {
    background: transparent;
    width: 300px;
    height: 200px;
    perspective: 1000px;
    margin: 0 auto;
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
    border-radius: 15px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 2rem;
}

.flip-card-front {
    background: var(--gradient-primary);
    color: white;
}

.flip-card-back {
    background: var(--gradient-secondary);
    color: white;
    transform: rotateY(180deg);
}

/* Galerie 3D */
.gallery-3d {
    display: flex;
    justify-content: center;
    align-items: center;
    perspective: 1000px;
    height: 200px;
}

.gallery-item {
    margin: 0 -50px;
    transition: all 0.3s ease;
    transform: rotateY(0deg);
}

.gallery-item:nth-child(1) {
    transform: rotateY(-20deg) translateZ(-50px);
}

.gallery-item:nth-child(3) {
    transform: rotateY(20deg) translateZ(-50px);
}

.gallery-item:hover {
    transform: rotateY(0deg) translateZ(50px) scale(1.1);
    z-index: 10;
}

.gallery-item img {
    width: 150px;
    height: 100px;
    object-fit: cover;
    border-radius: 10px;
    box-shadow: var(--shadow);
}

/* Animations au scroll */
.scroll-animation-demo {
    margin-bottom: 3rem;
}

.scroll-items {
    display: grid;
    gap: 2rem;
}

.scroll-item {
    padding: 2rem;
    background: white;
    border-radius: 10px;
    box-shadow: var(--shadow);
    text-align: center;
    font-size: 1.2rem;
    font-weight: 600;
    opacity: 0;
    transform: translateY(50px);
    transition: all 0.6s ease;
}

.scroll-item.animate {
    opacity: 1;
    transform: translateY(0);
}

/* Microinteractions */
.microinteractions-demo {
    margin-bottom: 3rem;
}

.micro-examples {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
}

/* Like button */
.like-btn {
    background: none;
    border: 2px solid var(--secondary);
    padding: 1rem 2rem;
    border-radius: 50px;
    cursor: pointer;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.like-btn:hover {
    background: var(--secondary);
    color: white;
}

.like-btn:hover .heart {
    animation: heartBeat 0.6s ease;
}

@keyframes heartBeat {
    0%, 100% { transform: scale(1); }
    25%, 75% { transform: scale(1.2); }
    50% { transform: scale(1.4); }
}

/* Toggle switch */
.toggle-switch {
    position: relative;
    display: inline-block;
}

.toggle-switch input {
    opacity: 0;
    width: 0;
    height: 0;
}

.toggle-switch label {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 30px;
    background: #ccc;
    border-radius: 30px;
    cursor: pointer;
    transition: background 0.3s ease;
}

.toggle-switch label::after {
    content: '';
    position: absolute;
    width: 26px;
    height: 26px;
    border-radius: 50%;
    background: white;
    top: 2px;
    left: 2px;
    transition: transform 0.3s ease;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.toggle-switch input:checked + label {
    background: var(--success);
}

.toggle-switch input:checked + label::after {
    transform: translateX(30px);
}

/* Progress ring */
.progress-ring {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
}

.progress-circle {
    transition: stroke-dashoffset 0.5s ease;
    transform: rotate(-90deg);
    transform-origin: 50% 50%;
}

.progress-text {
    position: absolute;
    font-size: 1.2rem;
    font-weight: bold;
    color: var(--primary);
}

/* Controls d'animation */
.animation-controls {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    display: flex;
    gap: 0.5rem;
    z-index: 1000;
}

.animation-controls button {
    background: var(--dark);
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    cursor: pointer;
    font-size: 0.9rem;
    transition: background 0.3s ease;
}

.animation-controls button:hover {
    background: var(--primary);
}

/* Responsive */
@media (max-width: 768px) {
    .demo-grid {
        grid-template-columns: 1fr;
    }
    
    .transition-examples,
    .button-examples,
    .loader-examples {
        grid-template-columns: 1fr;
        gap: 1rem;
    }
    
    .shape-examples {
        flex-direction: column;
    }
    
    .micro-examples {
        flex-direction: column;
    }
    
    .typewriter {
        font-size: 2rem;
    }
    
    .hero-buttons {
        flex-direction: column;
        align-items: center;
    }
    
    .animation-controls {
        flex-direction: column;
        bottom: 1rem;
        right: 1rem;
    }
}

/* Préférences utilisateur */
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
    
    .typewriter {
        border-right: none;
        width: auto;
    }
}

/* Focus pour l'accessibilité */
button:focus,
input:focus,
.nav-link:focus {
    outline: 2px solid var(--primary);
    outline-offset: 2px;
}
```

## ⚡ Performance et optimisation

### Propriétés performantes

```css
/* ✅ Propriétés qui ne déclenchent pas de reflow */
.optimized {
    /* Transform */
    transform: translateX(100px);
    transform: scale(1.2);
    transform: rotate(45deg);
    
    /* Opacity */
    opacity: 0.5;
    
    /* Filter */
    filter: blur(5px);
}

/* ❌ Propriétés coûteuses à éviter */
.expensive {
    /* Position/taille */
    left: 100px;
    width: 200px;
    height: 150px;
    
    /* Box model */
    padding: 20px;
    margin: 15px;
}
```

### Optimisation avec will-change

```css
.will-animate {
    will-change: transform, opacity;
}

.animation-complete {
    will-change: auto; /* Retirer après animation */
}
```

## ♿ Accessibilité

### Respect des préférences utilisateur

```css
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}

@media (prefers-reduced-motion: no-preference) {
    .can-animate {
        animation: slideIn 0.5s ease;
    }
}
```

## ✅ Exercice pratique

1. Créez une page d'animations complète avec :
   - Animations d'entrée au chargement
   - Effets de hover sur les éléments
   - Loaders animés
   - Transformations 3D
   - Microinteractions

2. Implémentez :
   - Contrôles pour pause/play
   - Animations au scroll
   - Respect des préférences utilisateur
   - Performance optimisée

3. Testez :
   - Sur différents appareils
   - Avec les préférences d'accessibilité
   - Performance avec DevTools

## 🔍 Bonnes pratiques

- **Utilisez transform et opacity** pour la performance
- **Respectez prefers-reduced-motion**
- **Évitez d'animer layout et paint**
- **Durées courtes** pour les microinteractions
- **will-change** avec parcimonie

## 🔗 Ressources supplémentaires

- [Animate.css](https://animate.style/)
- [CSS Animation Performance](https://developers.google.com/web/fundamentals/design-and-ux/animations)
- [Cubic Bezier Generator](https://cubic-bezier.com/)
- [Lottie Animations](https://lottiefiles.com/)

---

**Temps estimé :** 4.5 heures  
**Prochaine étape :** [Module 11 - Projet final](../11-projet-final/)