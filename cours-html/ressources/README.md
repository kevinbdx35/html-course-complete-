# Ressources - Cours HTML

## 📚 Documentation officielle

### Spécifications et standards

- **[HTML Living Standard](https://html.spec.whatwg.org/)** - Spécification officielle du HTML
- **[W3C HTML5 Recommendation](https://www.w3.org/TR/html52/)** - Recommandation W3C pour HTML5
- **[MDN Web Docs - HTML](https://developer.mozilla.org/fr/docs/Web/HTML)** - Documentation complète et exemples

### Références rapides

- **[HTML Element Reference](https://developer.mozilla.org/fr/docs/Web/HTML/Element)** - Liste complète des éléments HTML
- **[HTML Attribute Reference](https://developer.mozilla.org/fr/docs/Web/HTML/Attributes)** - Tous les attributs HTML
- **[HTML5 Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)** - Guide des éléments sémantiques

## 🛠️ Outils de développement

### Éditeurs de code

- **[Visual Studio Code](https://code.visualstudio.com/)** - Éditeur gratuit avec extensions HTML
- **[Sublime Text](https://www.sublimetext.com/)** - Éditeur léger et rapide
- **[Atom](https://atom.io/)** - Éditeur open source (archivé mais toujours utilisable)

### Extensions VS Code recommandées

- **HTML CSS Support** - Autocomplétion et validation
- **Auto Rename Tag** - Renommage automatique des balises
- **Live Server** - Serveur local pour tester vos pages
- **Prettier** - Formatage automatique du code
- **HTML Snippets** - Raccourcis pour les balises HTML

### Outils de validation

- **[W3C Markup Validator](https://validator.w3.org/)** - Validation HTML officielle
- **[HTML5 Outliner](https://gsnedders.html5.org/outliner/)** - Vérification de la structure de document
- **[Link Checker](https://validator.w3.org/checklink)** - Vérification des liens

## ♿ Accessibilité

### Outils de test

- **[WAVE](https://wave.webaim.org/)** - Évaluation d'accessibilité web
- **[axe DevTools](https://www.deque.com/axe/devtools/)** - Extension navigateur pour tester l'accessibilité
- **[Lighthouse](https://developers.google.com/web/tools/lighthouse)** - Audit de performance et accessibilité

### Guides d'accessibilité

- **[WebAIM](https://webaim.org/)** - Ressources complètes sur l'accessibilité web
- **[WCAG Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)** - Guide des règles d'accessibilité
- **[A11Y Project](https://www.a11yproject.com/)** - Checklist et bonnes pratiques

## 🎨 Ressources visuelles

### Images libres de droits

- **[Unsplash](https://unsplash.com/)** - Photos haute qualité gratuites
- **[Pexels](https://www.pexels.com/)** - Photos et vidéos gratuites
- **[Pixabay](https://pixabay.com/)** - Images, illustrations et vecteurs
- **[Freepik](https://www.freepik.com/)** - Illustrations et vecteurs (avec attribution)

### Icônes

- **[Font Awesome](https://fontawesome.com/)** - Bibliothèque d'icônes populaire
- **[Feather Icons](https://feathericons.com/)** - Icônes minimalistes
- **[Heroicons](https://heroicons.com/)** - Icônes modernes et élégantes
- **[Material Design Icons](https://materialdesignicons.com/)** - Icônes Google Material

### Palettes de couleurs

- **[Coolors](https://coolors.co/)** - Générateur de palettes de couleurs
- **[Adobe Color](https://color.adobe.com/)** - Outil de création de palettes
- **[Paletton](https://paletton.com/)** - Générateur de palettes harmonieuses

## 📖 Tutoriels et guides

### Cours en ligne

- **[freeCodeCamp](https://www.freecodecamp.org/)** - Cours HTML gratuits et interactifs
- **[Codecademy](https://www.codecademy.com/learn/learn-html)** - Cours HTML interactifs
- **[W3Schools](https://www.w3schools.com/html/)** - Tutoriels HTML avec exemples

### Chaînes YouTube

- **[Traversy Media](https://www.youtube.com/user/TechGuyWeb)** - Tutoriels web complets
- **[freeCodeCamp.org](https://www.youtube.com/channel/UC8butISFwT-Wl7EV0hUK0BQ)** - Cours longs et détaillés
- **[The Net Ninja](https://www.youtube.com/channel/UCW5YeuERMmlnqo4oq8vwUpg)** - Tutoriels courts et efficaces

## 📝 Aide-mémoires (Cheat Sheets)

### HTML5 Cheat Sheet

```html
<!-- Structure de base -->
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Titre de la page</title>
</head>
<body>
    <!-- Contenu -->
</body>
</html>

<!-- Balises sémantiques -->
<header>En-tête</header>
<nav>Navigation</nav>
<main>Contenu principal</main>
<section>Section</section>
<article>Article</article>
<aside>Contenu secondaire</aside>
<footer>Pied de page</footer>

<!-- Balises de texte -->
<h1>Titre principal</h1>
<p>Paragraphe</p>
<strong>Important</strong>
<em>Emphase</em>
<mark>Surligné</mark>
<small>Petit texte</small>

<!-- Liens et médias -->
<a href="url">Lien</a>
<img src="image.jpg" alt="Description">
<audio controls><source src="audio.mp3"></audio>
<video controls><source src="video.mp4"></video>

<!-- Listes -->
<ul><li>Élément</li></ul>
<ol><li>Élément</li></ol>
<dl><dt>Terme</dt><dd>Définition</dd></dl>

<!-- Tableaux -->
<table>
    <thead><tr><th>En-tête</th></tr></thead>
    <tbody><tr><td>Cellule</td></tr></tbody>
</table>

<!-- Formulaires -->
<form action="/submit" method="post">
    <label for="input">Label :</label>
    <input type="text" id="input" name="input" required>
    <button type="submit">Envoyer</button>
</form>
```

### Attributs HTML courants

| Attribut | Utilisation | Exemple |
|----------|-------------|---------|
| `id` | Identifiant unique | `<div id="header">` |
| `class` | Classe CSS | `<p class="intro">` |
| `src` | Source d'un média | `<img src="image.jpg">` |
| `href` | Lien hypertexte | `<a href="page.html">` |
| `alt` | Texte alternatif | `<img alt="Description">` |
| `title` | Info-bulle | `<a title="Plus d'info">` |
| `target` | Cible du lien | `<a target="_blank">` |
| `rel` | Relation du lien | `<a rel="noopener">` |
| `required` | Champ obligatoire | `<input required>` |
| `placeholder` | Texte d'aide | `<input placeholder="Nom">` |

## 🔧 Snippets utiles

### Template HTML5 de base

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Description de la page">
    <meta name="author" content="Votre nom">
    <title>Titre de la page</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Titre principal</h1>
        <nav>
            <ul>
                <li><a href="#home">Accueil</a></li>
                <li><a href="#about">À propos</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <h2>Accueil</h2>
            <p>Contenu de la section d'accueil.</p>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Mon site. Tous droits réservés.</p>
    </footer>
</body>
</html>
```

### Formulaire de contact

```html
<form action="/contact" method="post">
    <fieldset>
        <legend>Informations personnelles</legend>
        
        <label for="name">Nom :</label>
        <input type="text" id="name" name="name" required>
        
        <label for="email">Email :</label>
        <input type="email" id="email" name="email" required>
        
        <label for="phone">Téléphone :</label>
        <input type="tel" id="phone" name="phone">
    </fieldset>
    
    <fieldset>
        <legend>Message</legend>
        
        <label for="subject">Sujet :</label>
        <select id="subject" name="subject" required>
            <option value="">Choisissez un sujet</option>
            <option value="info">Demande d'information</option>
            <option value="support">Support technique</option>
            <option value="other">Autre</option>
        </select>
        
        <label for="message">Message :</label>
        <textarea id="message" name="message" rows="5" required></textarea>
    </fieldset>
    
    <button type="submit">Envoyer</button>
</form>
```

## 🌐 Communautés et forums

### Forums d'aide

- **[Stack Overflow](https://stackoverflow.com/)** - Questions/réponses techniques
- **[Reddit - r/webdev](https://www.reddit.com/r/webdev/)** - Communauté de développeurs
- **[Discord - The Programmer's Hangout](https://theprogrammershangout.com/)** - Chat en temps réel

### Blogs et newsletters

- **[CSS-Tricks](https://css-tricks.com/)** - Articles sur HTML, CSS et JavaScript
- **[A List Apart](https://alistapart.com/)** - Articles sur les standards web
- **[Smashing Magazine](https://www.smashingmagazine.com/)** - Ressources pour développeurs

## 📱 Outils mobiles

### Applications

- **[Buffer Editor](https://buffer-editor.com/)** - Éditeur de code mobile
- **[Dcoder](https://dcoder.tech/)** - IDE mobile pour le développement web
- **[Acode](https://acode.foxdebug.com/)** - Éditeur de code Android

## 📊 Statistiques et standards

### Compatibilité navigateurs

- **[Can I Use](https://caniuse.com/)** - Compatibilité des fonctionnalités HTML5
- **[MDN Browser Compatibility](https://developer.mozilla.org/fr/docs/Web/HTML/Element)** - Données de compatibilité

### Tendances web

- **[State of HTML](https://stateofjs.com/)** - Tendances et statistiques
- **[Web Almanac](https://almanac.httparchive.org/)** - État du web par HTTP Archive

## 🎯 Mémo des erreurs courantes

### Erreurs fréquentes à éviter

1. **Oublier le DOCTYPE** : `<!DOCTYPE html>`
2. **Balises non fermées** : `<p>Texte</p>`
3. **Attributs sans guillemets** : `<img src="image.jpg">`
4. **Mauvaise hiérarchie des titres** : h1 → h2 → h3
5. **Images sans alt** : `<img src="..." alt="Description">`
6. **Labels non associés** : `<label for="id">` avec `<input id="id">`
7. **Formulaires sans action** : `<form action="/submit">`

### Checklist de validation

- [ ] DOCTYPE présent
- [ ] Balises fermées correctement
- [ ] Attributs entre guillemets
- [ ] Images avec alt
- [ ] Liens fonctionnels
- [ ] Formulaires avec labels
- [ ] Structure sémantique
- [ ] Validation W3C sans erreurs

---

**Cette liste de ressources est régulièrement mise à jour. N'hésitez pas à bookmarquer cette page !**