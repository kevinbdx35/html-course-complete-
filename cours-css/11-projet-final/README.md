# Module 11 : Projet final CSS

## 🎯 Objectif du projet

Créer un site web complet et moderne qui met en pratique toutes les compétences CSS acquises dans ce cours. Ce projet servira de validation finale de vos connaissances et constituera une pièce maîtresse de votre portfolio.

## 📋 Cahier des charges

### Sujet : Portfolio personnel ou site d'entreprise moderne

Créez un site web professionnel comprenant :

1. **Page d'accueil** (`index.html`)
2. **Page "À propos"** (`about.html`)
3. **Page "Portfolio/Services"** (`portfolio.html`)
4. **Page "Contact"** (`contact.html`)
5. **Page "Blog"** (`blog.html`) - optionnelle

## 🔧 Exigences techniques obligatoires

### 1. Layout et structure
- [x] **CSS Grid** pour la structure générale
- [x] **Flexbox** pour les composants
- [x] **Design responsive** (mobile-first)
- [x] **Navigation sticky/fixed**
- [x] **Layout sémantique** avec HTML5

### 2. Couleurs et design
- [x] **Palette cohérente** avec variables CSS
- [x] **Dégradés CSS** créatifs
- [x] **Mode sombre** avec prefers-color-scheme
- [x] **Contrastes accessibles** (WCAG AA)

### 3. Typographie
- [x] **Google Fonts** ou polices système
- [x] **Hiérarchie typographique** claire
- [x] **Typographie responsive** avec clamp()
- [x] **Lisibilité optimisée**

### 4. Animations et interactions
- [x] **Transitions fluides** sur les interactions
- [x] **Animations d'entrée** au scroll
- [x] **Microinteractions** (boutons, formulaires)
- [x] **Respect de prefers-reduced-motion**

### 5. Responsive design
- [x] **Mobile-first** approach
- [x] **Breakpoints cohérents**
- [x] **Images responsives** (srcset/picture)
- [x] **Touch targets** de 44px minimum

### 6. Performance et accessibilité
- [x] **Validation CSS** sans erreurs
- [x] **Navigation au clavier**
- [x] **Lecteurs d'écran** compatibles
- [x] **Optimisation performance**

## 🎨 Spécifications détaillées

### Page d'accueil
```
┌─────────────────────────────────────┐
│            HEADER/NAV               │
├─────────────────────────────────────┤
│         HERO SECTION                │
│     (Animation d'entrée)            │
├─────────────────────────────────────┤
│        ABOUT PREVIEW                │
│    (Grid 2 colonnes)                │
├─────────────────────────────────────┤
│      SERVICES/SKILLS                │
│    (Grille responsive)              │
├─────────────────────────────────────┤
│       TESTIMONIALS                  │
│     (Carrousel CSS)                 │
├─────────────────────────────────────┤
│        CTA SECTION                  │
├─────────────────────────────────────┤
│          FOOTER                     │
└─────────────────────────────────────┘
```

### Composants requis

#### Navigation
```css
/* Navigation responsive avec hamburger menu */
.navigation {
    position: sticky;
    top: 0;
    z-index: 1000;
    background: var(--bg-primary);
    backdrop-filter: blur(10px);
}

.nav-menu {
    display: flex;
    gap: 2rem;
}

@media (max-width: 768px) {
    .nav-menu {
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        flex-direction: column;
        background: var(--bg-primary);
        transform: translateY(-100%);
        opacity: 0;
        visibility: hidden;
        transition: all 0.3s ease;
    }
    
    .nav-menu.active {
        transform: translateY(0);
        opacity: 1;
        visibility: visible;
    }
}
```

#### Hero section
```css
.hero {
    min-height: 100vh;
    display: grid;
    place-items: center;
    background: linear-gradient(135deg, var(--primary), var(--secondary));
    position: relative;
    overflow: hidden;
}

.hero-content {
    text-align: center;
    color: white;
    animation: fadeInUp 1s ease-out;
}

.hero-title {
    font-size: clamp(2.5rem, 5vw, 4rem);
    font-weight: 700;
    margin-bottom: 1rem;
}
```

#### Grille de services/compétences
```css
.services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin: 4rem 0;
}

.service-card {
    padding: 2rem;
    background: var(--bg-card);
    border-radius: 15px;
    box-shadow: var(--shadow);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    position: relative;
    overflow: hidden;
}

.service-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 4px;
    background: var(--gradient-primary);
    transform: scaleX(0);
    transition: transform 0.3s ease;
}

.service-card:hover::before {
    transform: scaleX(1);
}

.service-card:hover {
    transform: translateY(-10px);
    box-shadow: var(--shadow-hover);
}
```

