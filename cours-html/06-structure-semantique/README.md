# Module 6 : Structure sémantique HTML5

## 🎯 Objectifs du module

- Comprendre la sémantique HTML5
- Utiliser les nouvelles balises structurelles
- Créer une architecture de page moderne
- Améliorer l'accessibilité et le SEO

## 🏗️ Qu'est-ce que la sémantique ?

La sémantique HTML consiste à utiliser les bonnes balises pour décrire le **sens** du contenu, pas seulement son apparence.

### Avantages :
- **SEO amélioré** : les moteurs de recherche comprennent mieux le contenu
- **Accessibilité** : les lecteurs d'écran naviguent plus facilement
- **Maintenance** : code plus clair et structuré
- **Compatibilité** : meilleure adaptation aux nouveaux appareils

## 🆕 Nouvelles balises HTML5

### Structure principale

```html
<header>En-tête de la page ou section</header>
<nav>Navigation principale</nav>
<main>Contenu principal</main>
<section>Section thématique</section>
<article>Contenu autonome</article>
<aside>Contenu secondaire</aside>
<footer>Pied de page</footer>
```

## 📋 Éléments structurels détaillés

### `<header>`
En-tête de la page ou d'une section

```html
<!-- En-tête de page -->
<header>
    <h1>Mon site web</h1>
    <p>Tagline ou description</p>
</header>

<!-- En-tête d'article -->
<article>
    <header>
        <h2>Titre de l'article</h2>
        <p>Publié le <time datetime="2024-01-15">15 janvier 2024</time></p>
    </header>
    <p>Contenu de l'article...</p>
</article>
```

### `<nav>`
Navigation principale ou secondaire

```html
<nav aria-label="Navigation principale">
    <ul>
        <li><a href="/">Accueil</a></li>
        <li><a href="/about">À propos</a></li>
        <li><a href="/contact">Contact</a></li>
    </ul>
</nav>

<nav aria-label="Pagination">
    <a href="?page=1" rel="prev">Précédent</a>
    <span>Page 2 sur 10</span>
    <a href="?page=3" rel="next">Suivant</a>
</nav>
```

### `<main>`
Contenu principal de la page (unique par page)

```html
<main>
    <h1>Titre principal de la page</h1>
    <p>Contenu principal...</p>
</main>
```

### `<section>`
Section thématique avec titre

```html
<section>
    <h2>Nos services</h2>
    <p>Description des services...</p>
</section>

<section>
    <h2>Témoignages</h2>
    <blockquote>Excellent service...</blockquote>
</section>
```

### `<article>`
Contenu autonome et réutilisable

```html
<article>
    <header>
        <h2>Titre de l'article</h2>
        <p>Par <span>Auteur</span> le <time datetime="2024-01-15">15 janvier 2024</time></p>
    </header>
    <p>Contenu de l'article qui peut être distribué indépendamment...</p>
    <footer>
        <p>Tags : <a href="/tag/html">HTML</a>, <a href="/tag/css">CSS</a></p>
    </footer>
</article>
```

### `<aside>`
Contenu secondaire ou complémentaire

```html
<aside>
    <h3>Articles connexes</h3>
    <ul>
        <li><a href="/article1">Article 1</a></li>
        <li><a href="/article2">Article 2</a></li>
    </ul>
</aside>

<aside>
    <h3>Publicité</h3>
    <div>Contenu publicitaire</div>
</aside>
```

### `<footer>`
Pied de page ou de section

```html
<footer>
    <p>&copy; 2024 Mon site. Tous droits réservés.</p>
    <nav>
        <a href="/legal">Mentions légales</a>
        <a href="/privacy">Confidentialité</a>
    </nav>
</footer>
```

## 🕒 Éléments de temps et contenu

### `<time>`
Dates et heures

```html
<time datetime="2024-01-15">15 janvier 2024</time>
<time datetime="2024-01-15T14:30:00">15 janvier 2024 à 14h30</time>
<time datetime="PT2H30M">2 heures et 30 minutes</time>
```

### `<address>`
Informations de contact

```html
<address>
    <p>Contact : <a href="mailto:info@example.com">info@example.com</a></p>
    <p>Adresse : 123 Rue de la Paix, 75001 Paris</p>
</address>
```

### `<figure>` et `<figcaption>`
Contenu illustratif avec légende

```html
<figure>
    <img src="graph.png" alt="Graphique des ventes 2024">
    <figcaption>Évolution des ventes au premier trimestre 2024</figcaption>
</figure>

<figure>
    <pre><code>
function hello() {
    console.log("Hello World!");
}
    </code></pre>
    <figcaption>Exemple de fonction JavaScript</figcaption>
</figure>
```

