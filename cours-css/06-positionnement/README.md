# Module 6 : Positionnement CSS

## 🎯 Objectifs du module

- Comprendre les différents types de positionnement
- Maîtriser static, relative, absolute, fixed et sticky
- Utiliser les propriétés top, right, bottom, left
- Créer des layouts complexes avec le positionnement

## 📍 Types de positionnement

### Position static (défaut)

```css
/* Positionnement normal dans le flux */
.static {
    position: static;
    /* top, right, bottom, left n'ont aucun effet */
}

/* Comportement par défaut */
.element {
    /* position: static; est implicite */
    display: block;
    margin: 10px;
}
```

### Position relative

```css
/* Positionnement relatif à sa position normale */
.relative {
    position: relative;
    top: 10px;      /* Décale vers le bas */
    left: 20px;     /* Décale vers la droite */
}

/* L'espace original reste réservé */
.relative-example {
    position: relative;
    top: -5px;      /* Décale vers le haut */
    right: 10px;    /* Décale vers la gauche */
}
```

### Position absolute

```css
/* Positionnement absolu par rapport au parent positionné */
.absolute {
    position: absolute;
    top: 50px;
    right: 100px;
}

/* Parent de référence */
.parent {
    position: relative; /* Devient le parent de référence */
    width: 400px;
    height: 300px;
}

.child {
    position: absolute;
    top: 0;       /* Coin supérieur du parent */
    right: 0;     /* Coin droit du parent */
}
```

### Position fixed

```css
/* Positionnement fixe par rapport à la viewport */
.fixed {
    position: fixed;
    top: 0;
    right: 0;
    width: 100px;
    height: 50px;
}

/* Header fixe */
.header-fixed {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
}
```

### Position sticky

```css
/* Positionnement collant */
.sticky {
    position: sticky;
    top: 20px;      /* Distance du haut quand collé */
}

/* Navigation sticky */
.nav-sticky {
    position: sticky;
    top: 0;
    background: white;
    z-index: 100;
}
```

## 🎯 Propriétés de positionnement

### Top, Right, Bottom, Left

```css
/* Positionnement précis */
.positioned {
    position: absolute;
    top: 10px;      /* Distance du haut */
    right: 20px;    /* Distance de la droite */
    bottom: 30px;   /* Distance du bas */
    left: 40px;     /* Distance de la gauche */
}

/* Centrage absolu */
.centered-absolute {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

### Z-index (ordre de superposition)

```css
/* Contrôle de l'ordre d'affichage */
.layer-1 { z-index: 1; }
.layer-2 { z-index: 2; }
.layer-3 { z-index: 3; }

/* Valeurs courantes */
.background { z-index: -1; }
.content { z-index: 1; }
.navigation { z-index: 100; }
.modal { z-index: 1000; }
.tooltip { z-index: 10000; }
```

## 🏗️ Techniques de layout

### Overlay et modal

```css
/* Overlay de fond */
.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1000;
}

/* Modal centrée */
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    border-radius: 8px;
    padding: 2rem;
    z-index: 1001;
    max-width: 500px;
    width: 90%;
}
```

### Header et sidebar fixes

```css
/* Header fixe */
.header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: 60px;
    background: white;
    z-index: 100;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

/* Sidebar fixe */
.sidebar {
    position: fixed;
    top: 60px;  /* Hauteur du header */
    left: 0;
    width: 250px;
    height: calc(100vh - 60px);
    background: #f8f9fa;
    overflow-y: auto;
    z-index: 50;
}

/* Contenu principal */
.main-content {
    margin-top: 60px;     /* Hauteur du header */
    margin-left: 250px;   /* Largeur de la sidebar */
    padding: 2rem;
}
```

### Positionnement de badges

```css
/* Conteneur parent */
.badge-container {
    position: relative;
    display: inline-block;
}

/* Badge positionné */
.badge {
    position: absolute;
    top: -8px;
    right: -8px;
    background: #e74c3c;
    color: white;
    border-radius: 50%;
    width: 20px;
    height: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8rem;
    font-weight: bold;
}
```

## 🎨 Positionnement avancé

### Collage avec sticky

```css
/* En-tête de tableau collant */
.sticky-header {
    position: sticky;
    top: 0;
    background: white;
    z-index: 10;
}

