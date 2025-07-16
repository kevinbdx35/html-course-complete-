# Module 7 : Listes et tableaux

## 🎯 Objectifs du module

- Créer différents types de listes
- Construire des tableaux structurés et accessibles
- Comprendre l'utilisation appropriée de chaque élément
- Maîtriser les bonnes pratiques d'accessibilité

## 📋 Les listes

### Liste non ordonnée `<ul>`

```html
<ul>
    <li>Premier élément</li>
    <li>Deuxième élément</li>
    <li>Troisième élément</li>
</ul>
```

### Liste ordonnée `<ol>`

```html
<ol>
    <li>Étape 1</li>
    <li>Étape 2</li>
    <li>Étape 3</li>
</ol>
```

### Attributs des listes ordonnées

```html
<!-- Commencer à un numéro spécifique -->
<ol start="5">
    <li>Cinquième élément</li>
    <li>Sixième élément</li>
</ol>

<!-- Ordre inversé -->
<ol reversed>
    <li>Dernier élément</li>
    <li>Avant-dernier élément</li>
</ol>

<!-- Type de numérotation -->
<ol type="a">
    <li>Premier (a)</li>
    <li>Deuxième (b)</li>
</ol>

<ol type="i">
    <li>Premier (i)</li>
    <li>Deuxième (ii)</li>
</ol>
```

### Liste de définitions `<dl>`

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language - Langage de balisage pour créer des pages web</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets - Langage de style pour la présentation</dd>
    
    <dt>JavaScript</dt>
    <dd>Langage de programmation pour l'interactivité web</dd>
    <dd>Peut être utilisé côté client et serveur</dd>
</dl>
```

### Listes imbriquées

```html
<ul>
    <li>Développement web
        <ul>
            <li>Frontend
                <ul>
                    <li>HTML</li>
                    <li>CSS</li>
                    <li>JavaScript</li>
                </ul>
            </li>
            <li>Backend
                <ul>
                    <li>Node.js</li>
                    <li>Python</li>
                    <li>PHP</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>Design
        <ul>
            <li>UI/UX</li>
            <li>Graphisme</li>
        </ul>
    </li>
</ul>
```

## 📊 Les tableaux

### Structure de base

```html
<table>
    <thead>
        <tr>
            <th>Nom</th>
            <th>Âge</th>
            <th>Ville</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Jean</td>
            <td>25</td>
            <td>Paris</td>
        </tr>
        <tr>
            <td>Marie</td>
            <td>30</td>
            <td>Lyon</td>
        </tr>
    </tbody>
</table>
```

### Tableau complet avec toutes les sections

```html
<table>
    <caption>Résultats des ventes par trimestre</caption>
    <thead>
        <tr>
            <th scope="col">Produit</th>
            <th scope="col">Q1 2024</th>
            <th scope="col">Q2 2024</th>
            <th scope="col">Q3 2024</th>
            <th scope="col">Total</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Ordinateurs</th>
            <td>150</td>
            <td>200</td>
            <td>180</td>
            <td>530</td>
        </tr>
        <tr>
            <th scope="row">Téléphones</th>
            <td>300</td>
            <td>350</td>
            <td>400</td>
            <td>1050</td>
        </tr>
        <tr>
            <th scope="row">Tablettes</th>
            <td>100</td>
            <td>120</td>
            <td>90</td>
            <td>310</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th scope="row">Total</th>
            <td>550</td>
            <td>670</td>
            <td>670</td>
            <td>1890</td>
        </tr>
    </tfoot>
</table>
```

### Fusion de cellules

```html
<table>
    <thead>
        <tr>
            <th>Nom</th>
            <th colspan="2">Contact</th>
            <th>Statut</th>
        </tr>
        <tr>
            <th></th>
            <th>Email</th>
            <th>Téléphone</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">Jean Dupont</td>
            <td>jean@example.com</td>
            <td>01 23 45 67 89</td>
            <td>Actif</td>
        </tr>
        <tr>
            <td>jean.pro@example.com</td>
            <td>01 98 76 54 32</td>
            <td>Inactif</td>
        </tr>
    </tbody>
</table>
```

## 🎨 Exemples pratiques

### Navigation sous forme de liste

```html
<nav>
    <ul>
        <li><a href="/">Accueil</a></li>
        <li><a href="/products">Produits</a>
            <ul>
                <li><a href="/products/laptops">Ordinateurs portables</a></li>
                <li><a href="/products/desktops">Ordinateurs de bureau</a></li>
                <li><a href="/products/tablets">Tablettes</a></li>
            </ul>
        </li>
        <li><a href="/support">Support</a></li>
        <li><a href="/contact">Contact</a></li>
    </ul>
</nav>
```

### FAQ avec liste de définitions

```html
<section>
    <h2>Questions fréquentes</h2>
    <dl>
        <dt>Comment créer un compte ?</dt>
        <dd>Cliquez sur "S'inscrire" en haut à droite de la page et remplissez le formulaire.</dd>
        
        <dt>Puis-je modifier ma commande ?</dt>
        <dd>Oui, vous pouvez modifier votre commande dans les 24 heures suivant sa validation.</dd>
        
        <dt>Quels sont les moyens de paiement acceptés ?</dt>
        <dd>Nous acceptons les cartes bancaires, PayPal et les virements SEPA.</dd>
    </dl>
