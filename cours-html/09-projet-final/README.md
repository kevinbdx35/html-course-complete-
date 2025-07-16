# Module 9 : Projet final

## 🎯 Objectif du projet

Créer un site web complet qui met en pratique toutes les connaissances acquises dans ce cours HTML. Ce projet servira de validation de vos compétences et de portfolio pour vos futurs projets.

## 📋 Cahier des charges

### Sujet : Site web d'une entreprise fictive

Créez un site web pour une entreprise de votre choix (restaurant, agence web, boutique, etc.) comprenant :

1. **Page d'accueil** (`index.html`)
2. **Page "À propos"** (`about.html`)
3. **Page "Services/Produits"** (`services.html`)
4. **Page "Contact"** (`contact.html`)

## 🔧 Exigences techniques

### Structure HTML5 obligatoire

- [x] Utilisation des balises sémantiques (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`)
- [x] Structure de document valide (DOCTYPE, html, head, body)
- [x] Métadonnées appropriées (charset, viewport, title, description)
- [x] Hiérarchie des titres respectée (h1-h6)

### Contenu requis

#### Page d'accueil (`index.html`)
- [x] En-tête avec logo et navigation
- [x] Section héro avec titre principal
- [x] Section présentation de l'entreprise
- [x] Section services/produits (aperçu)
- [x] Section témoignages ou actualités
- [x] Pied de page avec informations de contact

#### Page "À propos" (`about.html`)
- [x] Histoire de l'entreprise
- [x] Équipe (avec photos et descriptions)
- [x] Valeurs et mission
- [x] Chronologie ou réalisations

#### Page "Services/Produits" (`services.html`)
- [x] Liste des services/produits
- [x] Descriptions détaillées
- [x] Tableau de tarifs ou comparatif
- [x] Galerie d'images

#### Page "Contact" (`contact.html`)
- [x] Formulaire de contact complet
- [x] Informations de contact (adresse, téléphone, email)
- [x] Carte ou plan d'accès (peut être une image)
- [x] Horaires d'ouverture

### Éléments techniques à inclure

#### Navigation
- [x] Menu de navigation cohérent sur toutes les pages
- [x] Liens internes et externes
- [x] Fil d'Ariane sur les pages secondaires

#### Médias
- [x] Images optimisées avec attributs `alt` appropriés
- [x] Au moins une image responsive (`srcset` ou `<picture>`)
- [x] Utilisation de `<figure>` et `<figcaption>`

#### Listes et tableaux
- [x] Liste de navigation
- [x] Listes à puces ou numérotées pour organiser l'information
- [x] Tableau avec en-têtes appropriés

#### Formulaires
- [x] Formulaire de contact avec validation HTML5
- [x] Différents types d'inputs
- [x] Groupement avec `<fieldset>` et `<legend>`
- [x] Labels appropriés pour l'accessibilité

## 📁 Structure de fichiers

```
projet-final/
├── index.html
├── about.html
├── services.html
├── contact.html
├── images/
│   ├── logo.png
│   ├── hero-image.jpg
│   ├── team/
│   │   ├── person1.jpg
│   │   └── person2.jpg
│   └── gallery/
│       ├── service1.jpg
│       └── service2.jpg
└── README.md
```

## 🎨 Contenu suggéré par type d'entreprise

### Restaurant
- **Accueil** : Présentation, spécialités, ambiance
- **À propos** : Histoire, chef, équipe
- **Services** : Menu, carte des vins, événements
- **Contact** : Réservation, localisation, horaires

### Agence web
- **Accueil** : Services, portfolio, témoignages
- **À propos** : Équipe, expertise, valeurs
- **Services** : Développement, design, SEO
- **Contact** : Devis, coordonnées, processus

### Boutique
- **Accueil** : Produits phares, nouveautés, promotions
- **À propos** : Histoire, philosophie, engagement
- **Services** : Catalogue, livraison, garantie
- **Contact** : Commande, SAV, magasins

## 💻 Exemple de page d'accueil

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Agence web créative spécialisée dans le développement de sites web modernes et performants">
    <meta name="keywords" content="agence web, développement web, design, SEO">
    <title>WebCréa - Agence web créative</title>
</head>
<body>
    <header>
        <img src="images/logo.png" alt="WebCréa - Agence web créative" width="200" height="60">
        <nav aria-label="Navigation principale">
            <ul>
                <li><a href="index.html" aria-current="page">Accueil</a></li>
                <li><a href="about.html">À propos</a></li>
                <li><a href="services.html">Services</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="hero">
            <h1>Créons ensemble votre présence digitale</h1>
            <p>Agence web spécialisée dans la création de sites web modernes, performants et sur mesure.</p>
            <a href="contact.html" class="cta-button">Demander un devis</a>
        </section>

        <section id="about-preview">
            <h2>Qui sommes-nous ?</h2>
            <p>WebCréa est une agence web créative composée de développeurs et designers passionnés. Nous accompagnons nos clients dans leur transformation digitale depuis plus de 5 ans.</p>
            <a href="about.html">En savoir plus</a>
        </section>

        <section id="services-preview">
            <h2>Nos services</h2>
            <div class="services-grid">
                <article>
                    <h3>Développement web</h3>
                    <p>Sites web sur mesure, applications web, e-commerce.</p>
                </article>
                <article>
                    <h3>Design UX/UI</h3>
                    <p>Conception d'interfaces utilisateur modernes et intuitives.</p>
                </article>
                <article>
                    <h3>Référencement SEO</h3>
                    <p>Optimisation pour les moteurs de recherche.</p>
                </article>
            </div>
            <a href="services.html">Voir tous nos services</a>
        </section>

        <section id="testimonials">
            <h2>Témoignages clients</h2>
            <blockquote>
                <p>« WebCréa a créé un site web exceptionnel pour notre entreprise. L'équipe est professionnelle et à l'écoute. »</p>
                <footer>— <cite>Marie Dubois, Directrice Marketing</cite></footer>
            </blockquote>
            <blockquote>
                <p>« Service impeccable et résultats au-delà de nos attentes. Je recommande vivement ! »</p>
                <footer>— <cite>Jean Martin, CEO TechStart</cite></footer>
            </blockquote>
        </section>
    </main>

    <aside>
        <section>
            <h3>Actualités</h3>
            <article>
                <h4>Nouveau site web pour TechCorp</h4>
                <time datetime="2024-01-15">15 janvier 2024</time>
                <p>Nous avons lancé le nouveau site web de TechCorp...</p>
            </article>
        </section>
    </aside>

    <footer>
        <section>
            <h3>Contact</h3>
            <address>
                <p>123 Rue de la Créativité<br>
                75001 Paris</p>
                <p>Téléphone : <a href="tel:+33123456789">01 23 45 67 89</a></p>
                <p>Email : <a href="mailto:contact@webcrea.com">contact@webcrea.com</a></p>
            </address>
        </section>
        
        <nav aria-label="Navigation footer">
            <ul>
                <li><a href="legal.html">Mentions légales</a></li>
                <li><a href="privacy.html">Confidentialité</a></li>
                <li><a href="sitemap.html">Plan du site</a></li>
            </ul>
        </nav>
        
        <p>&copy; 2024 WebCréa. Tous droits réservés.</p>
    </footer>
</body>
</html>
```

## ✅ Grille d'évaluation

### Structure et sémantique (25 points)
- [ ] DOCTYPE HTML5 et structure valide
- [ ] Balises sémantiques appropriées
- [ ] Hiérarchie des titres respectée
- [ ] Métadonnées complètes

### Navigation et liens (20 points)
- [ ] Navigation cohérente sur toutes les pages
- [ ] Liens internes fonctionnels
- [ ] Attributs appropriés (target, rel, etc.)
- [ ] Fil d'Ariane sur les pages secondaires

### Contenu et médias (20 points)
- [ ] Contenu pertinent et bien structuré
- [ ] Images avec attributs alt appropriés
- [ ] Utilisation de figure/figcaption
- [ ] Images responsives

### Formulaires (15 points)
- [ ] Formulaire de contact fonctionnel
- [ ] Validation HTML5 appropriée
- [ ] Labels et fieldsets corrects
- [ ] Différents types d'inputs

### Accessibilité (10 points)
- [ ] Navigation au clavier possible
- [ ] Attributs ARIA appropriés
- [ ] Contrastes et lisibilité
- [ ] Structure logique

### Qualité du code (10 points)
- [ ] Code propre et indenté
- [ ] Validation HTML5 sans erreurs
- [ ] Commentaires pertinents
- [ ] Organisation des fichiers

## 🚀 Étapes de réalisation

### Phase 1 : Planification (1 heure)
1. Choisir le type d'entreprise
2. Définir le contenu de chaque page
3. Créer la structure de fichiers
4. Rassembler les images nécessaires

### Phase 2 : Développement (6-8 heures)
1. Créer la structure HTML de base
2. Développer la page d'accueil
3. Créer les pages secondaires
4. Intégrer les médias
5. Développer le formulaire de contact

### Phase 3 : Finalisation (2 heures)
1. Tester tous les liens
2. Valider le code HTML
3. Vérifier l'accessibilité
4. Optimiser les performances

## 📝 Livrables

1. **Code source** : Tous les fichiers HTML organisés
2. **README.md** : Documentation du projet
3. **Présentation** : Description des choix techniques
4. **Auto-évaluation** : Utilisation de la grille d'évaluation

## 🎯 Conseils pour réussir

- Commencez par une structure simple et étoffez progressivement
- Validez régulièrement votre code avec le validateur W3C
- Testez votre site dans différents navigateurs
- Pensez à l'accessibilité dès le début
- Organisez votre code avec des commentaires
- Utilisez des images libres de droits

## 🔗 Ressources utiles

- [Validateur HTML W3C](https://validator.w3.org/)
- [Images libres : Unsplash](https://unsplash.com/)
- [Icônes : Font Awesome](https://fontawesome.com/)
- [Générateur de texte : Lorem Ipsum](https://www.lipsum.com/)

---

**Temps estimé :** 10-12 heures  
**Date limite :** À définir selon votre progression

## 🏆 Critères d'excellence

Pour aller plus loin, vous pouvez :
- Créer des pages supplémentaires
- Intégrer des éléments HTML5 avancés
- Optimiser les performances
- Améliorer l'accessibilité
- Ajouter des microformats

**Bonne chance pour votre projet final !**