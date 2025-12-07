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

📝 Rapport succinct:
 Difficultés rencontrées :
1️⃣ Problème : Le site affichait la page par défaut de NGINX

Cause : Le fichier principal n’était pas nommé index.html.

Solution : Renommage du fichier EcommerceWebsite.html → index.html.

2️⃣ Problème : Tests qui échouaient dans le CI

Cause : Le script test -f src/EcommerceWebsite.html ne trouvait rien.

Solution : Correction de l’arborescence et du nom du fichier.

3️⃣ Problème : Erreurs “favicon.ico not found” dans NGINX

Cause : NGINX tente de charger un favicon inexistant.

Solution : Erreur bénigne → ignorée.

Preuves du fonctionnement:
-Dockerfile:
--creation de l'image devops-site

<img width="1280" height="420" alt="image" src="https://github.com/user-attachments/assets/c05f6303-48f9-4c76-b333-fc63484334b5" />

--contenarization du site coin blanc (creation d'une instance encours dexecution de l'image devops-site)

<img width="1280" height="479" alt="image" src="https://github.com/user-attachments/assets/5bd66493-a64f-4ac6-b68a-d0a41e9604e2" />

--phase creation et execution du conteneur 

<img width="1280" height="719" alt="image" src="https://github.com/user-attachments/assets/90b46d1f-8360-43c5-842a-c5ee2c905465" />

-Fichier CI/CD (devops.yml)
--preuve du bon deroulement

<img width="1280" height="638" alt="image" src="https://github.com/user-attachments/assets/8317427e-8087-4f7d-8b1c-b0ed17add487" />
<img width="1280" height="490" alt="image" src="https://github.com/user-attachments/assets/e70f0188-7cc0-44ae-a46d-e66cacb2cc08" />


-tester la portabiliter du site:

<img width="1280" height="683" alt="image" src="https://github.com/user-attachments/assets/0ff37594-260c-40af-818e-51938cc35a38" />

