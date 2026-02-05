# 💿 Mission 2 : Création du Poste Maître (Master)

Cette section détaille la création de la machine virtuelle de référence qui servira de base au déploiement sur l'ensemble du parc informatique de **Mille Nuits**.

## 1. Objectif de la mission

L'objectif est de préparer un environnement **Windows 11** propre, configuré avec les standards de l'entreprise, afin de pouvoir le cloner ultérieurement sur 19 autres postes.

**Contraintes respectées :**
* Système d'exploitation : **Windows 11 Pro**
* Compte administrateur local imposé.
* Suite logicielle standard installée.

---

## 2. Configuration de la Machine Virtuelle (VirtualBox)

La VM a été paramétrée pour respecter les prérequis matériels stricts de Windows 11 (TPM 2.0 et Secure Boot).

| Paramètre              | Valeur Configurée                                      |
| :--------------------- | :----------------------------------------------------- |
| **Nom de la VM**       | `Master-MilleNuits-W11`                                |
| **Mémoire Vive (RAM)** | 4096 Mo (4 Go) ou 8096 Mo (8Go)                        |
| **Processeur (vCPU)**  | 2 Cœurs                                                |
| **Module TPM**         | Activé (Version 2.0)                                   |
| **Réseau**             | NAT (Déconnecté temporairement lors de l'installation) |

---

## 3. Installation du Système (Bypass Compte Microsoft)

Pour respecter la contrainte d'un **compte local** (et non un compte Microsoft en ligne), une procédure spécifique a été appliquée lors de l'installation (OOBE).

**Procédure appliquée :**
1.  Lancement de l'installation standard de Windows 11.
2.  À l'écran de connexion réseau, déconnexion physique (ou virtuelle) de la carte réseau.
3.  Ouverture de l'invite de commande avec `MAJ + F10`.
4.  Exécution de la commande de contournement :
```
    OOBE\BYPASSNRO
```
5.  Après redémarrage, sélection de l'option **"Je n'ai pas Internet"** pour forcer la création du compte local.

> **Source de la procédure :** Cette méthode est documentée sur la communauté technique Microsoft.

---

## 4. Configuration Utilisateur

Conformément aux directives du service informatique, le compte administrateur local a été créé avec les identifiants suivants :

* **Nom d'utilisateur :** `Admin-MilleNuits`
* **Mot de passe :** `Mille_2026`
* **Privilèges :** Administrateur local

---

## 5. Installation des Logiciels Standards

Le poste maître a été enrichi avec la suite logicielle demandée par le service administratif. Tous les logiciels ont été testés après installation.

| Logiciel | Rôle | État |
| :--- | :--- | :--- |
| **Firefox** | Navigateur Web par défaut | ✅ Installé |
| **LibreOffice** | Suite Bureautique | ✅ Installé |
| **VLC Media Player** | Lecteur Multimédia | ✅ Installé |
| **Adobe Acrobat** | Lecteur de fichiers PDF | ✅ Installé |

---

## 6. Préparation au déploiement (Sysprep)

*Note : Cette étape sera réalisée juste avant la capture de l'image (Mission 3).*
L'outil **Sysprep** sera utilisé pour généraliser l'installation (suppression des ID uniques) avant le clonage.