# README.md — Projet BillXpert : page de téléchargement sans compte

README.md = le fichier à lire tout le temps !!!

README = READ(lire) ME(moi), donc littéralement : **“lisez-moi”**.

Quand tu arrives sur un projet, le README est toujours le premier fichier à lire.
Il sert à comprendre :

* le but du projet ;
* comment installer le projet ;
* comment lancer le serveur ;
* comment est organisée la structure ;
* quels fichiers modifier ;
* quelles étapes suivre ;
* comment éviter de casser le site existant.

---

# 1. Introduction

Ceci est ton premier projet complexe.

Tu devras t’y prendre avec sérieux, avec l’aide de l’IA si besoin.
Le but est que tu apprennes progressivement à :

* gérer une structure de fichiers ;
* ouvrir un projet proprement dans VS Code ;
* lancer un serveur local ;
* comprendre la base du code ;
* utiliser HTML, CSS, JavaScript, PHP et CSV ;
* organiser un projet informatique ;
* créer une vraie fonctionnalité dans un site déjà existant.

Dans quelques mois, tu comprendras pourquoi c’est important.
Quand tu sais organiser un projet, lire du code, créer une page et connecter un frontend à un backend, tu peux commencer à créer presque n’importe quoi avec un ordinateur.

---

# 2. Objectif du projet

Ton premier projet est plus simple qu’il en a l’air.

Tu ne dois pas refaire tout le site BillXpert.

Tu dois :

> installer le site actuel depuis GitHub, comprendre sa structure, puis ajouter une nouvelle page proprement, sans casser le site existant.

La page à créer sera une page de téléchargement de la beta BillXpert **sans connexion**.

Cela veut dire qu’un utilisateur pourra télécharger la beta sans avoir besoin de créer un compte ou de se connecter.

---

# 3. Ce que la page doit faire

La nouvelle page doit contenir un formulaire qui demande :

* nom ;
* prénom ;
* nom de société ;
* raison pour laquelle la personne installe BillXpert.

Sous le formulaire, il doit y avoir un bouton de téléchargement.

Le bouton doit respecter cette logique :

* tant que tous les champs ne sont pas remplis, le bouton est gris ;
* tant que le bouton est gris, il ne doit rien faire au clic ;
* quand tous les champs sont remplis, le bouton devient vert ;
* quand le bouton est vert, l’utilisateur peut cliquer ;
* au clic, les informations sont envoyées au backend ;
* le backend enregistre les informations dans un fichier CSV ;
* ensuite, un lien de téléchargement est ouvert.

Pour l’instant, le lien de téléchargement peut être vide ou temporaire, car la beta BillXpert n’est pas encore mise en ligne.

---

# 4. Télécharger le projet depuis GitHub

Va sur ce lien :

```txt
https://github.com/iluwailuwa1-cmd/billxpert-web.git
```

Ensuite :

1. clique sur le bouton vert **Code** ;
2. clique sur **Download ZIP** ;
3. télécharge le fichier ZIP ;
4. décompresse le ZIP sur ton bureau ;
5. vérifie que tu as bien un dossier appelé:

```txt
billxpert_web
```

---

# 5. Lancer le serveur local

Va dans le dossier du projet avec l’explorateur Windows.

Dans la barre du chemin, pas la barre de recherche, tu dois voir quelque chose comme :

```txt
Bureau > billxpert_web
```

Clique dans cette barre, efface le texte, puis tape :

```txt
powershell
```

Ensuite, appuie sur Entrée.

Une fenêtre PowerShell va s’ouvrir directement dans le dossier du projet.

Tu peux ensuite lancer le serveur avec cette commande :

```powershell
php -S 127.0.0.1:8000 router.php
```

Une fois la commande lancée, PowerShell affichera une adresse du type :

```txt
http://127.0.0.1:8000
```

Tu dois copier cette adresse et la coller dans ton navigateur.

Important :

> Ne fais pas `Ctrl + C` dans PowerShell sans avoir selectionner de texte pendant que le serveur tourne, car cela arrête le serveur.

Si tout fonctionne, tu seras sur le site BillXpert en local.

---

# 6. Ouvrir le projet dans VS Code

Une fois le site lancé, ouvre VS Code.

