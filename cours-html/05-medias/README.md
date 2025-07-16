# Module 5 : Médias (Images, vidéos, audio)

## 🎯 Objectifs du module

- Intégrer des images avec la balise `<img>`
- Utiliser les médias audio et vidéo
- Comprendre les formats et l'optimisation
- Maîtriser l'accessibilité des médias

## 🖼️ Images avec `<img>`

### Syntaxe de base

```html
<img src="chemin/vers/image.jpg" alt="Description de l'image">
```

### Attributs essentiels

```html
<img src="photo.jpg" 
     alt="Coucher de soleil sur la mer" 
     width="800" 
     height="600"
     title="Photo prise en Bretagne">
```

### Types de chemins

```html
<!-- Chemin relatif -->
<img src="images/logo.png" alt="Logo de l'entreprise">

<!-- Chemin absolu -->
<img src="/assets/images/banner.jpg" alt="Bannière d'accueil">

<!-- URL externe -->
<img src="https://example.com/image.jpg" alt="Image externe">
```

## 🎨 Images responsives

### Attribut `srcset`

```html
<img src="image-small.jpg" 
     srcset="image-small.jpg 300w,
             image-medium.jpg 600w,
             image-large.jpg 1200w"
     sizes="(max-width: 600px) 300px,
            (max-width: 1200px) 600px,
            1200px"
     alt="Image responsive">
```

### Élément `<picture>`

```html
<picture>
    <source media="(max-width: 600px)" srcset="image-mobile.jpg">
    <source media="(max-width: 1200px)" srcset="image-tablet.jpg">
    <img src="image-desktop.jpg" alt="Image adaptative">
</picture>
```

### Formats d'image modernes

```html
<picture>
    <source type="image/webp" srcset="image.webp">
    <source type="image/jpeg" srcset="image.jpg">
    <img src="image.jpg" alt="Image avec fallback">
</picture>
```

## 🎵 Audio avec `<audio>`

### Syntaxe de base

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Votre navigateur ne supporte pas l'audio HTML5.
</audio>
```

### Attributs principaux

```html
<audio controls 
       autoplay 
       loop 
       muted
       preload="auto">
    <source src="music.mp3" type="audio/mpeg">
    <source src="music.ogg" type="audio/ogg">
    <p>Votre navigateur ne supporte pas l'élément audio.</p>
</audio>
```

### Exemple avec contrôles personnalisés

```html
<audio id="monAudio" preload="auto">
    <source src="podcast.mp3" type="audio/mpeg">
    <source src="podcast.ogg" type="audio/ogg">
</audio>

<div>
    <button onclick="document.getElementById('monAudio').play()">Play</button>
    <button onclick="document.getElementById('monAudio').pause()">Pause</button>
</div>
```

## 🎬 Vidéo avec `<video>`

### Syntaxe de base

```html
<video controls width="640" height="480">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <source src="video.ogg" type="video/ogg">
    Votre navigateur ne supporte pas la vidéo HTML5.
</video>
```

### Attributs avancés

```html
<video controls
       width="800"
       height="450"
       poster="thumbnail.jpg"
       preload="metadata"
       muted
       autoplay>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <track kind="subtitles" src="subtitles-fr.vtt" srclang="fr" label="Français">
    <track kind="subtitles" src="subtitles-en.vtt" srclang="en" label="English">
    <p>Votre navigateur ne supporte pas la vidéo HTML5.</p>
</video>
```

## 📱 Intégration de médias externes

### YouTube

```html
<iframe width="560" 
        height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        title="Titre de la vidéo"
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen>
</iframe>
```

### Avec conteneur responsive

```html
<div style="position: relative; width: 100%; height: 0; padding-bottom: 56.25%;">
    <iframe src="https://www.youtube.com/embed/VIDEO_ID"
            style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
            frameborder="0"
            allowfullscreen>
    </iframe>
</div>
```

## 🔧 Optimisation et performance

### Formats d'image recommandés

```html
<!-- Pour les photos -->
<picture>
    <source type="image/webp" srcset="photo.webp">
    <img src="photo.jpg" alt="Photo" loading="lazy">
</picture>

<!-- Pour les graphiques -->
<img src="logo.svg" alt="Logo" width="200" height="100">

<!-- Pour les icônes -->
<img src="icon.png" alt="Icône" width="32" height="32">
```

### Chargement différé (lazy loading)

```html
<img src="image.jpg" 
     alt="Image" 
     loading="lazy"
     width="800" 
     height="600">
