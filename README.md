# AF Crash New — Frontend

Catalogue automobile en HTML, CSS et JavaScript natifs. Aucun framework,
serveur applicatif, installation npm ou base de données ne sont nécessaires.
Contact WhatsApp : +216 29 011 043.

## Ouvrir dans VS Code et sur son ordinateur

1. Dans VS Code, choisir **Fichier → Ouvrir le dossier**.
2. Sélectionner ce dossier `af-crash-new-frontend`.
3. Dans l'Explorateur Windows, double-cliquer sur `index.html` pour consulter le site.
   On peut également utiliser l'extension Live Server de VS Code pour l'aperçu.

Le catalogue et les logos fonctionnent même par double-clic : les marques sont
chargées par `brands.js`, sans `fetch`. Les polices Google Fonts sont facultatives :
des polices de secours sont prévues. Ouvrir WhatsApp demande Internet.

## Ce que contient le site

- 50 marques avec logos et recherche de pièces.
- 11 types de pièces et photos d'illustration.
- Filtres, fiches détaillées, quantités et sélection conservée dans le navigateur
  lorsque le stockage local est disponible.
- Demande de devis préparée dans le navigateur puis ouverte dans WhatsApp.
- Affichage adapté aux mobiles.

Le visiteur relit et envoie lui-même son message WhatsApp. Il n'y a pas de paiement
en ligne, de gestion de stock centralisée ni d'administration serveur.

## Modifier le catalogue

| Fichier | Utilisation |
| --- | --- |
| `index.html` | Textes et structure de la page |
| `style.css`, `premium.css` | Couleurs, mise en page et mobile |
| `app.js` | Recherche, filtres, sélection et devis |
| `catalogue.js` | Téléphone, pièces, descriptions, photos et prix |
| `brands.js` | Liste des marques et chemins des logos |
| `assets/` | Images et logos locaux |

Dans `catalogue.js`, `price: null` affiche « Prix sur demande » ;
`price: 250` affiche un prix de 250 DT. Les images actuelles sont des illustrations :
remplacer les photos et descriptions par celles des articles réellement proposés.
Une modification des fichiers puis un nouveau push mettront le catalogue à jour.

## Publier pour que les visiteurs accèdent au site

Suivre [PUBLICATION.md](PUBLICATION.md) : dépôt GitHub pour le code,
puis Cloudflare Pages pour l'hébergement statique et le lien public HTTPS.
Publier uniquement un dépôt GitHub n'ouvre pas automatiquement le site aux visiteurs.

GitHub Pages exclut l'hébergement d'une boutique ou d'un site destiné principalement
à faciliter des transactions commerciales. Nous utilisons donc GitHub pour le code
et Cloudflare Pages pour la publication de ce catalogue commercial.
Source : https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits

Après publication, le site est consultable même lorsque votre ordinateur et VS Code
sont fermés. Son apparition dans les résultats Google est une étape distincte.

## Référencement après changement d'adresse

L'export ne contient pas de lien canonique vers l'ancien hébergement, ni son sitemap,
ni son fichier de validation Google. La version actuellement publiée reste intacte.

Une fois l'adresse définitive connue :

1. Ajouter cette nouvelle URL comme URL canonique et `og:url` dans `index.html` ;
   ajouter l'URL absolue de `assets/hero-v2.png` comme `og:image`.
2. Créer un `sitemap.xml` avec la nouvelle URL et le déclarer dans `robots.txt`.
3. Valider cette nouvelle adresse dans Google Search Console avec le fichier ou
   la balise fournie pour cette propriété, puis soumettre le nouveau sitemap.
4. Remplacer l'adresse du site dans la fiche Google Business Profile.

Ces réglages n'empêchent pas la consultation du site. L'indexation et le classement
dans Google ne sont pas garantis par l'hébergement.

## Sources des illustrations

Les références des visuels hérités de la version précédente se trouvent dans `docs/`.
