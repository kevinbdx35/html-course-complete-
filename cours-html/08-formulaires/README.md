# Module 8 : Formulaires

## 🎯 Objectifs du module

- Créer des formulaires interactifs
- Maîtriser tous les types d'inputs
- Implémenter la validation HTML5
- Comprendre l'accessibilité des formulaires

## 📝 Structure de base d'un formulaire

```html
<form action="/submit" method="post">
    <label for="name">Nom :</label>
    <input type="text" id="name" name="name" required>
    
    <button type="submit">Envoyer</button>
</form>
```

### Attributs de `<form>`

```html
<form action="/process"           <!-- URL de traitement -->
      method="post"               <!-- GET ou POST -->
      enctype="multipart/form-data" <!-- Pour les fichiers -->
      target="_blank"             <!-- Cible d'ouverture -->
      autocomplete="off"          <!-- Désactiver l'autocomplétion -->
      novalidate>                 <!-- Désactiver la validation -->
</form>
```

## 🔤 Types d'inputs

### Inputs de texte

```html
<label for="text">Texte simple :</label>
<input type="text" id="text" name="text" placeholder="Tapez votre texte">

<label for="email">Email :</label>
<input type="email" id="email" name="email" placeholder="exemple@domain.com">

<label for="password">Mot de passe :</label>
<input type="password" id="password" name="password">

<label for="search">Recherche :</label>
<input type="search" id="search" name="search" placeholder="Rechercher...">

<label for="url">URL :</label>
<input type="url" id="url" name="url" placeholder="https://exemple.com">

<label for="tel">Téléphone :</label>
<input type="tel" id="tel" name="tel" placeholder="01 23 45 67 89">
```

### Inputs numériques

```html
<label for="number">Nombre :</label>
<input type="number" id="number" name="number" min="1" max="100" step="1">

<label for="range">Plage :</label>
<input type="range" id="range" name="range" min="0" max="100" value="50">

<label for="price">Prix :</label>
<input type="number" id="price" name="price" min="0" step="0.01" placeholder="0.00">
```

### Inputs de date et heure

```html
<label for="date">Date :</label>
<input type="date" id="date" name="date">

<label for="time">Heure :</label>
<input type="time" id="time" name="time">

<label for="datetime">Date et heure :</label>
<input type="datetime-local" id="datetime" name="datetime">

<label for="month">Mois :</label>
<input type="month" id="month" name="month">

<label for="week">Semaine :</label>
<input type="week" id="week" name="week">
```

### Inputs de sélection

```html
<!-- Cases à cocher -->
<input type="checkbox" id="newsletter" name="newsletter" value="yes">
<label for="newsletter">S'abonner à la newsletter</label>

<input type="checkbox" id="terms" name="terms" required>
<label for="terms">J'accepte les conditions d'utilisation</label>

<!-- Boutons radio -->
<fieldset>
    <legend>Choisissez votre genre :</legend>
    <input type="radio" id="male" name="gender" value="male">
    <label for="male">Homme</label>
    
    <input type="radio" id="female" name="gender" value="female">
    <label for="female">Femme</label>
    
    <input type="radio" id="other" name="gender" value="other">
    <label for="other">Autre</label>
</fieldset>
```

### Inputs de fichier

```html
<label for="file">Choisir un fichier :</label>
<input type="file" id="file" name="file" accept=".pdf,.doc,.docx">

<label for="image">Image :</label>
<input type="file" id="image" name="image" accept="image/*">

<label for="multiple">Plusieurs fichiers :</label>
<input type="file" id="multiple" name="multiple[]" multiple>
```

## 📋 Éléments de sélection

### Menu déroulant `<select>`

```html
<label for="country">Pays :</label>
<select id="country" name="country">
    <option value="">Choisissez un pays</option>
    <option value="fr">France</option>
    <option value="be">Belgique</option>
    <option value="ch">Suisse</option>
</select>

<!-- Avec groupes -->
<label for="cuisine">Type de cuisine :</label>
<select id="cuisine" name="cuisine">
    <optgroup label="Européenne">
        <option value="french">Française</option>
        <option value="italian">Italienne</option>
        <option value="spanish">Espagnole</option>
    </optgroup>
    <optgroup label="Asiatique">
        <option value="japanese">Japonaise</option>
        <option value="chinese">Chinoise</option>
        <option value="thai">Thaïlandaise</option>
    </optgroup>
</select>

<!-- Sélection multiple -->
<label for="skills">Compétences :</label>
<select id="skills" name="skills[]" multiple size="4">
    <option value="html">HTML</option>
    <option value="css">CSS</option>
    <option value="js">JavaScript</option>
    <option value="react">React</option>
</select>
```

