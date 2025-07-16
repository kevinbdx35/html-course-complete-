# Module 1 : Introduction au CSS

## 🎯 Objectifs du module

- Comprendre le rôle du CSS dans le développement web
- Découvrir l'histoire et l'évolution du CSS
- Apprendre les trois façons d'intégrer le CSS
- Créer votre premier style CSS

## 📚 Qu'est-ce que le CSS ?

**CSS** (Cascading Style Sheets) est le langage utilisé pour décrire la présentation d'un document HTML. Il contrôle l'apparence, la mise en page et le comportement visuel des pages web.

### Rôle du CSS dans le trio web :
- **HTML** : Structure et contenu (le squelette)
- **CSS** : Présentation et design (la peau)
- **JavaScript** : Comportement et interactivité (les muscles)

## 🎨 Pourquoi utiliser CSS ?

### Avantages :
- **Séparation des préoccupations** : Sépare contenu et présentation
- **Réutilisabilité** : Un seul fichier CSS pour plusieurs pages
- **Maintenance** : Changements centralisés
- **Performance** : Fichiers mis en cache par le navigateur
- **Accessibilité** : Améliore l'expérience utilisateur

### Exemple concret :
```html
<!-- Sans CSS -->
<h1>Titre principal</h1>
<p>Paragraphe normal</p>

<!-- Avec CSS -->
<h1 style="color: blue; font-size: 2em;">Titre principal</h1>
<p style="color: gray; line-height: 1.5;">Paragraphe stylisé</p>
```

## 🔧 Les trois façons d'intégrer CSS

### 1. CSS inline (dans l'attribut style)

```html
<h1 style="color: red; font-size: 24px;">Titre avec CSS inline</h1>
<p style="background-color: yellow; padding: 10px;">Paragraphe stylisé</p>
```

**Avantages :** Rapide pour des tests  
**Inconvénients :** Difficile à maintenir, pas de réutilisabilité

### 2. CSS interne (dans la balise `<style>`)

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        h1 {
            color: blue;
            font-size: 2em;
            text-align: center;
        }
        
        p {
            color: gray;
            line-height: 1.6;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <h1>Titre principal</h1>
    <p>Contenu du paragraphe</p>
</body>
</html>
```

**Avantages :** Centralisé dans le document  
**Inconvénients :** Pas de réutilisabilité entre pages

### 3. CSS externe (fichier .css séparé)

**style.css :**
```css
/* Styles pour les titres */
h1 {
    color: #333;
    font-size: 2.5em;
    font-weight: bold;
    margin-bottom: 20px;
}

/* Styles pour les paragraphes */
p {
    color: #666;
    line-height: 1.8;
    margin: 15px 0;
}
```

**index.html :**
```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Titre principal</h1>
    <p>Contenu du paragraphe</p>
</body>
</html>
```

**Avantages :** Réutilisable, maintenable, performance  
**Inconvénients :** Fichier supplémentaire

## 🏗️ Anatomie d'une règle CSS

```css
sélecteur {
    propriété: valeur;
    propriété: valeur;
}
```

### Exemple détaillé :

```css
h1 {                    /* Sélecteur */
    color: blue;        /* Propriété: valeur; */
    font-size: 24px;    /* Propriété: valeur; */
    text-align: center; /* Propriété: valeur; */
}                       /* Fin du bloc */
```

### Composants :
- **Sélecteur** : Cible les éléments HTML
- **Propriété** : Aspect à modifier
- **Valeur** : Nouvelle valeur de la propriété
- **Déclaration** : Paire propriété-valeur
- **Bloc de déclarations** : Ensemble entre accolades

## 💻 Votre premier style CSS

### Exercice guidé :

1. **Créez un fichier HTML** (`index.html`) :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mon premier CSS</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bienvenue dans le monde du CSS</h1>
    <p>Ce paragraphe va être stylisé avec CSS.</p>
    <p>Voici un second paragraphe pour voir la différence.</p>
</body>
</html>
```

2. **Créez un fichier CSS** (`style.css`) :

```css
/* Réinitialisation de base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Styles pour le body */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}

/* Styles pour le titre */
h1 {
    color: #2c3e50;
    font-size: 2.5em;
    text-align: center;
    margin-bottom: 30px;
    border-bottom: 3px solid #3498db;
    padding-bottom: 10px;
}

/* Styles pour les paragraphes */
p {
    color: #555;
    font-size: 1.1em;
    margin-bottom: 20px;
    padding: 15px;
    background-color: #f8f9fa;
    border-left: 4px solid #3498db;
}
```

3. **Ouvrez le fichier** dans votre navigateur et observez la transformation !

## 🛠️ Outils de développement

### Navigateur (F12) :
- **Inspecteur** : Voir le HTML et CSS appliqué
- **Computed** : Voir les styles calculés
- **Console** : Débogage et tests

### Extensions VS Code :
- **Live Server** : Serveur local pour tester
- **CSS Peek** : Navigation dans le CSS
- **Autoprefixer** : Compatibilité navigateurs

## 🔍 Concepts clés à retenir

### La cascade CSS :
1. **Importance** : `!important`
2. **Spécificité** : ID > classe > élément
3. **Ordre d'apparition** : Le dernier gagne

### Héritage :
Certaines propriétés sont héritées des parents :
```css
body {
    color: blue;  /* Hérité par tous les éléments */
}

h1 {
    color: red;   /* Surcharge l'héritage */
}
```

## ✅ Exercice pratique

1. Créez une page HTML avec :
   - Un titre principal
   - Deux paragraphes
   - Une liste à puces

2. Créez un fichier CSS externe qui :
   - Change la couleur du titre
   - Modifie la taille de police des paragraphes
   - Ajoute un arrière-plan coloré
   - Style la liste

3. Testez les trois méthodes d'intégration CSS

## 🎯 Bonnes pratiques

- **Utilisez CSS externe** pour la production
- **Organisez votre code** avec des commentaires
- **Testez dans différents navigateurs**
- **Utilisez des noms de classe descriptifs**
- **Évitez les styles inline** sauf exceptions

## 🔗 Ressources supplémentaires

- [MDN CSS](https://developer.mozilla.org/fr/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/) - Compatibilité CSS

---

**Temps estimé :** 2 heures  
**Prochaine étape :** [Module 2 - Syntaxe et sélecteurs](../02-syntaxe-selecteurs/)