</section>
```

### Tableau de prix

```html
<table>
    <caption>Tarifs d'abonnement</caption>
    <thead>
        <tr>
            <th scope="col">Fonctionnalité</th>
            <th scope="col">Basic</th>
            <th scope="col">Pro</th>
            <th scope="col">Enterprise</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Stockage</th>
            <td>10 GB</td>
            <td>100 GB</td>
            <td>1 TB</td>
        </tr>
        <tr>
            <th scope="row">Utilisateurs</th>
            <td>1</td>
            <td>5</td>
            <td>Illimité</td>
        </tr>
        <tr>
            <th scope="row">Support</th>
            <td>Email</td>
            <td>Email + Chat</td>
            <td>24/7 Phone</td>
        </tr>
        <tr>
            <th scope="row">Prix/mois</th>
            <td>9€</td>
            <td>29€</td>
            <td>99€</td>
        </tr>
    </tbody>
</table>
```

## ♿ Accessibilité

### Listes accessibles

```html
<!-- Utiliser les listes pour la navigation -->
<nav aria-label="Navigation principale">
    <ul>
        <li><a href="/" aria-current="page">Accueil</a></li>
        <li><a href="/about">À propos</a></li>
    </ul>
</nav>

<!-- Grouper les listes reliées -->
<div role="group" aria-labelledby="skills-heading">
    <h3 id="skills-heading">Compétences techniques</h3>
    <ul>
        <li>HTML/CSS</li>
        <li>JavaScript</li>
        <li>React</li>
    </ul>
</div>
```

### Tableaux accessibles

```html
<table role="table" aria-label="Données de vente">
    <caption>Ventes par mois (en milliers d'euros)</caption>
    <thead>
        <tr>
            <th scope="col" id="month">Mois</th>
            <th scope="col" id="sales">Ventes</th>
            <th scope="col" id="growth">Croissance</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row" headers="month">Janvier</th>
            <td headers="sales month">150</td>
            <td headers="growth month">+5%</td>
        </tr>
        <tr>
            <th scope="row" headers="month">Février</th>
            <td headers="sales month">180</td>
            <td headers="growth month">+20%</td>
        </tr>
    </tbody>
</table>
```

## 📱 Tableaux responsive

```html
<div class="table-container">
    <table>
        <thead>
            <tr>
                <th>Produit</th>
                <th>Prix</th>
                <th>Stock</th>
                <th>Actions</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td data-label="Produit">iPhone 15</td>
                <td data-label="Prix">999€</td>
                <td data-label="Stock">En stock</td>
                <td data-label="Actions">
                    <button>Modifier</button>
                    <button>Supprimer</button>
                </td>
            </tr>
        </tbody>
    </table>
</div>
```

## 💻 Exemple complet

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Listes et tableaux - Exemple</title>
</head>
<body>
    <header>
        <h1>Catalogue de produits</h1>
        <nav>
            <ul>
                <li><a href="#categories">Catégories</a></li>
                <li><a href="#products">Produits</a></li>
                <li><a href="#specs">Spécifications</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="categories">
            <h2>Catégories de produits</h2>
            <ul>
                <li>Informatique
                    <ul>
                        <li>Ordinateurs portables</li>
                        <li>Ordinateurs de bureau</li>
                        <li>Accessoires</li>
                    </ul>
                </li>
                <li>Téléphonie
                    <ul>
                        <li>Smartphones</li>
                        <li>Tablettes</li>
                        <li>Accessoires</li>
                    </ul>
                </li>
            </ul>
        </section>

        <section id="products">
            <h2>Liste des produits</h2>
            <table>
                <caption>Inventaire des produits en stock</caption>
                <thead>
                    <tr>
                        <th scope="col">Nom</th>
                        <th scope="col">Catégorie</th>
                        <th scope="col">Prix</th>
                        <th scope="col">Stock</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <th scope="row">MacBook Air</th>
                        <td>Ordinateur portable</td>
                        <td>1199€</td>
                        <td>15</td>
                    </tr>
                    <tr>
                        <th scope="row">iPhone 15</th>
                        <td>Smartphone</td>
                        <td>999€</td>
                        <td>25</td>
                    </tr>
                    <tr>
                        <th scope="row">iPad Pro</th>
                        <td>Tablette</td>
                        <td>899€</td>
                        <td>8</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <section id="specs">
            <h2>Spécifications techniques</h2>
            <dl>
                <dt>MacBook Air</dt>
                <dd>Processeur Apple M2</dd>
                <dd>8 GB de RAM</dd>
                <dd>256 GB SSD</dd>
                
                <dt>iPhone 15</dt>
                <dd>Processeur A17 Bionic</dd>
                <dd>6 GB de RAM</dd>
                <dd>128 GB de stockage</dd>
            </dl>
        </section>
    </main>
</body>
</html>
```

## ✅ Exercice pratique

1. Créez une page restaurant avec :
   - Menu sous forme de liste imbriquée
   - Tableau des horaires d'ouverture
   - Liste de définitions pour les allergènes
   - Tableau de prix avec fusion de cellules

2. Assurez-vous que tous les tableaux sont accessibles

3. Testez la navigation au clavier

## 🔍 Bonnes pratiques

- Utiliser `<ul>` pour les listes non ordonnées
- Utiliser `<ol>` pour les séquences d'étapes
- Utiliser `<dl>` pour les définitions et FAQ
- Ajouter `<caption>` aux tableaux
- Utiliser `scope` et `headers` pour l'accessibilité
- Éviter les tableaux pour la mise en page

## 🔗 Ressources supplémentaires

- [MDN - Listes HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element/ul)
- [MDN - Tableaux HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element/table)
- [WebAIM - Accessibilité des tableaux](https://webaim.org/techniques/tables/)

---

**Temps estimé :** 2 heures  
**Prochaine étape :** [Module 8 - Formulaires](../08-formulaires/)