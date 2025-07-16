# Module 2 : Structure de base d'un document HTML

## 🎯 Objectifs du module

- Comprendre la structure fondamentale d'un document HTML
- Maîtriser les balises essentielles `<html>`, `<head>`, `<body>`
- Connaître les métadonnées importantes
- Savoir organiser le contenu d'une page

## 🏗️ Anatomie d'un document HTML

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <!-- Métadonnées -->
</head>
<body>
    <!-- Contenu visible -->
</body>
</html>
```

## 📄 La déclaration DOCTYPE

```html
<!DOCTYPE html>
```

- **Rôle** : Indique au navigateur qu'il s'agit d'un document HTML5
- **Position** : Toujours en première ligne
- **Importance** : Assure un rendu correct et cohérent

## 🌐 L'élément racine `<html>`

```html
<html lang="fr">
    <!-- Tout le contenu du document -->
</html>
```

### Attributs importants :
- `lang="fr"` : Spécifie la langue du document
- `dir="ltr"` : Direction du texte (gauche à droite)

## 🧠 La section `<head>`

Contient les métadonnées (informations sur le document) :

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Description de la page">
    <meta name="keywords" content="mot1, mot2, mot3">
    <meta name="author" content="Votre nom">
    <title>Titre de la page</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
```

### Métadonnées essentielles :

#### `<meta charset="UTF-8">`
- **Rôle** : Définit l'encodage des caractères
- **Importance** : Évite les problèmes d'affichage des caractères spéciaux

#### `<meta name="viewport">`
- **Rôle** : Contrôle l'affichage sur les appareils mobiles
- **Exemple** : `content="width=device-width, initial-scale=1.0"`

#### `<title>`
- **Rôle** : Titre affiché dans l'onglet du navigateur
- **SEO** : Important pour le référencement

## 👁️ La section `<body>`

Contient tout le contenu visible de la page :

```html
<body>
    <header>
        <!-- En-tête de la page -->
    </header>
    
    <main>
        <!-- Contenu principal -->
    </main>
    
    <footer>
        <!-- Pied de page -->
    </footer>
</body>
```

## 📝 Exemple complet

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Mon site web personnel">
    <meta name="author" content="Jean Dupont">
    <title>Accueil - Mon site web</title>
</head>
<body>
    <header>
        <h1>Bienvenue sur mon site</h1>
        <nav>
            <ul>
                <li><a href="#accueil">Accueil</a></li>
                <li><a href="#apropos">À propos</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="accueil">
            <h2>Accueil</h2>
            <p>Contenu de la page d'accueil.</p>
        </section>
    </main>
    
    <footer>
        <p>&copy; 2024 Mon site web. Tous droits réservés.</p>
    </footer>
</body>
</html>
```

## ✅ Exercice pratique

1. Créez un document HTML avec la structure complète
2. Ajoutez des métadonnées pertinentes
3. Créez un en-tête, un contenu principal et un pied de page
4. Validez votre code avec le [validateur W3C](https://validator.w3.org/)

## 🔍 Bonnes pratiques

- Toujours inclure `<!DOCTYPE html>`
- Spécifier la langue avec `lang="fr"`
- Utiliser l'encodage UTF-8
- Ajouter une description et un titre pertinents
- Structurer le contenu avec header, main, footer

## 🔗 Ressources supplémentaires

- [MDN - Structure d'un document HTML](https://developer.mozilla.org/fr/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
- [W3C HTML Validator](https://validator.w3.org/)

---

**Temps estimé :** 1.5 heure  
**Prochaine étape :** [Module 3 - Éléments de texte](../03-elements-texte/)