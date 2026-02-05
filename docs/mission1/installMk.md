# Installation de l'Environnement de Documentation

Ce guide détaille la procédure complète pour installer et configurer l'environnement de travail technique du projet **Mille Nuits**.

## 1. Prérequis Techniques
Assurez-vous que les logiciels suivants sont installés sur votre poste de travail :

| Outil | Rôle | Vérification (Terminal) |
| :--- | :--- | :--- |
| **Python** (v3.x) | Langage nécessaire pour MkDocs | `python --version` |
| **PIP** | Gestionnaire de paquets Python | `pip --version` |
| **Git** | Gestionnaire de versions | `git --version` |
| **VS Code** | Éditeur de texte recommandé | `Aucune` |

---
## 2. Installation de MkDocs
L'installation se réalise via le terminal.
### Étape 1 : Installation du moteur
Exécutez la commande suivante pour télécharger MkDocs et ses dépendances :
```
pip install mkdocs
```

Étape 2 : Installation du thème (Optionnel)
Pour obtenir un rendu visuel professionnel (comme le thème ReadTheDocs ou Material), installez le paquet supplémentaire :
```
pip install mkdocs-material
```
Étape 3 : Validation
Vérifiez que l'installation s'est bien passée :
```
mkdocs --version
```
# Doit afficher : mkdocs, version 1.x.x

3. Création et Configuration du Projet
Étape 1 : Initialisation
Placez-vous dans le dossier de votre projet et lancez :
```
mkdocs new .    # Cette commande crée le fichier mkdocs.yml (configuration) et le dossier docs/ (contenu).
```

Étape 2 : Configuration
Modifiez le fichier mkdocs.yml pour définir le nom du site et la navigation (voir le fichier de configuration fourni dans la documentation principale).

4. Utilisation Quotidienne
Pour rédiger la documentation, nous utilisons un serveur local qui permet de voir le résultat en direct.

Commande de lancement :
```
mkdocs serve    # Accès au site : Ouvrez votre navigateur à l'adresse : http://127.0.0.1:8000
```
(Note : Le site se met à jour automatiquement à chaque sauvegarde d'un fichier .md).

5. Publication en Ligne (GitHub Pages)
L'hébergement est assuré gratuitement par GitHub Pages.

Lancez la commande de déploiement automatique :
```
1. Préparer les fichiers
git add .

2. Valider la version
git commit -m "Mise a jour documentation depuis Obsidian"

3.Connecter à GitHub
git remote add origin https://github.com/UTILISATEUR/DEPOT.git

4. Envoie de la version
git push origin master

5. Déployer sur la branche pour crée le site web
mkdocs gh-deploy
```

La commande "mkdocs gh-deploy"  va :
Générer le site statique (HTML/CSS).
Pousser les fichiers sur la branche gh-pages de votre dépôt.
Rendre le site accessible publiquement.

### Rappel pour la suite
Une fois ce fichier créé, votre structure de dossiers pour la **Mission 1** devrait ressembler à ceci dans VS Code :

```
MonProjet/
├── mkdocs.yml          (La configuration)
└── docs/
    ├── index.md        (L'accueil)
    └── mission1/
        ├── comparatif.md
        └── installation.md
```