### Zone de texte `<textarea>`

```html
<label for="message">Message :</label>
<textarea id="message" 
          name="message" 
          rows="5" 
          cols="50"
          placeholder="Tapez votre message ici..."
          maxlength="500"></textarea>
```

## 🎛️ Groupement et organisation

### Groupement avec `<fieldset>` et `<legend>`

```html
<form>
    <fieldset>
        <legend>Informations personnelles</legend>
        <label for="firstName">Prénom :</label>
        <input type="text" id="firstName" name="firstName" required>
        
        <label for="lastName">Nom :</label>
        <input type="text" id="lastName" name="lastName" required>
        
        <label for="birthDate">Date de naissance :</label>
        <input type="date" id="birthDate" name="birthDate">
    </fieldset>
    
    <fieldset>
        <legend>Adresse</legend>
        <label for="street">Rue :</label>
        <input type="text" id="street" name="street">
        
        <label for="city">Ville :</label>
        <input type="text" id="city" name="city">
        
        <label for="zipCode">Code postal :</label>
        <input type="text" id="zipCode" name="zipCode" pattern="[0-9]{5}">
    </fieldset>
</form>
```

## ✅ Validation HTML5

### Attributs de validation

```html
<!-- Champ obligatoire -->
<input type="text" name="name" required>

<!-- Longueur min/max -->
<input type="text" name="username" minlength="3" maxlength="20">

<!-- Valeur min/max pour les nombres -->
<input type="number" name="age" min="18" max="120">

<!-- Expression régulière -->
<input type="text" name="phone" pattern="[0-9]{2}\s[0-9]{2}\s[0-9]{2}\s[0-9]{2}\s[0-9]{2}">

<!-- Validation par type -->
<input type="email" name="email" required>
<input type="url" name="website">
```

### Messages de validation personnalisés

```html
<input type="email" 
       name="email" 
       required 
       title="Veuillez entrer une adresse email valide">

<input type="text" 
       name="phone" 
       pattern="[0-9]{10}" 
       title="Veuillez entrer 10 chiffres">
```

## 🔘 Types de boutons

```html
<!-- Bouton de soumission -->
<button type="submit">Envoyer</button>
<input type="submit" value="Envoyer">

<!-- Bouton de réinitialisation -->
<button type="reset">Réinitialiser</button>
<input type="reset" value="Réinitialiser">

<!-- Bouton normal -->
<button type="button" onclick="doSomething()">Bouton personnalisé</button>
<input type="button" value="Cliquez-moi" onclick="doSomething()">

<!-- Bouton image -->
<input type="image" src="submit-button.png" alt="Envoyer">
```

