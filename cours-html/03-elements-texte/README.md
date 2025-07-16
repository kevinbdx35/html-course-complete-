# Module 3 : Éléments de texte et formatage

## 🎯 Objectifs du module

- Maîtriser les balises de titre (h1 à h6)
- Utiliser les balises de paragraphe et de formatage
- Comprendre la sémantique des éléments de texte
- Structurer le contenu textuel efficacement

## 📑 Hiérarchie des titres

### Balises de titre (h1 à h6)

```html
<h1>Titre principal</h1>
<h2>Titre de section</h2>
<h3>Titre de sous-section</h3>
<h4>Titre de niveau 4</h4>
<h5>Titre de niveau 5</h5>
<h6>Titre de niveau 6</h6>
```

### Règles importantes :
- **Un seul h1** par page (titre principal)
- **Hiérarchie logique** : ne pas sauter de niveaux
- **Sémantique** : structure le contenu pour les lecteurs d'écran

## 📝 Paragraphes et texte

### Paragraphe `<p>`

```html
<p>Ceci est un paragraphe de texte. Il peut contenir plusieurs phrases et sera affiché comme un bloc séparé.</p>
<p>Ceci est un second paragraphe.</p>
```

### Saut de ligne `<br>`

```html
<p>Première ligne<br>
Deuxième ligne sur la même paragraphe</p>
```

### Ligne horizontale `<hr>`

```html
<p>Contenu avant la ligne</p>
<hr>
<p>Contenu après la ligne</p>
```

## 🎨 Formatage du texte

### Importance et emphase

```html
<p>Texte <strong>important</strong> et texte <em>avec emphase</em></p>
<p>Texte <b>gras</b> et texte <i>italique</i></p>
```

**Différence importante :**
- `<strong>` et `<em>` : importance sémantique
- `<b>` et `<i>` : formatage visuel uniquement

### Autres éléments de formatage

```html
<p>Texte <mark>surligné</mark></p>
<p>Texte <del>supprimé</del> et <ins>inséré</ins></p>
<p>Texte <small>petit</small> et <sub>indice</sub> et <sup>exposant</sup></p>
<p>Formule chimique : H<sub>2</sub>O</p>
<p>Équation : E = mc<sup>2</sup></p>
```

## 🔤 Éléments spécialisés

### Citations

```html
<!-- Citation courte -->
<p>Einstein a dit : <q>L'imagination est plus importante que la connaissance.</q></p>

<!-- Citation longue -->
<blockquote cite="https://source.com">
    <p>La vie, c'est comme une bicyclette, il faut avancer pour ne pas perdre l'équilibre.</p>
    <footer>— <cite>Albert Einstein</cite></footer>
</blockquote>
```

### Code et contenu technique

```html
<p>Utilisez la balise <code>&lt;p&gt;</code> pour créer un paragraphe.</p>

<pre><code>function hello() {
    console.log("Hello World!");
}
</code></pre>

<p>Appuyez sur <kbd>Ctrl</kbd> + <kbd>C</kbd> pour copier.</p>
```

### Abréviations et définitions

```html
<p>Le <abbr title="HyperText Markup Language">HTML</abbr> est le langage de base du web.</p>

<p>Le <dfn>HTML</dfn> est le langage de balisage pour créer des pages web.</p>
```

## 📊 Exemple complet

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Éléments de texte - Exemple</title>
</head>
<body>
    <h1>Guide du développeur web</h1>
    
    <h2>Introduction</h2>
    <p>Le développement web est une discipline en <em>constante évolution</em>. 
    Il est <strong>essentiel</strong> de rester à jour avec les dernières technologies.</p>
    
    <h2>Technologies de base</h2>
    <p>Les trois piliers du développement web front-end sont :</p>
    
    <h3>HTML</h3>
    <p>Le <abbr title="HyperText Markup Language">HTML</abbr> structure le contenu.</p>
    
    <h3>CSS</h3>
    <p>Le <abbr title="Cascading Style Sheets">CSS</abbr> gère la présentation.</p>
    
    <h3>JavaScript</h3>
    <p>JavaScript ajoute l'interactivité.</p>
    
    <hr>
    
    <h2>Citation inspirante</h2>
    <blockquote>
        <p>Le code est comme l'humour. Quand vous devez l'expliquer, c'est mauvais.</p>
        <footer>— <cite>Cory House</cite></footer>
    </blockquote>
    
    <h2>Exemple de code</h2>
    <p>Voici un exemple de fonction JavaScript :</p>
    <pre><code>function saluer(nom) {
    return "Bonjour " + nom + "!";
}
    </code></pre>
    
    <p><small>Note : Ce code est donné à titre d'exemple.</small></p>
</body>
</html>
```

## ✅ Exercice pratique

1. Créez une page "À propos" avec :
   - Un titre principal h1
   - Au moins 3 sections avec des h2
   - Des paragraphes avec différents formatages
   - Une citation en blockquote
   - Un exemple de code

2. Utilisez au moins 5 balises de formatage différentes

3. Validez votre HTML avec le validateur W3C

## 🔍 Bonnes pratiques

- Respecter la hiérarchie des titres
- Utiliser `<strong>` et `<em>` pour la sémantique
- Éviter `<br>` pour créer des espaces (utiliser CSS)
- Ajouter des attributs `title` aux abréviations
- Citer les sources avec `cite`

## 🔗 Ressources supplémentaires

- [MDN - Éléments de texte HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element#contenu_textuel)
- [Liste complète des entités HTML](https://developer.mozilla.org/fr/docs/Glossary/Entity)

---

**Temps estimé :** 2 heures  
**Prochaine étape :** [Module 4 - Liens et navigation](../04-liens-navigation/)