/* Sidebar collante */
.sticky-sidebar {
    position: sticky;
    top: 2rem;
    height: fit-content;
}

/* Footer collant */
.sticky-footer {
    position: sticky;
    bottom: 0;
    background: #f8f9fa;
    padding: 1rem;
}
```

### Positionnement responsive

```css
/* Adaptation mobile */
@media (max-width: 768px) {
    .sidebar {
        position: fixed;
        top: 0;
        left: -250px;  /* Caché par défaut */
        transition: left 0.3s ease;
    }
    
    .sidebar.open {
        left: 0;  /* Affiché quand ouvert */
    }
    
    .main-content {
        margin-left: 0;
    }
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
    <title>Positionnement CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Header fixe -->
    <header class="header">
        <div class="header-content">
            <h1>Mon Site</h1>
            <nav class="nav">
                <a href="#home">Accueil</a>
                <a href="#about">À propos</a>
                <a href="#contact">Contact</a>
            </nav>
            <button class="menu-toggle">☰</button>
        </div>
    </header>

    <!-- Sidebar -->
    <aside class="sidebar">
        <div class="sidebar-content">
            <h3>Navigation</h3>
            <ul>
                <li><a href="#section1">Section 1</a></li>
                <li><a href="#section2">Section 2</a></li>
                <li><a href="#section3">Section 3</a></li>
            </ul>
            
            <div class="sticky-widget">
                <h4>Widget collant</h4>
                <p>Ce widget reste visible pendant le scroll</p>
            </div>
        </div>
    </aside>

    <!-- Contenu principal -->
    <main class="main-content">
        <section id="home" class="section">
            <h2>Démonstration du positionnement</h2>
            
            <!-- Positionnement relatif -->
            <div class="demo-container">
                <h3>Position relative</h3>
                <div class="box static">Position static</div>
                <div class="box relative">Position relative (décalée)</div>
                <div class="box static">Position static</div>
            </div>
            
            <!-- Positionnement absolu -->
            <div class="demo-container">
                <h3>Position absolute</h3>
                <div class="parent-box">
                    <p>Parent avec position relative</p>
                    <div class="child-absolute top-left">Top Left</div>
                    <div class="child-absolute top-right">Top Right</div>
                    <div class="child-absolute bottom-left">Bottom Left</div>
                    <div class="child-absolute bottom-right">Bottom Right</div>
                    <div class="child-absolute centered">Centré</div>
                </div>
            </div>
            
            <!-- Badges -->
            <div class="demo-container">
                <h3>Badges positionnés</h3>
                <div class="badge-examples">
                    <div class="badge-container">
                        <button class="btn">Messages</button>
                        <span class="badge">3</span>
                    </div>
                    <div class="badge-container">
                        <button class="btn">Notifications</button>
                        <span class="badge">12</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="about" class="section">
            <h2>À propos</h2>
            <p>Cette section démontre le positionnement sticky avec la sidebar.</p>
            <p>Scrollez pour voir le comportement des éléments positionnés.</p>
            
            <!-- Contenu long pour tester le scroll -->
            <div class="long-content">
                <h4>Contenu long</h4>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
                <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.</p>
                <p>Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.</p>
            </div>
        </section>

        <section id="contact" class="section">
            <h2>Contact</h2>
            <p>Section de contact avec plus de contenu pour tester le scroll.</p>
            <div class="contact-form">
                <form>
                    <label for="name">Nom :</label>
                    <input type="text" id="name" name="name">
                    
                    <label for="email">Email :</label>
                    <input type="email" id="email" name="email">
                    
                    <label for="message">Message :</label>
                    <textarea id="message" name="message"></textarea>
                    
                    <button type="submit">Envoyer</button>
                </form>
            </div>
        </section>
    </main>

    <!-- Bouton retour en haut -->
    <button class="back-to-top" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">
        ↑
    </button>

    <!-- Modal (caché par défaut) -->
    <div class="modal-overlay" id="modal">
        <div class="modal">
            <button class="modal-close" onclick="closeModal()">&times;</button>
            <h3>Modal d'exemple</h3>
            <p>Ceci est un exemple de modal avec positionnement fixe.</p>
            <button onclick="closeModal()">Fermer</button>
        </div>
    </div>

    <script>
        function closeModal() {
            document.getElementById('modal').style.display = 'none';
        }
        
        // Afficher le modal après 3 secondes
        setTimeout(() => {
            document.getElementById('modal').style.display = 'flex';
        }, 3000);
    </script>
</body>
</html>
```

**CSS :**
```css
/* Reset et base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
    background: #f5f5f5;
}

/* Header fixe */
.header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: 60px;
    background: white;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    z-index: 1000;
}