## 🎨 Structure de page complète

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog - Mon site</title>
</head>
<body>
    <header>
        <h1>Mon Blog</h1>
        <p>Actualités et tutoriels web</p>
    </header>

    <nav aria-label="Navigation principale">
        <ul>
            <li><a href="/">Accueil</a></li>
            <li><a href="/articles">Articles</a></li>
            <li><a href="/about">À propos</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
    </nav>

    <main>
        <section>
            <h2>Articles récents</h2>
            
            <article>
                <header>
                    <h3>Introduction à HTML5</h3>
                    <p>Publié le <time datetime="2024-01-15">15 janvier 2024</time></p>
                </header>
                <p>HTML5 apporte de nouvelles fonctionnalités...</p>
                <footer>
                    <p>Tags : <a href="/tag/html5">HTML5</a>, <a href="/tag/web">Web</a></p>
                </footer>
            </article>

            <article>
                <header>
                    <h3>CSS Grid vs Flexbox</h3>
                    <p>Publié le <time datetime="2024-01-10">10 janvier 2024</time></p>
                </header>
                <p>Comparaison entre CSS Grid et Flexbox...</p>
                <footer>
                    <p>Tags : <a href="/tag/css">CSS</a>, <a href="/tag/layout">Layout</a></p>
                </footer>
            </article>
        </section>

        <section>
            <h2>Tutoriels populaires</h2>
            <ul>
                <li><a href="/tutorial/html-basics">Bases du HTML</a></li>
                <li><a href="/tutorial/css-grid">CSS Grid Layout</a></li>
                <li><a href="/tutorial/javascript-intro">Introduction JavaScript</a></li>
            </ul>
        </section>
    </main>

    <aside>
        <section>
            <h3>À propos de l'auteur</h3>
            <p>Développeur web passionné depuis 10 ans...</p>
        </section>

        <section>
            <h3>Newsletter</h3>
            <p>Inscrivez-vous pour recevoir les derniers articles :</p>
            <form>
                <input type="email" placeholder="Votre email">
                <button type="submit">S'inscrire</button>
            </form>
        </section>
    </aside>

    <footer>
        <p>&copy; 2024 Mon Blog. Tous droits réservés.</p>
        <nav aria-label="Navigation footer">
            <a href="/legal">Mentions légales</a>
            <a href="/privacy">Confidentialité</a>
            <a href="/sitemap">Plan du site</a>
        </nav>
        <address>
            Contact : <a href="mailto:contact@monblog.com">contact@monblog.com</a>
        </address>
    </footer>
</body>
</html>
```

## 🔍 Bonnes pratiques

### Hiérarchie des titres
```html
<h1>Titre principal</h1>
<section>
    <h2>Section 1</h2>
    <article>
        <h3>Article dans la section</h3>
        <h4>Sous-section de l'article</h4>
    </article>
</section>
```

### Utilisation appropriée
```html
<!-- ✅ Bon usage -->
<article>
    <h2>Article complet</h2>
    <p>Contenu autonome...</p>
</article>

<section>
    <h2>Section thématique</h2>
    <p>Contenu regroupé par thème...</p>
</section>

<!-- ❌ Mauvais usage -->
<section>
    <p>Contenu sans titre</p>
</section>

<article>
    <p>Contenu qui n'est pas autonome</p>
</article>
```

## ♿ Accessibilité

### Attributs ARIA
```html
<nav aria-label="Navigation principale">
    <ul>
        <li><a href="/" aria-current="page">Accueil</a></li>
        <li><a href="/about">À propos</a></li>
    </ul>
</nav>

<main aria-label="Contenu principal">
    <h1>Titre de la page</h1>
</main>
```

### Liens de navigation
```html
<a href="#main" class="skip-link">Aller au contenu principal</a>

<main id="main">
    <h1>Contenu principal</h1>
</main>
```

## ✅ Exercice pratique

1. Créez une page blog avec :
   - Structure HTML5 complète
   - Navigation principale et secondaire
   - 2-3 articles avec headers et footers
   - Sidebar avec contenu complémentaire
   - Footer avec informations de contact

2. Validez votre code HTML5

3. Testez l'accessibilité avec un lecteur d'écran

## 🔗 Ressources supplémentaires

- [MDN - Sections HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element#sections)
- [W3C - HTML5 Semantic Elements](https://www.w3.org/TR/html5/sections.html)
- [WebAIM - Semantic Structure](https://webaim.org/techniques/semanticstructure/)

---

**Temps estimé :** 2 heures  
**Prochaine étape :** [Module 7 - Listes et tableaux](../07-listes-tableaux/)