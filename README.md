# Iconocratie — 0.11.1

Application HTML autonome et hors ligne pour organiser des bibliothèques de diaporamas et projeter images, vidéos, sons, PDF et pages titre.

## Démarrage

Ouvrir `index.html` dans Firefox, Safari ou Chromium. L'application ne requiert aucun serveur et ne transfère pas les médias sur GitHub. Les fichiers importés sont conservés localement dans le navigateur (IndexedDB). Exporter régulièrement la bibliothèque en JSON pour garder une sauvegarde portable.

## Nouveau dans la 0.11.1

- **Éditer / Projeter** : un espace central d'édition en grille, distinct du mode plein écran / projection.
- Densité de la grille réglable de 2 à 9 colonnes.
- Sélection multiple dans la grille et la colonne gauche (`⌘`/`Ctrl` + clic ; `Maj` + clic).
- Déplacement d'un groupe de médias par glisser-déposer, dans un diaporama ou vers un autre.
- Insertion précise entre deux médias depuis la grille, la colonne gauche et le Finder (trait bleu avant ou après l'élément visé).
- Chevron des diaporamas : ouvre / replie d'un seul clic. Clic sur le nom : sélectionne sans forcer l'ouverture.
- Chargement des miniatures lorsque leurs éléments deviennent visibles, afin de limiter les opérations sur de grandes listes.
- Double-clic sur une vignette en mode Éditer pour revenir à sa projection.

## Commandes

- `Espace` : lecture/pause.
- `↑` / `↓` : diapositive précédente/suivante.
- `←` / `→` : modifier la durée des images fixes.
- `F` : plein écran en mode projection.
- `⌘ Z` / `⌘ ⇧ Z` : annuler / rétablir (Ctrl sous Windows).
- `⌘` + clic / `Maj` + clic : sélection multiple / plage.

Les formats vidéo et audio dépendent des codecs pris en charge par le navigateur. Les liens Internet intégrés restent soumis aux politiques des sites visités.

## Précautions

Le mode Grid est une **vue d'édition** : il ne modifie pas le rendu du diaporama projeté. Les dispositions Columns, Justify et Freeform sont réservées à de futures versions. Aucune action GitHub n'est nécessaire pour utiliser localement l'application.

## Développement

Le code est volontairement contenu dans `index.html` (HTML/CSS/JavaScript), sans dépendances. La licence MIT s'applique au code, pas aux médias importés par les utilisateurs.


## Version 0.11.1 — organisation visuelle

- Suppression directe d'une diapositive depuis la grille centrale par la croix × (coin supérieur droit). Annulation possible par ⌘Z.
- Suppr/Retour arrière supprime la sélection, confirmation si plusieurs médias.
- Trois dispositions de l'éditeur : Grid (régulière), Columns (colonnes verticales) et Justify (rangées adaptatives). La disposition n'affecte pas l'ordre de projection.
- Réglage de densité (2–9), recherche par nom ou type de média et tri temporaire par nom ou type.
- Par sécurité, les déplacements manuels sont suspendus pendant une recherche ou un tri temporaire. La liste normale peut toujours être restaurée en effaçant la recherche et en choisissant « Ordre du diaporama ».
- Aucun changement au stockage IndexedDB/JSON de la bibliothèque.

### 0.11.1 — Indications clavier
Les raccourcis ne sont affichés que tout en bas de Préférences. Retrait des rappels de touches de la projection, de la grille centrale, de la bibliothèque et des infobulles.
