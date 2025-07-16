# Exercices pratiques - Cours HTML

## 📚 Organisation des exercices

Ce dossier contient tous les exercices pratiques pour accompagner les modules du cours HTML. Chaque exercice est conçu pour renforcer les concepts appris dans les modules correspondants.

## 📂 Structure des exercices

### Exercice 1 : Premier site web
**Module correspondant :** [01-introduction](../01-introduction/) et [02-structure-base](../02-structure-base/)

**Objectif :** Créer votre première page web avec une structure HTML5 valide

**Fichiers à créer :**
- `exercice-01/index.html`
- `exercice-01/about.html`

**Instructions :**
1. Créez une page d'accueil avec la structure HTML5 de base
2. Ajoutez un titre principal, des métadonnées et du contenu simple
3. Créez une page "À propos" liée à la page d'accueil
4. Validez votre code avec le validateur W3C

---

### Exercice 2 : Mise en forme du texte
**Module correspondant :** [03-elements-texte](../03-elements-texte/)

**Objectif :** Utiliser les balises de formatage de texte

**Fichiers à créer :**
- `exercice-02/article.html`

**Instructions :**
1. Créez un article de blog avec :
   - Hiérarchie de titres (h1-h3)
   - Paragraphes avec formatage (strong, em, mark)
   - Citations (blockquote)
   - Listes à puces et numérotées
   - Abréviations et définitions

---

### Exercice 3 : Navigation et liens
**Module correspondant :** [04-liens-navigation](../04-liens-navigation/)

**Objectif :** Créer une navigation complète avec différents types de liens

**Fichiers à créer :**
- `exercice-03/index.html`
- `exercice-03/services.html`
- `exercice-03/contact.html`

**Instructions :**
1. Créez un site avec navigation principale
2. Ajoutez des liens internes (ancres)
3. Incluez des liens externes, email et téléphone
4. Créez un menu de navigation responsive

---

### Exercice 4 : Galerie multimédia
**Module correspondant :** [05-medias](../05-medias/)

**Objectif :** Intégrer images, audio et vidéo

**Fichiers à créer :**
- `exercice-04/galerie.html`
- `exercice-04/images/` (dossier d'images)

**Instructions :**
1. Créez une galerie d'images avec `figure` et `figcaption`
2. Intégrez un lecteur audio
3. Ajoutez une vidéo avec contrôles
4. Utilisez des images responsives

---

### Exercice 5 : Structure sémantique
**Module correspondant :** [06-structure-semantique](../06-structure-semantique/)

**Objectif :** Créer une structure HTML5 sémantique complète

**Fichiers à créer :**
- `exercice-05/blog.html`

**Instructions :**
1. Créez un blog avec :
   - Header avec navigation
   - Main avec articles
   - Aside avec widgets
   - Footer avec informations
2. Utilisez toutes les balises sémantiques HTML5

---

### Exercice 6 : Tableaux et listes
**Module correspondant :** [07-listes-tableaux](../07-listes-tableaux/)

**Objectif :** Créer des tableaux accessibles et des listes structurées

**Fichiers à créer :**
- `exercice-06/data.html`

**Instructions :**
1. Créez un tableau de données avec :
   - En-têtes appropriés
   - Fusion de cellules
   - Caption et summary
2. Ajoutez différents types de listes

---

### Exercice 7 : Formulaire complet
**Module correspondant :** [08-formulaires](../08-formulaires/)

**Objectif :** Créer un formulaire complexe avec validation

**Fichiers à créer :**
- `exercice-07/inscription.html`

**Instructions :**
1. Créez un formulaire d'inscription avec :
   - Tous les types d'inputs
   - Validation HTML5
   - Groupement avec fieldset
   - Accessibilité complète

---

## 🎯 Correction des exercices

### Auto-évaluation

Pour chaque exercice, vérifiez :
- [ ] Le code HTML est valide (validateur W3C)
- [ ] La structure est sémantique
- [ ] L'accessibilité est respectée
- [ ] Les liens fonctionnent correctement
- [ ] Les images ont des attributs alt appropriés

### Critères de réussite

**Niveau débutant :**
- Code HTML5 valide
- Structure de base correcte
- Utilisation des balises appropriées

**Niveau intermédiaire :**
- Sémantique HTML5 respectée
- Navigation fonctionnelle
- Médias intégrés correctement

**Niveau avancé :**
- Accessibilité optimisée
- Performance optimisée
- Bonnes pratiques respectées

## 📋 Modèle de fichier d'exercice

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice [Numéro] - [Titre]</title>
</head>
<body>
    <header>
        <h1>Exercice [Numéro]</h1>
        <nav>
            <!-- Navigation si nécessaire -->
        </nav>
    </header>

    <main>
        <!-- Contenu principal de l'exercice -->
    </main>

    <footer>
        <p>&copy; 2024 - Exercice du cours HTML</p>
    </footer>
</body>
</html>
```

## 🔧 Outils recommandés

- **Éditeur :** VS Code avec extension HTML
- **Validation :** [W3C Markup Validator](https://validator.w3.org/)
- **Accessibilité :** [WAVE Web Accessibility Evaluation Tool](https://wave.webaim.org/)
- **Images :** [Unsplash](https://unsplash.com/) pour des images libres

## 📝 Suivi de progression

Créez un fichier `progression.md` dans votre dossier d'exercices :

```markdown
# Ma progression

## Exercices terminés
- [x] Exercice 1 : Premier site web
- [x] Exercice 2 : Mise en forme du texte
- [ ] Exercice 3 : Navigation et liens
- [ ] Exercice 4 : Galerie multimédia
- [ ] Exercice 5 : Structure sémantique
- [ ] Exercice 6 : Tableaux et listes
- [ ] Exercice 7 : Formulaire complet

## Notes et difficultés
- Exercice 1 : Difficulté avec les métadonnées
- Exercice 2 : Bien maîtrisé les balises de formatage
```

## 🏆 Conseils pour réussir

1. **Pratiquez régulièrement** : Faites un exercice après chaque module
2. **Validez votre code** : Utilisez toujours le validateur W3C
3. **Testez l'accessibilité** : Naviguez au clavier et utilisez un lecteur d'écran
4. **Documentez votre progression** : Notez vos difficultés et réussites
5. **Demandez de l'aide** : N'hésitez pas à consulter les ressources supplémentaires

---

**Temps estimé total :** 15-20 heures  
**Difficulté :** Progressive du débutant à intermédiaire