Dans VS Code :

1. clique sur **File** ;
2. clique sur **Open Folder** ;
3. sélectionne le dossier complet du projet ;
4. ouvre le dossier `billxpert_web` 

Très important :

> Tu ne dois pas ouvrir seulement un fichier HTML.
> Tu dois ouvrir le dossier complet du projet.

Un site web fonctionne avec plusieurs fichiers liés entre eux :

* HTML ;
* CSS ;
* JavaScript ;
* PHP ;
* images ;
* partials ;
* router ;
* backend.

Si tu n’ouvres qu’un seul fichier, tu ne verras pas toute l’organisation.

---

# 7. Analyser la structure du projet

Avant de coder, tu dois comprendre la structure.

Le projet est organisé comme ceci :

```txt
billxpert-web/
├── router.php
├── index.html
├── assets/
│   ├── css/
│   │   ├── global.css
│   │   ├── connexion.css
│   │   ├── inscription.css
│   │   ├── acceuil.css
│   │   ├── acceuil-client.css
│   │   └── ...
│   ├── js/
│   │   ├── global.js
│   │   ├── connexion.js
│   │   ├── inscription.js
│   │   ├── acceuil.js
│   │   ├── acceuil-client.js
│   │   └── ...
│   └── img/
│       ├── logo-bx.png
│       └── logo-bx-light.png
├── pages/
│   ├── connexion.html
│   ├── inscription.html
│   ├── acceuil.html
│   ├── produit.html
│   ├── tarifs.html
│   ├── reforme-2026.html
│   ├── forgot-password.html
│   ├── reset-password.html
│   ├── 404.html
│   ├── 500.html
│   └── session/
│       ├── acceuil-client.php
│       └── help.php
└── partials/
    ├── header.php
    └── footer.html
```

Tu peux aussi afficher la structure dans PowerShell avec :

```powershell
tree /F
```

Cette commande affiche les dossiers et les fichiers.

---

# 8. Comprendre le rôle des fichiers et dossiers

## `router.php`

Ce fichier sert à lancer correctement le site avec le serveur PHP local.

La commande :

```powershell
php -S 127.0.0.1:8000 router.php
```

utilise ce fichier pour gérer les routes du site.

Tu ne dois pas le modifier au début.

---

## `index.html`

C’est souvent la page principale du site.

Elle peut rediriger ou représenter la page d’accueil.

Tu peux la lire pour comprendre comment le site démarre, mais tu ne dois pas la modifier pour ce projet.

---

## `assets/css/`

Ce dossier contient les fichiers CSS.

Le CSS sert à gérer le design :

* couleurs ;
* tailles ;
* marges ;
* boutons ;
* formulaires ;
* responsive ;
* style global du site.

Le fichier le plus important est :

```txt
assets/css/global.css
```

Il contient la base commune du site.

Tu dois réutiliser ce fichier au maximum pour éviter de tout recoder à la main.

---

## `assets/js/`

Ce dossier contient les fichiers JavaScript.

Le JavaScript sert à gérer les interactions :

* clics ;
* menus ;
* formulaires ;
* vérification des champs ;
* envoi des données au backend.

Le fichier global est :

```txt
assets/js/global.js
```

Tu ne dois pas le modifier au hasard.
Pour ta page, tu créeras ton propre fichier JavaScript.

---

## `assets/img/`

Ce dossier contient les images du site.

Exemples :

```txt
logo-bx.png
logo-bx-light.png
```

Tu peux utiliser ces logos sur ta nouvelle page pour rester cohérent avec le style BillXpert.

---

## `pages/`

Ce dossier contient les pages du site.

Exemples :

```txt
connexion.html
inscription.html
produit.html
tarifs.html
```

C’est dans ce dossier que tu vas créer ta nouvelle page HTML.

---

## `pages/session/`

Ce dossier contient les pages liées au compte utilisateur.

Exemple :

```txt
pages/session/acceuil-client.php
```

Ces pages peuvent être réservées aux personnes connectées.

Pour ton projet, la page de téléchargement doit être accessible **sans compte**, donc tu ne dois pas la mettre dans `pages/session/`.

---

## `partials/`

