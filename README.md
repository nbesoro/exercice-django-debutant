# Exercice : Construire un mini-portfolio avec Django

## Étape 1 : Créer un projet Django
- Créez un projet nommé **portfolio**.

## Étape 2 : Préparer les templates
- Dans le dossier principal de votre projet, créez un dossier nommé **templates**.
- Ajoutez trois fichiers dans ce dossier :
  - **home.html**
  - **about.html**
  - **detail.html**

## Étape 3 : Créer les vues
- Créez trois vues dans **views.py** :
  - Une vue pour afficher la page **home**.
  - Une vue pour afficher la page **about**.
  - Une vue pour afficher la page **detail**.

## Étape 4 : Dynamiser les pages
1. **Page Home** :
   - Dans la vue **home**, définissez une liste de dictionnaires représentant vos projets avec les clés suivantes :
     - `title` (titre du projet)
     - `description` (description du projet)
     - `created_at` (date de création)
     - `id` (identifiant du projet)
   - Exemple de données à passer au contexte :
     ```python
     projects = [
         {
             "id": 1,
             "title": "Gestionnaire de Tâches",
             "description": "Une application web pour gérer des tâches personnelles avec des notifications.",
             "created_at": "2024-10-10",
         },
         {
             "id": 2,
             "title": "Portfolio Personnel",
             "description": "Un site vitrine pour afficher vos compétences, projets et expériences.",
             "created_at": "2024-09-15",
         },
         {
             "id": 3,
             "title": "Blog Technologique",
             "description": "Un blog permettant de publier et commenter des articles sur la technologie.",
             "created_at": "2024-08-05",
         },
     ]
     ```
   - Affichez ces informations dans un tableau ou une liste sur la page **home.html**.

2. **Page About** :
   - Dans la vue **about**, définissez un dictionnaire contenant vos informations personnelles (par exemple, `nom`, `email`, `profession`, etc.).
   - Exemple de données à passer au contexte :
     ```python
     about_info = {
         "name": "Jean Dupont",
         "email": "jean.dupont@example.com",
         "profession": "Développeur Web",
         "bio": "Passionné par le développement web, j'aide les entreprises à concevoir des solutions modernes et efficaces.",
         "skills": ["Python", "Django", "HTML", "CSS", "JavaScript"],
         "hobbies": ["Lecture", "Voyages", "Coding"],
     }
     ```
   - Affichez ces informations de manière structurée sur la page **about.html**.

3. **Page Detail** :
   - Dans la vue **detail**, utilisez un paramètre d’URL pour récupérer l’identifiant (`id`) d’un projet.
   - Exemple de recherche du projet correspondant :
     ```python
     def detail(request, project_id):
         project = ?
         return render(request, "detail.html", {"project": project})
     ```
   - Affichez les informations du projet correspondant sur la page **detail.html**.

## Bonus : Ajouter des liens entre les pages
- Ajoutez un menu de navigation sur toutes les pages pour permettre de passer de **Home** à **About** et vice-versa.
- Sur la page **Home**, ajoutez des liens pour accéder aux détails de chaque projet via leur `id`.
