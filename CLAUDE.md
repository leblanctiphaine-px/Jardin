# Jardin de la coloc — guide des fichiers

Base de données + suivi du jardin et des plantes d'intérieur de la colocation (13 personnes).

## Où ranger quoi

- **`plantes.csv`** — LA liste de référence de toutes les plantes (jardin **et** intérieur), une ligne par plante/lot. Colonnes : `nom,zone,emplacement,etat,etat_detail,besoins_eau,ensoleillement,notes`. `zone` = une des zones du tableau « Zones du jardin » de `contexte-jardin.md` (vide = à classer) ; `emplacement` = repère précis dans la zone (ou `stock graines …` / `liste de souhaits …` pour ce qui n'est pas encore planté). `etat` = un tag court parmi `semis`, `en croissance`, `en forme`, `à récolter`, `à surveiller`, `en danger` (ou `à semer` / `à acheter` pour les graines et envies) ; le détail libre va dans `etat_detail`. Le champ `notes` doit inclure une courte description permettant de reconnaître la plante (feuillage, port, couleur) en plus des infos de soin/historique.
- **`taches.csv`** — liste des tâches (jardin et intérieur), avec priorité, responsable et statut. Colonnes : `tache,priorite,responsable,statut,notes,plante` (`plante` = nom exact de la plante liée dans `plantes.csv`, vide sinon). Quand une tâche passe à « fait », noter la date dans `notes` (`fait le JJ/MM/AAAA`) ; les tâches faites sont supprimées au bout d'un mois maximum (l'historique reste dans git).
- **`contexte-jardin.md`** — contexte général et durable : zones du jardin, type de sol, système d'arrosage, nuisibles connus (limaces), collaborateurs (qui fait quoi), préférences alimentaires des colocs, conseils de saison. Pas un inventaire de plantes — n'y ajoute pas de tableau de plantes, ça va dans `plantes.csv`.
- **`README.txt`** — présentation du projet (objectifs généraux). Rarement à modifier.
- **`photos/`** — photos du jardin par zone.
- **`index.html`** — le Carnet du jardin : interface web (GitHub Pages) pour gérer `plantes.csv`, `taches.csv` et `contexte-jardin.md`. Chaque modification faite dans l'interface devient un commit sur `main`. Si tu changes les colonnes d'un CSV ou la structure en sections `##` du contexte, mets l'interface à jour.

## Réflexe à chaque action sur une plante

Dès qu'une plante est semée, repiquée, plantée, déplacée, meurt ou est récoltée définitivement : mettre à jour `plantes.csv` avec la date de l'action, l'emplacement précis (zone + repère visuel si possible), et toute info utile (protection, état observé). Objectif : construire une vraie cartographie du jardin dans le temps.

## Réflexe nuisibles

Limaces = problème sévère et récurrent. Toujours le mentionner quand on plante quelque chose de sensible (laitue, basilic, jeunes poireaux, semis en général). Voir détails et solutions dans `contexte-jardin.md`.