## 🎨 Formulaire complet d'exemple

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulaire d'inscription</title>
</head>
<body>
    <form action="/register" method="post" enctype="multipart/form-data">
        <h1>Inscription</h1>
        
        <fieldset>
            <legend>Informations personnelles</legend>
            
            <label for="title">Civilité :</label>
            <select id="title" name="title" required>
                <option value="">Choisissez</option>
                <option value="mr">M.</option>
                <option value="mrs">Mme</option>
                <option value="miss">Mlle</option>
            </select>
            
            <label for="firstName">Prénom :</label>
            <input type="text" id="firstName" name="firstName" required minlength="2">
            
            <label for="lastName">Nom :</label>
            <input type="text" id="lastName" name="lastName" required minlength="2">
            
            <label for="birthDate">Date de naissance :</label>
            <input type="date" id="birthDate" name="birthDate" required>
            
            <label for="avatar">Photo de profil :</label>
            <input type="file" id="avatar" name="avatar" accept="image/*">
        </fieldset>
        
        <fieldset>
            <legend>Coordonnées</legend>
            
            <label for="email">Email :</label>
            <input type="email" id="email" name="email" required>
            
            <label for="phone">Téléphone :</label>
            <input type="tel" id="phone" name="phone" pattern="[0-9]{10}">
            
            <label for="website">Site web :</label>
            <input type="url" id="website" name="website">
        </fieldset>
        
        <fieldset>
            <legend>Adresse</legend>
            
            <label for="street">Adresse :</label>
            <input type="text" id="street" name="street" required>
            
            <label for="city">Ville :</label>
            <input type="text" id="city" name="city" required>
            
            <label for="zipCode">Code postal :</label>
            <input type="text" id="zipCode" name="zipCode" pattern="[0-9]{5}" required>
            
            <label for="country">Pays :</label>
            <select id="country" name="country" required>
                <option value="">Sélectionnez</option>
                <option value="fr">France</option>
                <option value="be">Belgique</option>
                <option value="ch">Suisse</option>
            </select>
        </fieldset>
        
        <fieldset>
            <legend>Préférences</legend>
            
            <label for="newsletter">
                <input type="checkbox" id="newsletter" name="newsletter" value="yes">
                S'abonner à la newsletter
            </label>
            
            <label for="sms">
                <input type="checkbox" id="sms" name="sms" value="yes">
                Recevoir des SMS promotionnels
            </label>
            
            <fieldset>
                <legend>Fréquence des emails :</legend>
                <label>
                    <input type="radio" name="frequency" value="daily">
                    Quotidien
                </label>
                <label>
                    <input type="radio" name="frequency" value="weekly" checked>
                    Hebdomadaire
                </label>
                <label>
                    <input type="radio" name="frequency" value="monthly">
                    Mensuel
                </label>
            </fieldset>
        </fieldset>
        
        <fieldset>
            <legend>Commentaires</legend>
            
            <label for="comments">Commentaires :</label>
            <textarea id="comments" 
                      name="comments" 
                      rows="4" 
                      cols="50"
                      placeholder="Parlez-nous de vous..."></textarea>
        </fieldset>
        
        <fieldset>
            <legend>Validation</legend>
            
            <label for="terms">
                <input type="checkbox" id="terms" name="terms" required>
                J'accepte les <a href="/terms">conditions d'utilisation</a>
            </label>
            
            <label for="age">
                <input type="checkbox" id="age" name="age" required>
                Je certifie être âgé(e) de plus de 18 ans
            </label>
        </fieldset>
        
        <div>
            <button type="submit">S'inscrire</button>
            <button type="reset">Réinitialiser</button>
        </div>
    </form>
</body>
</html>
```

## ♿ Accessibilité des formulaires

### Bonnes pratiques

```html
<!-- Toujours associer labels et inputs -->
<label for="email">Email :</label>
<input type="email" id="email" name="email" required>

<!-- Ou utiliser label implicite -->
<label>
    Email :
    <input type="email" name="email" required>
</label>

<!-- Grouper les éléments liés -->
<fieldset>
    <legend>Informations de contact</legend>
    <!-- Champs du groupe -->
</fieldset>

<!-- Décrire les champs complexes -->
<label for="password">Mot de passe :</label>
<input type="password" id="password" name="password" aria-describedby="pwd-help">
<div id="pwd-help">Au moins 8 caractères avec majuscules et chiffres</div>

<!-- Indiquer les champs obligatoires -->
<label for="name">Nom <span aria-label="obligatoire">*</span> :</label>
<input type="text" id="name" name="name" required aria-required="true">
```

## ✅ Exercice pratique

1. Créez un formulaire de contact avec :
   - Champs nom, email, téléphone
   - Menu déroulant pour le sujet
   - Zone de texte pour le message
   - Cases à cocher pour les préférences
   - Validation HTML5 appropriée

2. Testez l'accessibilité au clavier

3. Vérifiez que tous les champs sont correctement étiquetés

## 🔍 Bonnes pratiques

- Toujours associer labels et inputs
- Utiliser les types d'input appropriés
- Grouper les éléments avec fieldset/legend
- Valider côté client ET serveur
- Fournir des messages d'erreur clairs
- Tester l'accessibilité au clavier

## 🔗 Ressources supplémentaires

- [MDN - Formulaires HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element/form)
- [WebAIM - Accessibilité des formulaires](https://webaim.org/techniques/forms/)
- [HTML5 Input Types](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input)

---

**Temps estimé :** 3 heures  
**Prochaine étape :** [Module 9 - Projet final](../09-projet-final/)