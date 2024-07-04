[![GitHub followers](https://img.shields.io/github/followers/AlchTech?label=Follow&style=for-the-badge)](https://github.com/AlchTech) 
![GitHub stars](https://img.shields.io/github/stars/AlchTech?style=for-the-badge)
[![Email](https://img.shields.io/badge/Email-harmonyfidelis@gmail.com-red?style=for-the-badge&logo=gmail&logoColor=white)](mailto:votreadresse@email.com)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/j%C3%A9r%C3%A9my-saletteswozniak/)
[![Patreon](https://img.shields.io/badge/Patreon-Support-orange?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/votreprofil)


# &#127760; HTML
HTML est un langage de balisage utilisé pour structurer le contenu d'une page web. Il permet de définir différents éléments tels que les titres, les paragraphes, les liens, les images, les tableaux, etc. HTML est un langage interprété par les navigateurs web, qui lisent les balises et affichent le contenu de manière appropriée.

## Table des Matières

- [Architecture d'un projet](#)
- [HEAD](#)

### Architecture d'un projet
```
App
 |- public                          // Visible par le client
 |    |- index.html                 // Fichier d'entrer par le client (Page d'accueil)
 |    |- apple-touch-icon.png       // Icone
 |    |- favicon.ico                // Icone
 |    |- favicon.svg                // Icone
 |    |- manifest.json              // Information concernant le site
 |    |- sitemap.xml                // Carte de l'architecture du site
 | 
 |- src                             // Contient les fichiers anexes non visible par le client
 |    |- Assets                     // Contient le contenue media de la page
 |          |- styles
 |               |- style.css       // Feuille de style
 |          |- images
 |               |- image.jpg       // Image
 |          |- scripts
 |               |- script.js       // Fichier javaScript
 |    |- views
 |          |- Other.html           // Autres pages HTML
 |    |- Components
 |          |- Composant1.html      // Code ayant une fonction particuliere
 |    |- index.js                        // Fichier receptionnant tout les scripts.js
 | 
 |- node_modules
 |- .env
 |- .gitignore                      // Ignore l'envoi de fichier lourd(node_modules)ou sensible(.env) au repo
 |- package.json                    // Dépendance et information relative au projet
 |- yarn.lock                       // Dépendance et information relative au projet
```
### BASE 
```code
<!doctype html>
<head>
  <!-- Contenu du HEAD -->
</head>
<body>
  <!-- Contenu du BODY -->
</body>
```

### HEAD
En HTML, le <head> est une balise utilisée pour contenir des éléments qui définissent les métadonnées du document HTML. Ces métadonnées incluent des informations telles que le titre de la page (<title>), les liens vers des feuilles de style (<link>), des scripts JavaScript (<script>), des instructions pour les moteurs de recherche (<meta>), et d'autres données qui ne sont pas directement affichées sur la page web elle-même mais qui sont importantes pour son fonctionnement et son référencement.

#### META DE BASE
Métadonnées de base
```code
<!-- BASE - Titre, Description, Langue -->
<meta name="language" content="fr" />
<title>Titre de votre site</title>
<meta name="description" content="description de votre site en 160caracteres max">

<link rel="icon" href="/favicon.ico">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
```

#### CARACTERES
Permet l'utilisation de caractères spéciaux tels que les parenthèses, les accents, les symboles monétaires et les caractères de ponctuation.
```code
<meta charset="utf-8">
```

#### MOBILE
Assure un rendu responsive en ajustant la taille de la page à la largeur de l'appareil, tandis que manifest permet de configurer une Progressive Web App (PWA) avec des métadonnées essentielles.
```code
<meta name="viewport" content="width=device-width, initial-scale=1">

<link rel="manifest" href="manifest.json">

Exemple d'un manifest.json :
{
  "name": "Mon Application",                      // Nom de l'application
  "short_name": "App",                            // Nom court de l'application
  "description": "Description de l'application",  // Description de l'application
  "start_url": "/index.html",                     // URL de démarrage
  "display": "standalone",                        // Mode d'affichage (standalone, fullscreen, minimal-ui, browser)
  "background_color": "#ffffff",                  // Couleur de fond de l'application
  "theme_color": "#4285f4",                       // Couleur du thème de l'application
  "icons": [
    {
      "src": "/images/icons/icon-192x192.png",    // Chemin de l'icône principale
      "sizes": "192x192",                         // Taille de l'icône
      "type": "image/png"                         // Type MIME de l'image
    },
    {
      "src": "/images/icons/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ],
  "serviceworker": {
    "src": "/sw.js",                              // Chemin vers le service worker
    "scope": "/",                                 // Portée du service worker
    "update_via_cache": "none"                    // Méthode de mise à jour du service worker
  }
}

```

#### COPYRIGHT ET AUTEURS
Permet de définir les droits d'auteur et l'auteur.
```code
<meta name="copyright" content="Copyright 2024, Jérémy Salettes-Wozniak">
<meta name="author" content="Jérémy Salettes-Wozniak">
<meta name="author" content="Jérémy Salettes-Wozniak, Other Name">
```

#### SEO ET ROBOT
```
<!-- SEO - Page d'origine, Architecture  -->
<link rel="canonical" href="https://www.harmonyfidelis.com/" />
<link rel="sitemap" href="sitemap.xml" type="application/xml" />

<!-- ROBOT -->
<meta name="robots" content="index">      <!-- Permet l'indexation de la page -->
<meta name="robots" content="noindex">    <!-- Empêche l'indexation de la page -->
<meta name="robots" content="follow">     <!-- Autorise le suivi des liens -->
<meta name="robots" content="nofollow">   <!-- Empêche le suivi des liens -->
<meta name="robots" content="noarchive">  <!-- Empêche la mise en cache de la page -->
<meta name="robots" content="nosnippet">  <!-- Empêche l'affichage d'un extrait de la page
```
#### PERFORMANCE
```
<meta http-equiv="x-dns-prefetch-control" content="on">     <!-- Activer le prefetch DNS -->
<meta http-equiv="x-dns-prefetch-control" content="off">    <!-- Désactiver le prefetch DNS -->

<link rel="prerender" href="https://example.com">    <!-- Prérendu de la page -->

<link rel="preload" href="styles.css" as="style">    <!-- Préchargement CSS -->
<link rel="preload" href="image.jpg" as="image">     <!-- Préchargement IMAGE -->
<link rel="preload" href="script.js" as="script">    <!-- Préchargement JS -->

<meta http-equiv="cache-control" content="no-cache">        <!-- Désactiver le cache -->
<meta http-equiv="cache-control" content="max-age=3600">    <!-- Temps de mise en cache -->
<meta http-equiv="pragma" content="no-cache">               <!-- Alternative pour désactiver le cache -->

<meta http-equiv="content-encoding" content="gzip">    <!-- Compression des données -->
```
#### CONTROLE
```
<!-- CONTROLE -->
<meta name="distribution" content="global">      <!-- Destination globale -->
<meta name="distribution" content="local">       <!-- Destination locale -->
<meta name="distribution" content="Intranet">    <!-- Utilisateur Intranet -->

<meta name="rating" content="general">           <!-- Contenu général -->
<meta name="rating" content="adult">             <!-- Contenu pour adultes -->
<meta name="rating" content="safe for kids">     <!-- Contenu adapté aux enfants -->

<meta http-equiv="pics-label" content="mature">            <!-- Contenu mature -->
<meta http-equiv="pics-label" content="restricted">        <!-- Contenu restreint -->
<meta http-equiv="pics-label" content="safe">              <!-- Contenu sûr -->
<meta http-equiv="pics-label" content="no-rating">         <!-- Aucune notation -->
<meta http-equiv="pics-label" content="age-restricted">    <!-- Contenu restreint par âge -->
<meta http-equiv="pics-label" content="neutral">           <!-- Contenu neutre -->
```
#### SOCIAL MEDIA
```
<!-- Meta-tags Open Graph -->
<meta property="og:title" content="Titre de votre page">
<meta property="og:description" content="Description de votre site en 160 caractères maximum">
<meta property="og:type" content="website">
<meta property="og:url" content="https://www.votresite.com">
<meta property="og:image" content="https://www.votresite.com/image.jpg">

<!-- Meta-tags Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:site" content="@VotreCompteTwitter">
<meta name="twitter:title" content="Titre de votre page">
<meta name="twitter:description" content="Description de votre site en 160 caractères maximum">
<meta name="twitter:image" content="https://www.votresite.com/image.jpg">
```

#### STYLE
```
<meta name="theme-color" content="#4285f4"> <!-- Modifie couleur interface navigateur avec celle du site-->
<link rel="stylesheet" href="../src/assets/styles/style.css"> <!-- Fichier style.css-->
<link rel="stylesheet" href="../src/assets/styles/print.css" media="print"> <!-- Autre fiche de style spécifique-->
<link rel="stylesheet" href="specific.css" media="print and (feature)"> <!-- Si la condition est vrais-->
```

#### FRAMEWORK
```
<!-- Bootstrap -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
```

---
