# coin_blanc_devops
Coin Blanc est un site web e-commerce moderne dédié à la décoration intérieure, au design d’espace et au mobilier contemporain. Ce projet utilise HTML, CSS et JavaScript pour offrir une interface simple, élégante et intuitive adaptée aux utilisateurs cherchant à transformer leur espace de vie.

# 🧩 Projet DevOps – Déploiement d’un site statique avec Docker & GitHub Actions

## 📁 1. Structure du dépôt

Ce dépôt contient :
- Le **code source du site web** (HTML/CSS/Images) dans le dossier `src/`
- Le **Dockerfile** à la racine du projet
- Le fichier **CI/CD** situé dans `.github/workflows/devops.yml`
- Un **README** expliquant la démarche DevOps suivie

Arborescence :

<img width="899" height="400" alt="image" src="https://github.com/user-attachments/assets/fe76431a-62f0-4828-9806-9cd3854fa269" />

## 📝 2. Rapport succinct
🧩 Difficultés rencontrées et solutions apportées
1️⃣ Problème : Le site affichait la page par défaut de NGINX

Cause : Le fichier principal n’était pas nommé index.html.
Conséquence : NGINX ne trouvait pas de point d’entrée et affichait sa page par défaut.
Solution : Renommage du fichier EcommerceWebsite.html → index.html.

2️⃣ Problème : Tests échoués dans le pipeline CI/CD

Cause : Le script test -f src/EcommerceWebsite.html ne trouvait aucun fichier après le renommage.
Solution : Mise à jour du script et correction de l’arborescence du dossier src pour correspondre à la nouvelle structure du projet.

3️⃣ Problème : Incohérences entre l’arborescence locale et celle du dépôt GitHub

Cause : Certains fichiers n’avaient pas été ajoutés/committés correctement, ce qui provoquait des erreurs dans la CI qui s’attendait à une structure spécifique.
Solution : Réorganisation complète du dépôt + commits propres pour aligner la structure locale avec celle analysée par le pipeline GitHub Actions.

📸 Preuves du fonctionnement
✔️ Dockerfile

Création de l’image devops-site
<img width="1280" height="420" alt="image" src="https://github.com/user-attachments/assets/c05f6303-48f9-4c76-b333-fc63484334b5" />

Conteneurisation du site Coin Blanc
<img width="1280" height="479" alt="image" src="https://github.com/user-attachments/assets/5bd66493-a64f-4ac6-b68a-d0a41e9604e2" />

Création et exécution du conteneur
<img width="1280" height="719" alt="image" src="https://github.com/user-attachments/assets/90b46d1f-8360-43c5-842a-c5ee2c905465" />

✔️ Pipeline CI/CD (devops.yml)

Preuve du bon déroulement du workflow GitHub Actions
<img width="1280" height="638" alt="image" src="https://github.com/user-attachments/assets/8317427e-8087-4f7d-8b1c-b0ed17add487" />
<img width="1280" height="490" alt="image" src="https://github.com/user-attachments/assets/e70f0188-7cc0-44ae-a46d-e66cacb2cc08" />

✔️ Test de portabilité du site

Affichage correct du site dans un navigateur via le conteneur
<img width="1280" height="683" alt="image" src="https://github.com/user-attachments/assets/0ff37594-260c-40af-818e-51938cc35a38" />
