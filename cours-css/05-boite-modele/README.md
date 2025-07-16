# Module 5 : Modèle de boîte (Box Model)

## 🎯 Objectifs du module

- Comprendre le modèle de boîte CSS
- Maîtriser les marges, bordures et padding
- Utiliser box-sizing efficacement
- Contrôler les dimensions des éléments

## 📦 Le modèle de boîte CSS

### Anatomie d'une boîte

```
┌─────────────────────────────────────┐
│               MARGIN                │
│  ┌─────────────────────────────────┐│
│  │             BORDER              ││
│  │  ┌─────────────────────────────┐││
│  │  │           PADDING           │││
│  │  │  ┌─────────────────────────┐│││
│  │  │  │        CONTENT          ││││
│  │  │  │                         ││││
│  │  │  └─────────────────────────┘│││
│  │  └─────────────────────────────┘││
│  └─────────────────────────────────┘│
└─────────────────────────────────────┘
```

### Taille totale d'un élément

```css
/* Calcul de la largeur totale */
.box {
    width: 200px;           /* Contenu */
    padding: 20px;          /* + 40px (20px × 2) */
    border: 5px solid;      /* + 10px (5px × 2) */
    margin: 10px;           /* + 20px (10px × 2) */
}
/* Largeur totale = 200 + 40 + 10 + 20 = 270px */
```

## 📏 Dimensions (Width et Height)

### Propriétés de base

```css
/* Dimensions fixes */
.box-fixed {
    width: 300px;
    height: 200px;
}

/* Dimensions relatives */
.box-relative {
    width: 50%;
    height: 80vh;
}

/* Dimensions minimales et maximales */
.box-minmax {
    min-width: 200px;
    max-width: 800px;
    min-height: 100px;
    max-height: 400px;
}
```

### Unités de dimension

```css
/* Unités absolues */
.absolute-units {
    width: 300px;      /* Pixels */
    height: 2in;       /* Pouces */
    margin: 1cm;       /* Centimètres */
}

/* Unités relatives */
.relative-units {
    width: 50%;        /* Pourcentage du parent */
    height: 2em;       /* Relative à la taille de police */
    padding: 1rem;     /* Relative à la racine */
}

/* Unités viewport */
.viewport-units {
    width: 100vw;      /* Largeur viewport */
    height: 100vh;     /* Hauteur viewport */
    font-size: 5vmin;  /* Plus petite dimension */
}
```

## 🎨 Marges (Margin)

### Syntaxe des marges

```css
/* Marge uniforme */
.margin-all { margin: 20px; }

/* Marges verticales et horizontales */
.margin-vh { margin: 10px 20px; }

/* Marges spécifiques */
.margin-specific { margin: 10px 15px 20px 25px; }
/* top right bottom left */

/* Marges individuelles */
.margin-individual {
    margin-top: 10px;
    margin-right: 15px;
    margin-bottom: 20px;
    margin-left: 25px;
}
```

### Centrage avec marges

```css
/* Centrage horizontal */
.center-horizontal {
    width: 300px;
    margin: 0 auto;
}

/* Centrage vertical et horizontal */
.center-both {
    width: 300px;
    height: 200px;
    margin: auto;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
}
```

### Fusion des marges

```css
/* Les marges verticales fusionnent */
.box1 {
    margin-bottom: 20px;
}

.box2 {
    margin-top: 30px;
}
/* Marge effective entre les deux = 30px (la plus grande) */

/* Éviter la fusion */
.no-collapse {
    padding: 1px 0; /* Force la séparation */
}
```

## 🔲 Bordures (Border)

### Propriétés de bordure

```css
/* Bordure complète */
.border-full {
    border: 2px solid #333;
}

/* Bordures individuelles */
.border-individual {
    border-width: 2px;
    border-style: solid;
    border-color: #333;
}

/* Bordures par côté */
.border-sides {
    border-top: 3px solid red;
    border-right: 2px dashed blue;
    border-bottom: 1px dotted green;
    border-left: 4px double orange;
}
```

### Styles de bordure

```css
/* Différents styles */
.border-solid { border: 2px solid #333; }
.border-dashed { border: 2px dashed #333; }
.border-dotted { border: 2px dotted #333; }
.border-double { border: 4px double #333; }
.border-groove { border: 4px groove #333; }
.border-ridge { border: 4px ridge #333; }
.border-inset { border: 4px inset #333; }
.border-outset { border: 4px outset #333; }
```

### Bordures arrondies

```css
/* Coins arrondis uniformes */
.rounded { border-radius: 10px; }

/* Coins arrondis individuels */
.rounded-custom {
    border-top-left-radius: 10px;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 30px;
    border-bottom-left-radius: 40px;
}

/* Raccourci pour coins opposés */
.rounded-shorthand {
    border-radius: 10px 20px 30px 40px;
    /* top-left top-right bottom-right bottom-left */
}

/* Formes spéciales */
.circle {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}

.pill {
    border-radius: 25px;
}
```

## 🎯 Padding (Espacement interne)

### Syntaxe du padding

