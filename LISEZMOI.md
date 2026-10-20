# Site de lecture de la saga

Quatre fichiers : `index.html` (lecture + administration), `firebase-config.js` (vos identifiants Firebase), `firestore.rules` (sécurité) et ce guide.

## 1. Créer le projet Firebase (10 min)

1. Sur https://console.firebase.google.com, créez un projet (Google Analytics inutile).
2. **Authentication** > Commencer > méthode **E-mail/Mot de passe** > Activer.
3. Onglet **Users** > *Ajouter un utilisateur* : votre e-mail et **le mot de passe d’administration que vous choisissez**.
4. **Firestore Database** > Créer une base (mode production, région `eur3` ou `europe-west`).
5. Onglet **Règles** : collez le contenu de `firestore.rules`, remplacez `VOTRE_EMAIL@exemple.com` par l’e-mail de l’étape 3, puis *Publier*.
6. **Paramètres du projet** > *Vos applications* > icône Web `</>` : enregistrez l’app et copiez la config dans `firebase-config.js`.
7. **Authentication** > Paramètres > *Domaines autorisés* : ajoutez `VOTRE-PSEUDO.github.io`.

Le plan gratuit suffit : les images sont stockées dans Firestore (compressées, moins de 900 Ko chacune), sans activer Firebase Storage.

## 2. Publier sur GitHub Pages

1. Créez un dépôt GitHub public, puis ajoutez `index.html` et `firebase-config.js` à la racine.
2. *Settings* > *Pages* > Source : branche `main`, dossier `/ (root)`.
3. Le lien lecteur sera `https://VOTRE-PSEUDO.github.io/NOM-DU-DEPOT/`.

## 3. Utiliser l’administration

- Le petit engrenage ⚙ très pâle, en bas à droite, ouvre la connexion (e-mail + mot de passe Firebase).
- **Importer la saga** : dans l’atelier, section « Sauvegarde / transfert », cliquez sur *Exporter*, copiez le texte et collez-le dans l’import. Les tomes (titres, numéros, illustrations) sont créés en **brouillon**.
- **Couverture finale** : exportez la couverture en PNG dans l’atelier, puis ajoutez-la au tome. Sans PNG, le site affiche l’illustration avec le titre en doré.
- **Texte d’un tome** : importez un `.txt` ou `.md`.
  - Ligne commençant par `#` ou `Chapitre` = nouveau chapitre.
  - Ligne `[[illustration : légende]]` = page illustrée à cet endroit précis.
  - Vous pouvez aussi ajouter un chapitre, un texte ou une page illustrée entre deux blocs, et déplacer ou supprimer les blocs.
- **Continuer l’écriture** : statut *Brouillon* (invisible des lecteurs), *En cours d’écriture* (lisible, mention « La suite arrive… ») ou *Terminé*.
- Pensez à **Enregistrer le tome** après chaque session.

## Limites à connaître

- Un bloc de texte ne doit pas dépasser environ 1 Mo (l’import découpe déjà en blocs d’environ 8 000 caractères).
- Les pages saga et dos de saga de l’atelier ne sont pas importées : la page d’accueil du site est générée à partir du titre, de la présentation et des couvertures des tomes.
- Les lecteurs retrouvent leur position de lecture, la taille de police et le thème clair ou sombre (mémorisés dans leur navigateur).