.header-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
    padding: 0 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

.header h1 {
    color: #2c3e50;
    font-size: 1.5rem;
}

.nav {
    display: flex;
    gap: 2rem;
}

.nav a {
    color: #333;
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s;
}

.nav a:hover {
    color: #3498db;
}

.menu-toggle {
    display: none;
    background: none;
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
}

/* Sidebar */
.sidebar {
    position: fixed;
    top: 60px;
    left: 0;
    width: 250px;
    height: calc(100vh - 60px);
    background: white;
    border-right: 1px solid #e0e0e0;
    overflow-y: auto;
    z-index: 100;
}

.sidebar-content {
    padding: 2rem;
}

.sidebar h3 {
    color: #2c3e50;
    margin-bottom: 1rem;
}

.sidebar ul {
    list-style: none;
    margin-bottom: 2rem;
}

.sidebar li {
    margin-bottom: 0.5rem;
}

.sidebar a {
    color: #666;
    text-decoration: none;
    padding: 0.5rem 0;
    display: block;
    transition: color 0.3s;
}

.sidebar a:hover {
    color: #3498db;
}

/* Widget collant dans la sidebar */
.sticky-widget {
    position: sticky;
    top: 2rem;
    background: #f8f9fa;
    padding: 1rem;
    border-radius: 8px;
    border: 1px solid #e0e0e0;
}

.sticky-widget h4 {
    color: #2c3e50;
    margin-bottom: 0.5rem;
}

/* Contenu principal */
.main-content {
    margin-left: 250px;
    margin-top: 60px;
    padding: 2rem;
    min-height: calc(100vh - 60px);
}

.section {
    margin-bottom: 3rem;
    background: white;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.section h2 {
    color: #2c3e50;
    margin-bottom: 1.5rem;
    font-size: 2rem;
}

/* Démonstrations */
.demo-container {
    margin: 2rem 0;
    padding: 1rem;
    background: #f8f9fa;
    border-radius: 8px;
}

.demo-container h3 {
    color: #34495e;
    margin-bottom: 1rem;
}

/* Boxes pour démonstration */
.box {
    display: inline-block;
    padding: 1rem;
    margin: 0.5rem;
    background: #3498db;
    color: white;
    border-radius: 5px;
    font-weight: bold;
}

.box.static {
    background: #95a5a6;
}

.box.relative {
    position: relative;
    top: 10px;
    left: 20px;
    background: #e74c3c;
}

/* Parent pour démonstration absolute */
.parent-box {
    position: relative;
    width: 400px;
    height: 300px;
    background: #ecf0f1;
    border: 2px solid #bdc3c7;
    border-radius: 8px;
    margin: 1rem 0;
    padding: 1rem;
}

.child-absolute {
    position: absolute;
    padding: 0.5rem;
    background: #2ecc71;
    color: white;
    border-radius: 3px;
    font-size: 0.8rem;
    font-weight: bold;
}

.top-left {
    top: 10px;
    left: 10px;
}

.top-right {
    top: 10px;
    right: 10px;
}

.bottom-left {
    bottom: 10px;
    left: 10px;
}

.bottom-right {
    bottom: 10px;
    right: 10px;
}

.centered {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: #9b59b6;
}

/* Badges */
.badge-examples {
    display: flex;
    gap: 2rem;
    margin: 1rem 0;
}

.badge-container {
    position: relative;
    display: inline-block;
}

.btn {
    background: #3498db;
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    cursor: pointer;
    font-size: 0.9rem;
}

.badge {
    position: absolute;
    top: -8px;
    right: -8px;
    background: #e74c3c;
    color: white;
    border-radius: 50%;
    width: 20px;
    height: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: bold;
}

/* Formulaire */
.contact-form {
    max-width: 500px;
    margin: 2rem 0;
}

.contact-form label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: bold;
}

