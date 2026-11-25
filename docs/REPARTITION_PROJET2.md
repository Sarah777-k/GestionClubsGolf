# Projet 2 — Gestion de clubs de golf

## Répartition des tâches et branches Git

**Équipe :** Sarah Khodjaoui, Nesma-Dalel Medjber, Gabriel Lajoie  
**Cours :** 420-B56 — Bases de données III  
**Référence :** `gestion_de_projet_2.xlsx` (onglets `Liste` et `Taches`)

### 1. Répartition générale

| Rôle | Responsable | Travail principal | Branche Git |
|---|---|---|---|
| A | **Nesma** | LINQ to SQL, connexion, menu, droits d'accès, employés, dépenses et intégration | `feature/nesma-acces-employes-depenses` |
| B | **Sarah** | Abonnements, réabonnements, mise à jour des abonnés, tarifs et parties jouées | `feature/sarah-abonnements-parties-tarifs` |
| C | **Gabriel** | Données initiales et de test, rapports et statistiques | `feature/gabriel-rapports-statistiques` |

### 2. Dossiers et fichiers attribués
Ne pas oublier la configuration de connexion, sans identifiants personnels dans Git  dans App.config

| Dossier ou fichier | Responsable | Contenu |
|---|---|---|
| `src/GestionClubsGolf/Data/` | Nesma (coordination) | Modèle LINQ to SQL commun (`.dbml`) |
| `src/GestionClubsGolf/Forms/Authentification/` | Nesma | Connexion et déconnexion |
| `src/GestionClubsGolf/Forms/Commun/` | Nesma | Menu, navigation et droits d'accès |
| `src/GestionClubsGolf/Forms/Employes/` | Nesma | Liste, ajout, modification et suppression des employés |
| `src/GestionClubsGolf/Forms/Depenses/` | Nesma | Inscription d'une dépense, service associé, résumé |
| `src/GestionClubsGolf/Forms/Abonnements/` | Sarah | Abonnements, dépendants, réabonnements et mise à jour des abonnés |
| `src/GestionClubsGolf/Forms/Tarification/` | Sarah | Modification annuelle des prix et dépenses obligatoires |
| `src/GestionClubsGolf/Forms/Parties/` | Sarah | Inscription des parties jouées |
| `src/GestionClubsGolf/Forms/Rapports/` | Gabriel | Six rapports |
| `src/GestionClubsGolf/Forms/Statistiques/` | Gabriel | Six statistiques |
| `sql/02_insertions_initiales.sql` | Gabriel | Types, provinces, terrains, administrateur et données de test |
| `docs/`, `README.md`, `.sln`, `.csproj` | Commun | Documentation et fichiers partagés du projet |

Les dossiers sont réservés aux modules. Chacun crée ses formulaires lorsqu'il commence son travail. Aucun formulaire n'est imposé dans le squelette.


### 3. Branches et intégration

**Branche commune :** `main` — code validé et prêt à être repris par l'équipe.

**Branches de travail :**

- Nesma : `feature/nesma-acces-employes-depenses`
- Sarah : `feature/sarah-abonnements-parties-tarifs`
- Gabriel : `feature/gabriel-rapports-statistiques`

Pour créer sa branche à partir du dépôt :

```bash
git switch main
git pull origin main
git switch -c feature/nom-de-la-branche
git push -u origin feature/nom-de-la-branche
```

Remplacer `feature/nom-de-la-branche` par la branche attribuée dans le tableau. Les commits se font dans sa branche. L'intégration dans `main` se fait par pull request après vérification.

**Fichiers à coordonner :**

- `sql/01_creation_tables.sql` : modifications validées entre Nesma et Sarah avant intégration.
- `sql/02_insertions_initiales.sql` : Gabriel prépare les insertions; Sarah et Nesma vérifient que les données permettent leurs tests.
- `Data/*.dbml` : Nesma coordonne le modèle commun. Éviter les modifications simultanées du concepteur LINQ to SQL.
- `Program.cs`, `App.config`, `.csproj` et le menu : prévenir la personne responsable avant de modifier ces fichiers.
- Chaque personne développe et teste ses formulaires dans son propre dossier.

### 8. Règles de travail


- Les données de test doivent inclure des employés, abonnements, réabonnements, services, dépenses et parties à plusieurs dates pour couvrir les rapports et statistiques.
- Les modules utilisent **LINQ to SQL**, selon les consignes du projet 2. Chaque personne vérifie ses validations et ses conflits d'accès.
- Nesma et Sarah effectuent l'intégration finale. **Le 10 décembre**, si un livrable du module C manque, l'équipe réattribue ce qui reste à faire.
- Ne pas pousser de mots de passe, de fichiers locaux Visual Studio, ni de chaînes de connexion contenant des identifiants dans Git.

### 8. Remises

| Remise | Date limite |
|---|---|
| Base de données | 25 novembre 2026, 00 h |
| Au moins trois cas d'utilisation fonctionnels | 2 décembre 2026, 00 h |
| Projet final | 16 décembre 2026, 00 h |

Les dates des tâches ci-dessus sont les échéances internes du fichier Excel. Les trois dates de remise sont celles de l'énoncé du projet.