```

## ♿ Accessibilité des médias

### Texte alternatif pour les images

```html
<!-- Image informative -->
<img src="graph.png" alt="Graphique montrant une augmentation des ventes de 25% en 2024">

<!-- Image décorative -->
<img src="decoration.jpg" alt="">

<!-- Image complexe -->
<img src="complex-chart.png" alt="Graphique des ventes" longdesc="chart-description.html">
```

### Sous-titres pour les vidéos

```html
<video controls>
    <source src="video.mp4" type="video/mp4">
    <track kind="subtitles" src="subtitles.vtt" srclang="fr" default>
    <track kind="captions" src="captions.vtt" srclang="fr">
    <track kind="descriptions" src="descriptions.vtt" srclang="fr">
</video>
```

## 💻 Exemple pratique complet

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galerie multimédia</title>
</head>
<body>
    <header>
        <h1>Ma galerie multimédia</h1>
    </header>

    <main>
        <section>
            <h2>Galerie photos</h2>
            
            <figure>
                <picture>
                    <source media="(max-width: 600px)" srcset="landscape-small.jpg">
                    <source media="(max-width: 1200px)" srcset="landscape-medium.jpg">
                    <img src="landscape-large.jpg" 
                         alt="Paysage montagneux au coucher du soleil"
                         loading="lazy">
                </picture>
                <figcaption>Coucher de soleil dans les Alpes</figcaption>
            </figure>

            <figure>
                <img src="portrait.jpg" 
                     alt="Portrait d'une personne souriante"
                     width="400" 
                     height="600"
                     loading="lazy">
                <figcaption>Portrait réalisé en studio</figcaption>
            </figure>
        </section>

        <section>
            <h2>Contenu audio</h2>
            
            <figure>
                <audio controls preload="metadata">
                    <source src="podcast.mp3" type="audio/mpeg">
                    <source src="podcast.ogg" type="audio/ogg">
                    <p>Votre navigateur ne supporte pas l'audio HTML5.</p>
                </audio>
                <figcaption>Podcast sur le développement web</figcaption>
            </figure>
        </section>

        <section>
            <h2>Contenu vidéo</h2>
            
            <figure>
                <video controls 
                       width="800" 
                       height="450"
                       poster="video-thumbnail.jpg"
                       preload="metadata">
                    <source src="tutorial.mp4" type="video/mp4">
                    <source src="tutorial.webm" type="video/webm">
                    <track kind="subtitles" 
                           src="subtitles-fr.vtt" 
                           srclang="fr" 
                           label="Français" 
                           default>
                    <p>Votre navigateur ne supporte pas la vidéo HTML5.</p>
                </video>
                <figcaption>Tutoriel de développement web</figcaption>
            </figure>
        </section>

        <section>
            <h2>Vidéo YouTube</h2>
            
            <div style="position: relative; width: 100%; height: 0; padding-bottom: 56.25%;">
                <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ"
                        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
                        title="Vidéo YouTube intégrée"
                        frameborder="0"
                        allowfullscreen>
                </iframe>
            </div>
        </section>
    </main>
</body>
</html>
```

## ✅ Exercice pratique

1. Créez une galerie multimédia avec :
   - 3 images différentes avec `alt` appropriés
   - Une image responsive avec `srcset`
   - Un fichier audio avec contrôles
   - Une vidéo locale avec sous-titres
   - Une vidéo YouTube intégrée

2. Optimisez pour la performance avec `loading="lazy"`

3. Testez l'accessibilité avec un lecteur d'écran

## 🔍 Bonnes pratiques

- Toujours inclure l'attribut `alt` pour les images
- Utiliser des formats modernes (WebP, AVIF)
- Implémenter le chargement différé
- Fournir des sous-titres pour les vidéos
- Optimiser la taille des fichiers médias
- Utiliser `figure` et `figcaption` pour les légendes

## 🔗 Ressources supplémentaires

- [MDN - Images HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element/img)
- [MDN - Élément video](https://developer.mozilla.org/fr/docs/Web/HTML/Element/video)
- [WebAIM - Accessibilité des images](https://webaim.org/techniques/images/)

---

**Temps estimé :** 2.5 heures  
**Prochaine étape :** [Module 6 - Structure sémantique](../06-structure-semantique/)