Ce dossier contient des morceaux de page réutilisables.

Exemples :

```txt
partials/header.php
partials/footer.html
```

Le header correspond au haut du site.
Le footer correspond au bas du site.

Tu devras modifier le header pour ajouter un lien vers ta nouvelle page.

---

# 9. Fichiers concernés par les modifications

Les dossiers principalement concernés seront :

```txt
pages/
assets/css/
assets/js/
partials/
```

Tu devras aussi créer un nouveau dossier à la racine :

```txt
backend/
```

Dans ce dossier, tu créeras :

```txt
backend/
├── stockage.csv
└── stockage.php
```

Le fichier `stockage.php` contiendra le code backend.

Le fichier `stockage.csv` ne contiendra pas de code.
Il servira uniquement à stocker les informations reçues depuis le formulaire.

Si ton PHP est bien codé, le fichier CSV pourra être rempli automatiquement pendant les tests.

---

# 10. Créer les nouveaux fichiers

Après avoir analysé la structure, tu dois créer une nouvelle page dans le dossier `pages/`.

Tu peux choisir un nom simple, par exemple :

```txt
pages/ezdownload.html
```

Explication du nom :

* `ez` = easy = facile ;
* `download` = téléchargement.

Donc `ezdownload` veut dire : téléchargement simple.

Ensuite, tu dois créer un fichier CSS du même nom :

```txt
assets/css/ezdownload.css
```

Et un fichier JavaScript du même nom :

```txt
assets/js/ezdownload.js
```

La logique est simple :

```txt
ezdownload.html  = structure de la page
ezdownload.css   = style de la page
ezdownload.js    = comportement de la page
```

---

# 11. Comprendre les extensions de fichiers

Une extension, ce sont les lettres après le point dans un nom de fichier.

Exemples :

```txt
.html  = fichier HTML
.css   = fichier CSS
.js    = fichier JavaScript
.php   = fichier PHP
.csv   = fichier CSV
.md    = fichier Markdown
.txt   = fichier texte simple
```

Dans ce projet :

* `.html` sert à créer la page ;
* `.css` sert à styliser la page ;
* `.js` sert à rendre la page interactive ;
* `.php` sert au backend ;
* `.csv` sert à stocker les données ;
* `.md` sert à écrire de la documentation comme ce README.

---

# 12. Les langages à connaître

Tu n’as pas besoin de connaître les langages par cœur.

C’est impossible et inutile.

Tu dois simplement connaître :

* les bases ;
* les structures importantes ;
* les commandes utiles ;
* la logique générale ;
* comment demander de l’aide à l’IA ;
* comment lire et modifier du code existant.

Les langages utiles pour ce projet sont :

## HTML

Le HTML sert à construire la structure de la page.

Exemples :

* titres ;
* paragraphes ;
* formulaires ;
* boutons ;
* liens ;
* sections.

Le HTML répond à la question :

> Qu’est-ce qu’il y a sur la page ?

---

## CSS

Le CSS sert à gérer le style visuel.

Exemples :

* couleurs ;
* tailles ;
* espacements ;
* boutons ;
* formulaires ;
* responsive ;
* alignement.

Le CSS répond à la question :

> À quoi ressemble la page ?

---

## JavaScript

JavaScript sert à rendre la page interactive.

Dans ce projet, il servira à :

* vérifier si tous les champs sont remplis ;
* rendre le bouton vert quand le formulaire est prêt ;
* empêcher le clic si le formulaire est incomplet ;
* envoyer les données au backend PHP ;
* ouvrir le lien de téléchargement.

JavaScript répond à la question :

> Que se passe-t-il quand l’utilisateur agit ?

---

## PHP

PHP sert au backend.

Dans ce projet, il servira à :

* recevoir les données du formulaire ;
* vérifier les informations ;
* récupérer la date et l’heure ;
* écrire une ligne dans le fichier CSV ;
* renvoyer une réponse au JavaScript.

PHP répond à la question :

> Que fait le serveur avec les données ?

---

## CSV

CSV est un format simple de tableau.

Exemple :

```csv
date,heure,nom,prenom,societe,raison
2026-07-02,15:30,Dupont,Jean,Entreprise Test,Tester BillXpert
```