#### Formulaire de contact
```css
.contact-form {
    max-width: 600px;
    margin: 0 auto;
    padding: 2rem;
    background: var(--bg-card);
    border-radius: 15px;
    box-shadow: var(--shadow);
}

.form-group {
    position: relative;
    margin-bottom: 2rem;
}

.form-input {
    width: 100%;
    padding: 1rem;
    border: 2px solid transparent;
    border-radius: 8px;
    background: var(--bg-input);
    font-size: 1rem;
    transition: all 0.3s ease;
}

.form-input:focus {
    outline: none;
    border-color: var(--primary);
    background: white;
}

.form-label {
    position: absolute;
    top: 1rem;
    left: 1rem;
    color: var(--text-muted);
    transition: all 0.3s ease;
    pointer-events: none;
}

.form-input:focus + .form-label,
.form-input:not(:placeholder-shown) + .form-label {
    top: -0.5rem;
    left: 0.5rem;
    font-size: 0.8rem;
    color: var(--primary);
    background: var(--bg-card);
    padding: 0 0.5rem;
}
```

## 💻 Structure de fichiers

```
projet-final-css/
├── index.html
├── about.html
├── portfolio.html
├── contact.html
├── blog.html (optionnel)
├── css/
│   ├── styles.css
│   ├── variables.css
│   ├── components.css
│   └── responsive.css
├── js/
│   ├── main.js
│   └── animations.js
├── images/
│   ├── hero-bg.jpg
│   ├── about-photo.jpg
│   ├── portfolio/
│   │   ├── project1.jpg
│   │   └── project2.jpg
│   └── icons/
│       ├── skill1.svg
│       └── skill2.svg
├── fonts/ (si polices locales)
└── README.md
```

## 🎯 Fonctionnalités spécifiques

### 1. Système de thème sombre/clair
```css
:root {
    --primary: #667eea;
    --secondary: #764ba2;
    --bg-primary: #ffffff;
    --bg-secondary: #f8f9fa;
    --text-primary: #333333;
    --text-secondary: #666666;
}

[data-theme="dark"] {
    --bg-primary: #1a1a1a;
    --bg-secondary: #2d2d2d;
    --text-primary: #ffffff;
    --text-secondary: #cccccc;
}

@media (prefers-color-scheme: dark) {
    :root {
        --bg-primary: #1a1a1a;
        --bg-secondary: #2d2d2d;
        --text-primary: #ffffff;
        --text-secondary: #cccccc;
    }
}
```

### 2. Animations au scroll
```css
.scroll-reveal {
    opacity: 0;
    transform: translateY(50px);
    transition: all 0.6s ease;
}

.scroll-reveal.active {
    opacity: 1;
    transform: translateY(0);
}

/* JavaScript requis pour l'activation */
```

### 3. Galerie portfolio interactive
```css
.portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
    margin: 3rem 0;
}

.portfolio-item {
    position: relative;
    border-radius: 15px;
    overflow: hidden;
    aspect-ratio: 16/10;
    cursor: pointer;
}

.portfolio-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
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
    padding: 2rem;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.portfolio-item:hover .portfolio-image {
    transform: scale(1.1);
}

.portfolio-item:hover .portfolio-overlay {
    opacity: 1;
}
```

### 4. Composants réutilisables
```css
/* Boutons */
.btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 1rem 2rem;
    border: none;
    border-radius: 50px;
    font-weight: 600;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.btn-primary {
    background: var(--gradient-primary);
    color: white;
}

.btn-outline {
    background: transparent;
    color: var(--primary);
    border: 2px solid var(--primary);
}

/* Cards */
.card {
    background: var(--bg-card);
    border-radius: 15px;
    padding: 2rem;
    box-shadow: var(--shadow);
    transition: all 0.3s ease;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-hover);
}

/* Sections */
.section {
    padding: 5rem 0;
}

.section-title {
    font-size: clamp(2rem, 4vw, 3rem);
    text-align: center;
    margin-bottom: 3rem;
    position: relative;
}

.section-title::after {
    content: '';
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    width: 50px;
    height: 3px;
    background: var(--gradient-primary);
    border-radius: 2px;
}
```

## ✅ Grille d'évaluation (100 points)

### Structure et sémantique (20 points)
- [ ] HTML5 sémantique correct (5 pts)
- [ ] Structure logique et claire (5 pts)
- [ ] Navigation cohérente (5 pts)
- [ ] URLs et liens fonctionnels (5 pts)