.contact-form input,
.contact-form textarea {
    width: 100%;
    padding: 0.8rem;
    border: 1px solid #ddd;
    border-radius: 5px;
    margin-bottom: 1rem;
    font-size: 1rem;
}

.contact-form button {
    background: #2ecc71;
    color: white;
    border: none;
    padding: 0.8rem 2rem;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;
}

/* Bouton retour en haut */
.back-to-top {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    width: 50px;
    height: 50px;
    background: #3498db;
    color: white;
    border: none;
    border-radius: 50%;
    font-size: 1.2rem;
    cursor: pointer;
    z-index: 1000;
    transition: all 0.3s;
}

.back-to-top:hover {
    background: #2980b9;
    transform: translateY(-2px);
}

/* Modal */
.modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 2000;
}

.modal {
    position: relative;
    background: white;
    padding: 2rem;
    border-radius: 8px;
    max-width: 500px;
    width: 90%;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

.modal-close {
    position: absolute;
    top: 10px;
    right: 15px;
    background: none;
    border: none;
    font-size: 2rem;
    cursor: pointer;
    color: #999;
}

.modal h3 {
    color: #2c3e50;
    margin-bottom: 1rem;
}

.modal button {
    background: #3498db;
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 1rem;
}

/* Contenu long */
.long-content {
    margin: 2rem 0;
}

.long-content h4 {
    color: #2c3e50;
    margin-bottom: 1rem;
}

.long-content p {
    margin-bottom: 1rem;
    text-align: justify;
}

/* Responsive */
@media (max-width: 768px) {
    .sidebar {
        left: -250px;
        transition: left 0.3s ease;
    }
    
    .sidebar.open {
        left: 0;
    }
    
    .main-content {
        margin-left: 0;
    }
    
    .menu-toggle {
        display: block;
    }
    
    .nav {
        display: none;
    }
    
    .parent-box {
        width: 100%;
        max-width: 350px;
    }
    
    .badge-examples {
        flex-direction: column;
        gap: 1rem;
    }
    
    .back-to-top {
        bottom: 1rem;
        right: 1rem;
        width: 40px;
        height: 40px;
    }
}

/* Animations */
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

.section {
    animation: fadeIn 0.6s ease-out;
}

/* États de focus pour l'accessibilité */
button:focus,
input:focus,
textarea:focus {
    outline: 2px solid #3498db;
    outline-offset: 2px;
}

/* Scrollbar personnalisée */
.sidebar::-webkit-scrollbar {
    width: 6px;
}

.sidebar::-webkit-scrollbar-track {
    background: #f1f1f1;
}

.sidebar::-webkit-scrollbar-thumb {
    background: #c1c1c1;
    border-radius: 3px;
}

.sidebar::-webkit-scrollbar-thumb:hover {
    background: #a8a8a8;
}
```

## ✅ Exercice pratique

1. Créez un layout avec :
   - Header fixe en haut
   - Sidebar collante à gauche
   - Contenu principal scrollable
   - Bouton "retour en haut" fixe

2. Ajoutez des éléments positionnés :
   - Badges sur des boutons
   - Tooltip au survol
   - Modal centré
   - Menu dropdown

3. Rendez le tout responsive

## 🔍 Bonnes pratiques

- **Utilisez relative/absolute** ensemble pour le contrôle précis
- **Évitez position: absolute** pour les layouts principaux
- **Gérez les z-index** avec une échelle cohérente
- **Testez le scroll** sur mobile
- **Attention aux éléments fixes** qui peuvent masquer le contenu

## 🔗 Ressources supplémentaires

- [MDN - Position](https://developer.mozilla.org/fr/docs/Web/CSS/position)
- [CSS Positioning Guide](https://css-tricks.com/almanac/properties/p/position/)
- [Z-Index Explained](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Positioning/Understanding_z_index)

---

**Temps estimé :** 3.5 heures  
**Prochaine étape :** [Module 7 - Flexbox](../07-flexbox/)