Dans ce projet, le fichier CSV servira à stocker les informations des personnes qui ont cliqué sur le bouton de téléchargement.

---

# 13. Apprendre avec ChatGPT

Tu peux utiliser ChatGPT pour apprendre, mais tu dois lui demander des choses précises.

Tu peux lui envoyer ce README complet et lui dire :

```txt
Voici mon projet. Aide-moi étape par étape à apprendre les bases nécessaires et à construire la page.
```

Exemples de bonnes demandes :

```txt
Explique-moi la structure HTML d’un formulaire.
```

```txt
Fais-moi un exercice simple en HTML lié à mon projet.
```

```txt
Explique-moi comment connecter un fichier CSS à une page HTML.
```

```txt
Fais-moi un exercice JavaScript pour activer un bouton seulement quand tous les champs sont remplis.
```

```txt
Explique-moi comment envoyer un formulaire en JavaScript vers un fichier PHP.
```

```txt
Explique-moi comment écrire dans un fichier CSV avec PHP.
```

```txt
Corrige mon code et explique-moi mes erreurs.
```

Tu dois apprendre en construisant la page.

L’objectif n’est pas d’apprendre toute la théorie avant de coder.
L’objectif est de pratiquer directement avec un vrai mini-projet.

---

# 14. Ordre de travail obligatoire

Tu dois suivre cet ordre :

1. télécharger le ZIP depuis GitHub ;
2. décompresser le projet sur le bureau ;
3. lancer le serveur local ;
4. ouvrir le site dans le navigateur ;
5. ouvrir le dossier complet dans VS Code ;
6. analyser la structure ;
7. comprendre `global.css`, `connexion.css`, `global.js` et `header.php` ;
8. créer `pages/ezdownload.html` ;
9. créer `assets/css/ezdownload.css` ;
10. créer `assets/js/ezdownload.js` ;
11. modifier le header pour ajouter le lien ;
12. coder le frontend ;
13. tester le frontend ;
14. créer `backend/stockage.php` ;
15. créer ou laisser créer `backend/stockage.csv` ;
16. connecter le frontend au backend ;
17. tester l’enregistrement CSV ;
18. tester le clic final ;
19. nettoyer le code ;
20. vérifier que le site existant fonctionne toujours.

---

# 15. Modifier le header

Tu dois ajouter un lien vers ta nouvelle page dans :

```txt
partials/header.php
```

Dans la section “Compte”, ajoute un lien nommé :

```txt
Télécharger sans compte
```

Ce lien doit pointer vers ta nouvelle page.

Exemple :

```html
<a href="/pages/ezdownload.html">Télécharger sans compte</a>
```

Attention : selon le fonctionnement du routeur, le chemin peut être différent.

Tu dois tester dans le navigateur.

Le but est qu’un visiteur puisse accéder à la page de téléchargement depuis le site actuel.

---

# 16. Construire d’abord le frontend

Très important :

> Tu dois d’abord coder le frontend.

Ne commence pas par PHP.

Le frontend, c’est ce que l’utilisateur voit dans le navigateur.

Ta page doit être dans le même style que BillXpert.

Elle doit utiliser :

```html
<link rel="stylesheet" href="/assets/css/global.css">
<link rel="stylesheet" href="/assets/css/ezdownload.css">
```

Et à la fin de la page :

```html
<script src="/assets/js/global.js"></script>
<script src="/assets/js/ezdownload.js"></script>
```

Tu dois t’inspirer de :

```txt
pages/connexion.html
assets/css/connexion.css
```

Mais tu ne dois pas casser la page de connexion.

Lis ces fichiers, comprends leur logique, puis crée ta propre page.

---

# 17. Contenu attendu sur la page

La page doit contenir :

* le header du site ;
* un titre clair ;
* un texte court qui explique le téléchargement sans compte ;
* un formulaire ;
* un bouton ;
* le footer du site.

Exemple de texte :

```txt
Télécharger BillXpert sans compte
```

```txt
Remplissez ce court formulaire pour accéder à la beta de BillXpert. Ces informations nous permettent de mieux comprendre qui teste le logiciel et pourquoi.
```

Formulaire attendu :