```css
/* Padding uniforme */
.padding-all { padding: 20px; }

/* Padding vertical et horizontal */
.padding-vh { padding: 10px 20px; }

/* Padding spécifique */
.padding-specific { padding: 10px 15px 20px 25px; }

/* Padding individuel */
.padding-individual {
    padding-top: 10px;
    padding-right: 15px;
    padding-bottom: 20px;
    padding-left: 25px;
}
```

### Padding et contenu

```css
/* Le padding affecte la taille totale */
.box-with-padding {
    width: 200px;
    padding: 20px;
    /* Largeur totale = 200 + 40 = 240px */
}

/* Padding en pourcentage */
.padding-percentage {
    padding: 5%; /* 5% de la largeur du parent */
}
```

## ⚙️ Box-sizing

### Content-box (défaut)

```css
/* Comportement par défaut */
.content-box {
    box-sizing: content-box;
    width: 200px;
    padding: 20px;
    border: 5px solid;
    /* Largeur totale = 200 + 40 + 10 = 250px */
}
```

### Border-box

```css
/* Taille incluant padding et border */
.border-box {
    box-sizing: border-box;
    width: 200px;
    padding: 20px;
    border: 5px solid;
    /* Largeur totale = 200px */
    /* Largeur du contenu = 200 - 40 - 10 = 150px */
}
```

### Reset universel

```css
/* Appliqué à tous les éléments */
* {
    box-sizing: border-box;
}

/* Ou plus spécifique */
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

## 🔧 Contrôle du débordement

### Overflow

```css
/* Gestion du débordement */
.overflow-visible { overflow: visible; }
.overflow-hidden { overflow: hidden; }
.overflow-scroll { overflow: scroll; }
.overflow-auto { overflow: auto; }

