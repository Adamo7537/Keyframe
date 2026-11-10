# Keyframe — site web public

Application web de montage vidéo côté navigateur, construite avec React et Vite.

## Fonctions incluses
- Interface studio sombre responsive
- Import local de vidéos, images et fichiers audio
- Aperçu vidéo et image
- Timeline séquentielle vidéo / titres
- Ajout de cartes de titre
- Réglage du début et de la fin des clips
- Réorganisation des clips
- Enregistrement de la structure du projet en JSON
- Export navigateur en WebM avec MediaRecorder (Chrome / Edge recommandé)

## Lancer en local
Installe Node.js LTS depuis https://nodejs.org/

Dans un terminal, dans ce dossier :
```bash
npm install
npm run dev
```
Ouvre l'adresse locale indiquée, généralement http://localhost:5173

Tester la version de production :
```bash
npm run build
npm run preview
```
Le site compilé est créé dans `dist/`.

## Mettre en ligne gratuitement avec Netlify
1. Crée un compte sur https://app.netlify.com/
2. Décompresse le ZIP puis crée un dépôt GitHub et envoie tous les fichiers du projet.
3. Dans Netlify, clique sur **Add new site** > **Import an existing project**.
4. Connecte GitHub et choisis le dépôt `Keyframe`.
5. Paramètres de build :
   - Build command : `npm run build`
   - Publish directory : `dist`
6. Clique sur **Deploy**. Netlify attribuera une adresse publique `*.netlify.app`.
7. Pour un domaine personnalisé, achète un domaine chez un registrar et ajoute-le dans **Domain management** sur Netlify.

## Mise en ligne avec Vercel
1. Envoie le projet sur GitHub.
2. Connecte-toi sur https://vercel.com/
3. Importe le dépôt.
4. Framework : Vite ; Build command : `npm run build` ; Output directory : `dist`.
5. Clique sur Deploy. Vercel fournit une URL publique.

## Important : limites de cette version
- Le montage et l'export se font dans le navigateur de l'utilisateur ; les fichiers vidéo ne sont pas envoyés sur un serveur.
- L'export de cette version est en WebM, pas en MP4. Le navigateur et les codecs disponibles peuvent influencer la compatibilité.
- Le projet JSON mémorise la structure du montage, mais les médias doivent être réimportés après rechargement pour reconnecter les fichiers locaux.
- Les pistes audio multiples, transitions avancées, effets appliqués au rendu, sous-titres automatiques, collaboration, comptes utilisateurs et export MP4/4K serveur ne sont pas encore inclus.
- Pour un vrai service de production de type CapCut, il faudra un moteur de rendu vidéo (FFmpeg côté serveur ou WebAssembly), une gestion de stockage, des tâches d'export et des protections de ressources. L'hébergement statique Netlify/Vercel publie le front-end, pas un moteur de rendu serveur.

## Déploiement statique Netlify
Le dossier `netlify/` contient une configuration optionnelle de cache. Aucune variable secrète n'est nécessaire pour cette version.