```txt
Nom
Prénom
Nom de société
Pourquoi installez-vous BillXpert ?
```

Bouton attendu :

```txt
Télécharger
```

---

# 18. Comportement attendu du bouton

Le bouton doit avoir deux états.

## État 1 — Formulaire incomplet

Si un champ est vide :

* le bouton est gris ;
* le bouton paraît désactivé ;
* le bouton ne doit pas envoyer le formulaire ;
* le bouton ne doit pas ouvrir le lien de téléchargement.

## État 2 — Formulaire complet

Si tous les champs sont remplis :

* le bouton devient vert ;
* le bouton devient cliquable ;
* au clic, JavaScript envoie les données au backend ;
* le backend écrit dans le CSV ;
* ensuite, le lien de téléchargement s’ouvre.

---

# 19. Créer ensuite le backend

Une fois que le frontend est prêt, tu peux créer le backend.

Crée un dossier à la racine :

```txt
backend/
```

Puis crée :

```txt
backend/stockage.php
```

Ce fichier doit recevoir les données envoyées par JavaScript.

Il doit enregistrer dans :

```txt
backend/stockage.csv
```

Le CSV doit contenir :

* date du clic ;
* heure du clic ;
* nom ;
* prénom ;
* nom de société ;
* raison de l’installation.

Exemple de colonnes :

```csv
date,heure,nom,prenom,societe,raison
```

Exemple de ligne :

```csv
2026-07-02,15:42:10,Dupont,Jean,Entreprise Test,Je veux tester la beta
```

---

# 20. Logique complète frontend/backend

Le fonctionnement complet doit être :

```txt
Utilisateur remplit le formulaire
→ JavaScript vérifie que tout est rempli
→ Le bouton devient vert
→ Utilisateur clique sur le bouton
→ JavaScript envoie les données à backend/stockage.php
→ PHP reçoit les données
→ PHP ajoute la date et l’heure
→ PHP écrit une ligne dans backend/stockage.csv
→ PHP répond au JavaScript
→ JavaScript ouvre le lien de téléchargement
```

---

# 21. Exemple de logique JavaScript

Le JavaScript doit suivre cette idée :

```js
const form = document.querySelector("#downloadForm");
const button = document.querySelector("#downloadButton");

function checkForm() {
  const isValid = form.checkValidity();

  if (isValid) {
    button.disabled = false;
    button.classList.add("is-ready");
  } else {
    button.disabled = true;
    button.classList.remove("is-ready");
  }
}

form.addEventListener("input", checkForm);

form.addEventListener("submit", async function (event) {
  event.preventDefault();

  if (!form.checkValidity()) {
    return;
  }

  const formData = new FormData(form);

  const response = await fetch("/backend/stockage.php", {
    method: "POST",
    body: formData
  });

  const result = await response.json();

  if (result.success) {
    window.open("#", "_blank");
  } else {
    alert("Erreur : les informations n’ont pas été enregistrées.");
  }
});

checkForm();
```

Ici, `window.open("#", "_blank")` est temporaire.

Plus tard, `#` sera remplacé par le vrai lien de téléchargement.

---

# 22. Exemple de logique PHP

Le fichier :

```txt
backend/stockage.php
```

doit suivre cette logique :

```php
<?php

header('Content-Type: application/json');

if ($_SERVER['REQUEST_METHOD'] !== 'POST') {
    echo json_encode([
        'success' => false,
        'message' => 'Méthode non autorisée.'
    ]);
    exit;
}

$nom = trim($_POST['nom'] ?? '');
$prenom = trim($_POST['prenom'] ?? '');
$societe = trim($_POST['societe'] ?? '');
$raison = trim($_POST['raison'] ?? '');

if ($nom === '' || $prenom === '' || $societe === '' || $raison === '') {
    echo json_encode([
        'success' => false,
        'message' => 'Tous les champs sont obligatoires.'
    ]);
    exit;
}

$csvPath = __DIR__ . '/stockage.csv';
$isNewFile = !file_exists($csvPath);

$file = fopen($csvPath, 'a');

if ($file === false) {
    echo json_encode([
        'success' => false,
        'message' => 'Impossible d’ouvrir le fichier CSV.'
    ]);
    exit;
}

if ($isNewFile) {
    fputcsv($file, ['date', 'heure', 'nom', 'prenom', 'societe', 'raison']);
}

fputcsv($file, [
    date('Y-m-d'),
    date('H:i:s'),
    $nom,
    $prenom,
    $societe,
    $raison
]);

fclose($file);

echo json_encode([
    'success' => true,
    'message' => 'Informations enregistrées.'
]);
```

