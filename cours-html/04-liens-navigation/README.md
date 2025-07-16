# Module 4 : Liens et navigation

## 🎯 Objectifs du module

- Créer des liens hypertextes avec la balise `<a>`
- Comprendre les différents types de liens
- Construire une navigation efficace
- Maîtriser les attributs des liens

## 🔗 La balise `<a>` (ancre)

### Syntaxe de base

```html
<a href="destination">Texte du lien</a>
```

### Attributs principaux

```html
<a href="https://example.com" 
   target="_blank" 
   title="Ouvre dans un nouvel onglet"
   rel="noopener">
   Visitez notre site
</a>
```

## 📍 Types de liens

### 1. Liens absolus (vers d'autres sites)

```html
<a href="https://www.google.com">Google</a>
<a href="https://developer.mozilla.org">MDN Web Docs</a>
```

### 2. Liens relatifs (vers des pages de votre site)

```html
<!-- Fichier dans le même dossier -->
<a href="contact.html">Contact</a>

<!-- Fichier dans un sous-dossier -->
<a href="images/photo.jpg">Voir la photo</a>

<!-- Fichier dans le dossier parent -->
<a href="../index.html">Retour à l'accueil</a>

<!-- Fichier dans un autre dossier -->
<a href="../blog/article1.html">Article 1</a>
```

### 3. Liens internes (ancres dans la même page)

```html
<!-- Création de l'ancre -->
<h2 id="section1">Section 1</h2>

<!-- Lien vers l'ancre -->
<a href="#section1">Aller à la section 1</a>
<a href="#top">Retour en haut</a>
```

### 4. Liens spéciaux

```html
<!-- Lien email -->
<a href="mailto:contact@example.com">Nous contacter</a>
<a href="mailto:contact@example.com?subject=Demande d'information">Email avec sujet</a>

<!-- Lien téléphone -->
<a href="tel:+33123456789">01 23 45 67 89</a>

<!-- Téléchargement -->
<a href="document.pdf" download>Télécharger le PDF</a>
<a href="image.jpg" download="mon-image.jpg">Télécharger l'image</a>
```

## 🧭 Navigation web

### Structure de navigation basique

```html
<nav>
    <ul>
        <li><a href="index.html">Accueil</a></li>
        <li><a href="about.html">À propos</a></li>
        <li><a href="services.html">Services</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

### Navigation avec sous-menus

```html
<nav>
    <ul>
        <li><a href="index.html">Accueil</a></li>
        <li>
            <a href="products.html">Produits</a>
            <ul>
                <li><a href="laptops.html">Ordinateurs portables</a></li>
                <li><a href="desktops.html">Ordinateurs de bureau</a></li>
                <li><a href="tablets.html">Tablettes</a></li>
            </ul>
        </li>
        <li><a href="support.html">Support</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

### Breadcrumb (fil d'Ariane)

```html
<nav aria-label="Breadcrumb">
    <ol>
        <li><a href="/">Accueil</a></li>
        <li><a href="/products/">Produits</a></li>
        <li><a href="/products/laptops/">Ordinateurs portables</a></li>
        <li aria-current="page">MacBook Pro</li>
    </ol>
</nav>
```

## 🎨 Attributs avancés

### Attribut `target`

```html
<a href="https://example.com" target="_blank">Nouvel onglet</a>
<a href="page.html" target="_self">Même onglet (défaut)</a>
<a href="page.html" target="_parent">Fenêtre parent</a>
<a href="page.html" target="_top">Fenêtre principale</a>
```

### Attribut `rel`

```html
<!-- Sécurité pour les liens externes -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
    Lien externe sécurisé
</a>

<!-- Relation avec la page liée -->
<a href="next-page.html" rel="next">Page suivante</a>
<a href="prev-page.html" rel="prev">Page précédente</a>
<a href="author.html" rel="author">Auteur</a>
```

### Attribut `title`

```html
<a href="document.pdf" title="Télécharger le guide PDF (2 MB)">
    Guide utilisateur
</a>
```

## 📱 Accessibilité des liens

### Bonnes pratiques

```html
<!-- Texte de lien descriptif -->
<a href="rapport-2024.pdf">Télécharger le rapport annuel 2024</a>

<!-- Éviter les textes vagues -->
<!-- ❌ Mauvais -->
<a href="rapport.pdf">Cliquez ici</a>

<!-- ✅ Bon -->
<a href="rapport.pdf">Télécharger le rapport financier</a>

<!-- Indication du type de fichier -->
<a href="presentation.pptx">
    Présentation PowerPoint (PPTX, 5 MB)
</a>

<!-- Liens avec icônes -->
<a href="https://twitter.com" aria-label="Suivez-nous sur Twitter">
    <img src="twitter-icon.png" alt="Twitter">
</a>
```

## 💻 Exemple pratique complet

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mon site - Navigation</title>
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#accueil">Accueil</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#portfolio">Portfolio</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="accueil">
            <h1>Bienvenue sur mon site</h1>
            <p>Découvrez mes <a href="#services">services</a> et consultez mon 
            <a href="#portfolio">portfolio</a> pour voir mes réalisations.</p>
        </section>

        <section id="services">
            <h2>Mes services</h2>
            <p>Je propose différents services :</p>
            <ul>
                <li><a href="services/web-design.html">Web design</a></li>
                <li><a href="services/development.html">Développement web</a></li>
                <li><a href="services/seo.html">Référencement SEO</a></li>
            </ul>
        </section>

        <section id="portfolio">
            <h2>Portfolio</h2>
            <p>Voici quelques-uns de mes projets :</p>
            <div>
                <h3>Site e-commerce</h3>
                <p><a href="https://example-shop.com" target="_blank" rel="noopener">
                    Voir le site en ligne
                </a></p>
            </div>
        </section>

        <section id="contact">
            <h2>Contact</h2>
            <p>N'hésitez pas à me contacter :</p>
            <ul>
                <li>Email : <a href="mailto:contact@monsite.com">contact@monsite.com</a></li>
                <li>Téléphone : <a href="tel:+33123456789">01 23 45 67 89</a></li>
                <li>LinkedIn : <a href="https://linkedin.com/in/monprofil" target="_blank" rel="noopener">Mon profil LinkedIn</a></li>
            </ul>
        </section>
    </main>

    <footer>
        <nav>
            <ul>
                <li><a href="#top">Haut de page</a></li>
                <li><a href="legal.html">Mentions légales</a></li>
                <li><a href="privacy.html">Confidentialité</a></li>
            </ul>
        </nav>
    </footer>
</body>
</html>
```

## ✅ Exercice pratique

1. Créez une page avec navigation complète :
   - Menu principal avec 4-5 liens
   - Liens internes vers différentes sections
   - Au moins un lien externe
   - Liens email et téléphone
   - Navigation de pied de page

2. Testez tous vos liens pour vérifier qu'ils fonctionnent

3. Ajoutez des attributs `title` pertinents

## 🔍 Bonnes pratiques

- Utiliser des textes de liens descriptifs
- Ajouter `rel="noopener"` pour les liens externes
- Structurer la navigation avec `<nav>`
- Tester l'accessibilité des liens
- Éviter les liens brisés

## 🔗 Ressources supplémentaires

- [MDN - L'élément `<a>`](https://developer.mozilla.org/fr/docs/Web/HTML/Element/a)
- [WebAIM - Accessibilité des liens](https://webaim.org/techniques/hypertext/)

---

**Temps estimé :** 2 heures  
**Prochaine étape :** [Module 5 - Médias](../05-medias/)