/* Par axe */
.overflow-x { overflow-x: hidden; }
.overflow-y { overflow-y: scroll; }
```

### Text-overflow

```css
/* Ellipsis pour le texte */
.text-ellipsis {
    width: 200px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
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
    <title>Modèle de boîte CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Comprendre le modèle de boîte</h1>
        
        <!-- Démonstration box-sizing -->
        <section class="demo-section">
            <h2>Box-sizing : content-box vs border-box</h2>
            <div class="box-comparison">
                <div class="box content-box">
                    <h3>Content-box</h3>
                    <p>width: 200px<br>
                       padding: 20px<br>
                       border: 5px<br>
                       = 250px total</p>
                </div>
                <div class="box border-box">
                    <h3>Border-box</h3>
                    <p>width: 200px<br>
                       padding: 20px<br>
                       border: 5px<br>
                       = 200px total</p>
                </div>
            </div>
        </section>

        <!-- Démonstration marges -->
        <section class="demo-section">
            <h2>Marges et centrage</h2>
            <div class="margin-demo">
                <div class="centered-box">
                    <p>Boîte centrée avec margin: 0 auto</p>
                </div>
                <div class="margin-example">
                    <p>Marge de 20px autour</p>
                </div>
            </div>
        </section>

        <!-- Démonstration bordures -->
        <section class="demo-section">
            <h2>Styles de bordures</h2>
            <div class="border-showcase">
                <div class="border-box solid">Solid</div>
                <div class="border-box dashed">Dashed</div>
                <div class="border-box dotted">Dotted</div>
                <div class="border-box double">Double</div>
                <div class="border-box rounded">Rounded</div>
                <div class="border-box circle">Circle</div>
            </div>
        </section>

        <!-- Démonstration padding -->
        <section class="demo-section">
            <h2>Padding et espacement</h2>
            <div class="padding-demo">
                <div class="padding-box small">
                    <p>Padding: 10px</p>
                </div>
                <div class="padding-box medium">
                    <p>Padding: 20px</p>
                </div>
                <div class="padding-box large">
                    <p>Padding: 30px</p>
                </div>
            </div>
        </section>

        <!-- Démonstration débordement -->
        <section class="demo-section">
            <h2>Gestion du débordement</h2>
            <div class="overflow-demo">
                <div class="overflow-box hidden">
                    <h4>Overflow: hidden</h4>
                    <p>Ce texte est très long et dépasse la largeur fixe de la boîte. Il sera coupé car overflow est défini sur hidden.</p>
                </div>
                <div class="overflow-box scroll">
                    <h4>Overflow: scroll</h4>
                    <p>Ce texte est très long et dépasse la largeur fixe de la boîte. Une barre de défilement apparaîtra pour permettre de voir tout le contenu.</p>
                </div>
                <div class="overflow-box ellipsis">
                    <h4>Text-overflow: ellipsis</h4>
                    <p>Ce texte très long sera coupé avec des points de suspension</p>
                </div>
            </div>
        </section>
    </div>
</body>
</html>
```

**CSS :**
```css
/* Reset universel avec border-box */
*,
*::before,
*::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

/* Styles de base */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
    background: #f5f5f5;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

h1 {
    text-align: center;
    color: #2c3e50;
    margin-bottom: 2rem;
    font-size: 2.5rem;
}

/* Sections de démonstration */
.demo-section {
    background: white;
    margin-bottom: 2rem;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.demo-section h2 {
    color: #34495e;
    margin-bottom: 1.5rem;
    font-size: 1.8rem;
    border-bottom: 3px solid #3498db;
    padding-bottom: 0.5rem;
}

/* Démonstration box-sizing */
.box-comparison {
    display: flex;
    gap: 2rem;
    justify-content: center;
    flex-wrap: wrap;
}

.box {
    width: 200px;
    padding: 20px;
    border: 5px solid #3498db;
    background: #ecf0f1;
    text-align: center;
    margin: 1rem;
}

.content-box {
    box-sizing: content-box;
    border-color: #e74c3c;
}

.border-box {
    box-sizing: border-box;
    border-color: #2ecc71;
}

.box h3 {
    color: #2c3e50;
    margin-bottom: 1rem;
}

.box p {
    font-size: 0.9rem;
    color: #7f8c8d;
}

/* Démonstration marges */
.margin-demo {
    display: flex;
    flex-direction: column;
    gap: 2rem;
}

.centered-box {
    width: 300px;
    margin: 0 auto;
    padding: 1rem;
    background: #3498db;
    color: white;
    text-align: center;
    border-radius: 5px;
}

.margin-example {
    width: 250px;
    margin: 20px auto;
    padding: 1rem;
    background: #2ecc71;
    color: white;
    text-align: center;
    border-radius: 5px;
}

/* Démonstration bordures */
.border-showcase {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem;
}

.border-box {
    padding: 1rem;
    text-align: center;
    background: #ecf0f1;
    color: #2c3e50;
    font-weight: bold;
}

.solid { border: 3px solid #3498db; }
.dashed { border: 3px dashed #e74c3c; }
.dotted { border: 3px dotted #2ecc71; }
.double { border: 6px double #9b59b6; }
.rounded { 
    border: 3px solid #f39c12;
    border-radius: 10px;
}
.circle { 
    border: 3px solid #1abc9c;
    border-radius: 50%;
    width: 100px;
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
}

/* Démonstration padding */
.padding-demo {
    display: flex;
    gap: 2rem;
    justify-content: center;
    flex-wrap: wrap;
}

.padding-box {
    background: #3498db;
    color: white;
    text-align: center;
    border-radius: 5px;
    border: 2px solid #2980b9;
}

.padding-box.small {
    padding: 10px;
}

.padding-box.medium {
    padding: 20px;
}

.padding-box.large {
    padding: 30px;
}

/* Démonstration débordement */
.overflow-demo {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
}

.overflow-box {
    width: 250px;
    height: 120px;
    padding: 1rem;
    background: #ecf0f1;
    border: 2px solid #bdc3c7;
    border-radius: 5px;
}

.overflow-box.hidden {
    overflow: hidden;
}

.overflow-box.scroll {
    overflow: scroll;
}

.overflow-box.ellipsis {
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}

.overflow-box h4 {
    color: #2c3e50;
    margin-bottom: 0.5rem;
    font-size: 1rem;
}

.overflow-box p {
    color: #7f8c8d;
    font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 768px) {
    .box-comparison {
        flex-direction: column;
        align-items: center;
    }
    
    .box {
        width: 100%;
        max-width: 300px;
    }
    
    .padding-demo {
        flex-direction: column;
        align-items: center;
    }
    
    .container {
        padding: 1rem;
    }
}

/* Styles pour la visualisation du box model */
.box-model-visual {
    position: relative;
    display: inline-block;
    margin: 2rem;
}

.box-model-visual::before {
    content: 'MARGIN';
    position: absolute;
    top: -25px;
    left: 50%;
    transform: translateX(-50%);
    color: #e74c3c;
    font-size: 0.8rem;
    font-weight: bold;
}

.box-model-visual::after {
    content: '';
    position: absolute;
    top: -10px;
    right: -10px;
    bottom: -10px;
    left: -10px;
    border: 2px dashed #e74c3c;
    pointer-events: none;
}
```

## ✅ Exercice pratique

1. Créez des boîtes démontrant :
   - La différence entre content-box et border-box
   - Différents styles de bordures
   - Techniques de centrage
   - Gestion du débordement

2. Construisez une grille de cartes avec :
   - Dimensions cohérentes
   - Espacement uniforme
   - Bordures arrondies
   - Effets de hover

3. Testez le responsive design

## 🔍 Bonnes pratiques

- **Utilisez border-box** comme défaut
- **Évitez les largeurs fixes** quand possible
- **Utilisez em/rem** pour les espacements
- **Testez sur différents écrans**
- **Attention aux marges fusionnées**

## 🔗 Ressources supplémentaires

- [MDN - Box Model](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Box_Model)
- [Box-sizing Explained](https://www.paulirish.com/2012/box-sizing-border-box-ftw/)
- [CSS Box Model Interactive](https://codepen.io/carolineartz/pen/ogVXZj)

---

**Temps estimé :** 3 heures  
**Prochaine étape :** [Module 6 - Positionnement](../06-positionnement/)