Ce code est une base simple.

Tu dois comprendre chaque ligne avant de l’utiliser.

---

# 23. Tests à faire

Tu dois tester plusieurs cas.

## Test 1 — Formulaire vide

Ouvre la page :

```txt
http://127.0.0.1:8000/pages/ezdownload.html
```

Ne remplis rien.

Résultat attendu :

* le bouton reste gris ;
* le bouton ne fonctionne pas.

---

## Test 2 — Formulaire complet

Remplis tous les champs.

Résultat attendu :

* le bouton devient vert ;
* le clic envoie les données ;
* le fichier `backend/stockage.csv` est créé ou mis à jour ;
* une ligne est ajoutée.

---

## Test 3 — Plusieurs essais

Remplis le formulaire plusieurs fois.

Résultat attendu :

* chaque clic ajoute une nouvelle ligne dans le CSV ;
* les anciennes lignes ne sont pas supprimées.

---

## Test 4 — Console navigateur

Ouvre les outils développeur avec :

```txt
F12
```

Va dans l’onglet :

```txt
Console
```

Il ne doit pas y avoir d’erreurs rouges.

Va aussi dans :

```txt
Network
```

Tu dois voir la requête vers :

```txt
/backend/stockage.php
```

---

# 24. Ce qu’il faut éviter

Ne modifie pas tout le site.

Ne renomme pas les fichiers existants.

Ne supprime pas les fichiers existants.

Ne modifie pas `router.php` au début.

Ne casse pas la page de connexion.

Ne mets pas le backend dans le dossier `pages`.

Ne mets pas le CSS dans le dossier `js`.

Ne mets pas le JavaScript dans le dossier `css`.

Ne stocke pas de mots de passe dans le CSV.

Ne commence pas par PHP avant d’avoir fait le frontend.

---

# 25. Préparation à l’examen

Le jour de l’examen, tu auras environ 2 heures.

Ton environnement sera déjà prêt.

Tu n’auras normalement pas besoin de :

* créer tout le projet ;
* préparer le serveur ;
* installer PHP ;
* organiser tous les dossiers ;
* chercher longtemps la structure.

Tu devras surtout refaire une page similaire avec :

* un fichier HTML ;
* un fichier CSS ;
* un fichier JavaScript ;
* un backend PHP simple ;
* un fichier CSV qui stocke les informations.

Le backend devra seulement enregistrer les mêmes types d’informations que pour le site BillXpert.

Normalement, un exercice comme celui-ci peut se faire en 45 minutes à 1 heure si tu t’es bien entraîné.

Le but de l’examen n’est pas de faire un site parfait.
Le but est de prouver que tu sais :

* comprendre une structure ;
* créer une page propre ;
* styliser avec CSS ;
* gérer un formulaire en JavaScript ;
* envoyer des données à PHP ;
* enregistrer dans un CSV ;
* tester ton travail.

---

# 26. Résumé final

Tu dois faire une page de téléchargement sans compte dans le site BillXpert.

Tu dois créer :

```txt
pages/ezdownload.html
assets/css/ezdownload.css
assets/js/ezdownload.js
backend/stockage.php
backend/stockage.csv
```

Tu dois modifier :

```txt
partials/header.php
```

uniquement pour ajouter un lien vers ta page.

Tu dois respecter cet ordre :

```txt
Télécharger le projet
→ Lancer le serveur
→ Ouvrir dans VS Code
→ Comprendre la structure
→ Créer la page HTML
→ Créer le CSS
→ Créer le JavaScript
→ Tester le frontend
→ Créer le PHP
→ Connecter le backend
→ Vérifier le CSV
→ Nettoyer le code
```

Le plus important est de comprendre ce que tu fais.

Un bon développeur ne code pas au hasard.
Il lit, il observe, il comprend, il organise, puis il construit.
