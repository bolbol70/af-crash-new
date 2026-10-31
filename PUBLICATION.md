# Publier AF Crash New depuis GitHub

Le code est prêt. Les étapes ci-dessous nécessitent vos comptes GitHub et Cloudflare.
Aucun dépôt distant ni nouvel hébergement n'a encore été créé pour cet export.

## 1. Créer le dépôt GitHub

1. Se connecter à https://github.com puis ouvrir https://github.com/new.
2. Nom du dépôt : `af-crash-new`.
3. Choisir **Public** si le code doit être visible de tous. Le site publié pourra
   aussi être public avec un dépôt privé relié à Cloudflare.
4. Laisser décochées les options README, licence et .gitignore : les fichiers
   locaux sont déjà prêts.
5. Cliquer sur **Create repository**.
6. Copier l'URL HTTPS du dépôt, de la forme `https://github.com/VOTRE-COMPTE/af-crash-new.git`.

## 2. Envoyer les fichiers depuis VS Code

1. Ouvrir ce dossier `af-crash-new-frontend` dans VS Code.
2. Ouvrir **Terminal → Nouveau terminal**. Le terminal doit être situé dans ce
   dossier, celui qui contient directement `index.html`.
3. Exécuter les commandes ci-dessous une à une. Dans la commande `remote`,
   remplacer `VOTRE-COMPTE` par votre identifiant GitHub ou coller l'URL copiée.

```powershell
git init -b main
git add .
git commit -m "Ajouter le frontend AF Crash New"
git remote add origin https://github.com/VOTRE-COMPTE/af-crash-new.git
git push -u origin main
```

Si Git demande votre nom et votre adresse de commit :

```powershell
git config user.name "Votre nom"
git config user.email "Votre adresse de commit GitHub"
```

Renseigner vos propres valeurs, puis relancer le commit et le push. Vous pouvez
utiliser l'adresse `noreply` indiquée dans les paramètres e-mail GitHub.
Si GitHub demande une connexion, la terminer dans le navigateur.
Si `git` n'est pas reconnu, installer Git depuis https://git-scm.com/download/win
puis rouvrir VS Code.

## 3. Créer l'hébergement statique

1. Se connecter à https://dash.cloudflare.com avec un compte Cloudflare.
2. Aller dans **Workers & Pages**.
3. Choisir **Create application → Pages → Import an existing Git repository**.
4. Relier GitHub en autorisant seulement le dépôt `af-crash-new` si cette option
   est proposée, puis sélectionner ce dépôt.
5. Choisir **Begin setup**.
6. Renseigner les paramètres suivants :

| Paramètre | Valeur |
| --- | --- |
| Project name | `af-crash-new`, ou un nom disponible |
| Production branch | `main` |
| Framework preset | `None` |
| Build command | `exit 0` |
| Build output directory | `.` (un point : les fichiers sont à la racine) |
| Root directory | Laisser la valeur par défaut |

7. Cliquer sur **Save and Deploy** et attendre le statut réussi.
8. Ouvrir l'adresse HTTPS fournie par Cloudflare, de la forme `https://NOM.pages.dev`.
   Le nom exact dépend de sa disponibilité ; aucune adresse précise n'est réservée.

Le plan gratuit Pages dispose de limites, notamment 500 builds par mois.
Ce site ne nécessite ni fonctions serveur ni option payante pour son fonctionnement
statique. Un nom de domaine personnalisé acheté séparément reste facultatif.

Documentation :
- https://developers.cloudflare.com/pages/framework-guides/deploy-anything/
- https://developers.cloudflare.com/pages/platform/limits/

## 4. Vérifier l'accès public

1. Ouvrir l'adresse publiée en navigation privée, sans connexion à GitHub.
2. Choisir une marque, chercher une pièce, ajouter un article à la sélection.
3. Préparer une demande de devis et vérifier le numéro WhatsApp : +216 29 011 043.
4. Fermer VS Code : l'adresse publiée doit continuer à fonctionner.
5. Mettre ce lien dans votre fiche Google et le partager aux clients.

Les utilisateurs consultent cette adresse de site, pas la page du dépôt GitHub.

## 5. Mettre le site à jour

Après modification des fichiers dans VS Code :

```powershell
git add .
git commit -m "Mettre à jour le catalogue"
git push
```

Avec l'intégration Git, Cloudflare publie automatiquement la nouvelle version.
Pour le référencement de la nouvelle adresse, voir la section correspondante
dans `README.md`.
