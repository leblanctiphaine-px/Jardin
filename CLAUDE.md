# Jardin de la coloc — guide des fichiers

Base de données + suivi du jardin et des plantes d'intérieur de la colocation (13 personnes).

## Où ranger quoi

- **`plantes.csv`** — LA liste de référence de toutes les plantes (jardin **et** intérieur), une ligne par plante/lot. Colonnes : `nom,emplacement,etat,besoins_eau,ensoleillement,notes`. Le champ `notes` doit inclure une courte description permettant de reconnaître la plante (feuillage, port, couleur) en plus des infos de soin/historique.
- **`taches.csv`** — liste des tâches (jardin et intérieur), avec priorité, responsable et statut. Colonnes : `tache,priorite,responsable,statut,notes`.
- **`contexte-jardin.md`** — contexte général et durable : zones du jardin, type de sol, système d'arrosage, nuisibles connus (limaces), collaborateurs (qui fait quoi), préférences alimentaires des colocs, conseils de saison. Pas un inventaire de plantes — n'y ajoute pas de tableau de plantes, ça va dans `plantes.csv`.
- **`README.txt`** — présentation du projet (objectifs généraux). Rarement à modifier.
- **`photos/`** — photos du jardin par zone.

## Réflexe à chaque action sur une plante

Dès qu'une plante est semée, repiquée, plantée, déplacée, meurt ou est récoltée définitivement : mettre à jour `plantes.csv` avec la date de l'action, l'emplacement précis (zone + repère visuel si possible), et toute info utile (protection, état observé). Objectif : construire une vraie cartographie du jardin dans le temps.

## Réflexe nuisibles

Limaces = problème sévère et récurrent. Toujours le mentionner quand on plante quelque chose de sensible (laitue, basilic, jeunes poireaux, semis en général). Voir détails et solutions dans `contexte-jardin.md`.
