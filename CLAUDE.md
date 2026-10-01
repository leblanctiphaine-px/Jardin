# Jardin de la coloc — guide des fichiers

Base de données + suivi du jardin et des plantes d'intérieur de la colocation (13 personnes).

## Où ranger quoi

- **`plantes.csv`** — LA liste de référence de toutes les plantes (jardin **et** intérieur), une ligne par plante/lot. Colonnes : `nom,zone,etat,etat_detail,besoins_eau,ensoleillement,notes`. `zone` = une des zones du tableau « Zones du jardin » de `contexte-jardin.md` (vide = à classer), ou `Stock de graines` / `Liste de souhaits` pour ce qui n'est pas encore planté ; un repère plus précis (pot, bac…) va dans `notes`. `etat` = un tag court parmi `semis`, `en croissance`, `en forme`, `à récolter`, `à surveiller` (ou `à semer` / `à acheter` pour les graines et envies) ; le détail libre va dans `etat_detail`. `besoins_eau` ∈ `faible`, `moyen`, `élevé`, `très élevé` ; `ensoleillement` ∈ `plein soleil`, `mi-ombre`, `ombre` (extérieur) ou `1/5` à `5/5` (intérieur, légende dans le contexte). Toute précision (quantité d'eau, etc.) va dans `notes`, affiché « Description » dans l'interface. Le champ `notes` doit inclure une courte description permettant de reconnaître la plante (feuillage, port, couleur) en plus des infos de soin/historique.
- **`taches.csv`** — liste des tâches (jardin et intérieur), avec priorité, responsable et statut. Colonnes : `tache,priorite,responsable,statut,notes,plante` (`plante` = nom exact de la plante liée dans `plantes.csv`, vide sinon). Quand une tâche passe à « fait », noter la date dans `notes` (`fait le JJ/MM/AAAA`) ; les tâches faites sont supprimées au bout d'un mois maximum (l'historique reste dans git).
- **`bilans.csv`** — ce qui a marché ou non, pour décider quoi refaire. Colonnes : `date,plante,resultat,pourquoi,fiche` (`resultat` ∈ `réussi`, `mitigé`, `raté` ; `fiche` = nom de la fiche de Graines et envies concernée). Quand une plante est retirée de `plantes.csv` (récolte finie, morte, jetée), demander comment ça s'est passé et ajouter une ligne ici.
- **`contexte-jardin.md`** — contexte général et durable : zones du jardin, type de sol, système d'arrosage, nuisibles connus (limaces), conseils de saison. Pas un inventaire de plantes — n'y ajoute pas de tableau de plantes, ça va dans `plantes.csv`.
- **`README.txt`** — présentation du projet (objectifs généraux). Rarement à modifier.
- **`photos/`** — photos du jardin par zone.
- **`index.html`** — le Carnet du jardin : interface web (GitHub Pages) pour gérer `plantes.csv`, `taches.csv`, `bilans.csv` et `contexte-jardin.md`. Chaque modification faite dans l'interface devient un commit sur `main`. Si tu changes les colonnes d'un CSV ou la structure en sections `##` du contexte, mets l'interface à jour.

## Réflexe à chaque action sur une plante

Dès qu'une plante est semée, repiquée, plantée, déplacée, meurt ou est récoltée définitivement : mettre à jour `plantes.csv` avec la date de l'action, la zone (et un repère visuel dans les notes si utile), et toute info utile (protection, état observé). Objectif : construire une vraie cartographie du jardin dans le temps.

## Réflexe nuisibles

Limaces = problème sévère et récurrent. Toujours le mentionner quand on plante quelque chose de sensible (laitue, basilic, jeunes poireaux, semis en général). Voir détails et solutions dans `contexte-jardin.md`.