### CSS et layout (25 points)
- [ ] CSS Grid utilisé efficacement (8 pts)
- [ ] Flexbox pour les composants (7 pts)
- [ ] Code CSS organisé et commenté (5 pts)
- [ ] Variables CSS utilisées (5 pts)

### Design responsive (20 points)
- [ ] Mobile-first approach (8 pts)
- [ ] Breakpoints cohérents (6 pts)
- [ ] Images responsives (3 pts)
- [ ] Touch targets appropriés (3 pts)

### Animations et interactions (15 points)
- [ ] Transitions fluides (5 pts)
- [ ] Animations d'entrée (5 pts)
- [ ] Microinteractions (3 pts)
- [ ] Performance optimisée (2 pts)

### Accessibilité (10 points)
- [ ] Navigation au clavier (3 pts)
- [ ] Contrastes suffisants (3 pts)
- [ ] Attributs ARIA appropriés (2 pts)
- [ ] Préférences utilisateur respectées (2 pts)

### Créativité et finition (10 points)
- [ ] Design original et attrayant (5 pts)
- [ ] Détails soignés (3 pts)
- [ ] Cohérence visuelle (2 pts)

## 🚀 Étapes de réalisation

### Phase 1 : Planification (2 heures)
1. **Wireframing** : Dessinez la structure de chaque page
2. **Design system** : Définissez couleurs, typographie, espacements
3. **Architecture CSS** : Planifiez l'organisation des fichiers
4. **Contenu** : Rassemblez textes et images

### Phase 2 : Structure HTML (3 heures)
1. **Pages HTML** : Créez la structure sémantique
2. **Navigation** : Implémentez le menu principal
3. **Contenu** : Ajoutez le contenu réel
4. **Formulaires** : Créez les formulaires fonctionnels

### Phase 3 : Styles CSS (8 heures)
1. **Variables et base** : Système de design
2. **Layout principal** : Grid et structure
3. **Composants** : Cards, boutons, formulaires
4. **Responsive** : Adaptation mobile

### Phase 4 : Animations (3 heures)
1. **Transitions** : Effets de hover
2. **Animations** : Entrées et microinteractions
3. **Performance** : Optimisation
4. **Accessibilité** : Préférences utilisateur

### Phase 5 : Finition (4 heures)
1. **Tests** : Différents navigateurs et appareils
2. **Validation** : Code HTML/CSS
3. **Optimisation** : Performance et accessibilité
4. **Documentation** : README et commentaires

## 📝 Livrables

1. **Code source complet** avec tous les fichiers
2. **README.md** détaillé avec :
   - Description du projet
   - Technologies utilisées
   - Instructions d'installation
   - Captures d'écran
   - Défis rencontrés et solutions
3. **Présentation courte** (5 minutes) du projet

## 🎯 Conseils pour réussir

### Organisation
- **Planifiez avant de coder**
- **Utilisez Git** pour le versioning
- **Testez régulièrement** sur différents appareils
- **Validez votre code** en continu

### Bonnes pratiques
- **Mobile-first** toujours
- **Performance** : optimisez images et CSS
- **Accessibilité** : testez avec lecteur d'écran
- **Cohérence** : utilisez un design system

### Inspiration
- [Awwwards](https://www.awwwards.com/)
- [Dribbble](https://dribbble.com/)
- [Behance](https://www.behance.net/)
- [CSS Design Awards](https://www.cssdesignawards.com/)

## 🔧 Outils recommandés

### Développement
- **VS Code** avec extensions CSS
- **Live Server** pour tests locaux
- **DevTools** pour debugging
- **Git** pour versioning

### Design
- **Figma** pour wireframes
- **Coolors** pour palettes
- **Google Fonts** pour typographie
- **Unsplash** pour images

### Validation
- **W3C CSS Validator**
- **WAVE** pour accessibilité
- **Lighthouse** pour performance
- **Can I Use** pour compatibilité

## 🏆 Critères d'excellence

Pour un projet exceptionnel :
- **Innovation** : Techniques CSS créatives
- **Performance** : Temps de chargement < 3s
- **Accessibilité** : Score WAVE parfait
- **Responsive** : Fonctionnel sur tous écrans
- **Code quality** : Clean et maintenable

## 📚 Ressources de référence

### Documentation
- [MDN CSS Reference](https://developer.mozilla.org/fr/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [Web.dev](https://web.dev/)

### Inspiration
- [CodePen](https://codepen.io/)
- [CSS Grid Garden](https://cssgridgarden.com/)
- [Flexbox Froggy](https://flexboxfroggy.com/)

---

**Temps estimé total :** 20-25 heures  
**Date limite :** À définir selon votre progression  
**Présentation :** Prévue après finalisation

**Bonne chance pour votre projet final ! 🚀**