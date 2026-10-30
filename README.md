# Iconocratie — 0.13.2

Application HTML autonome et hors ligne pour organiser des bibliothèques de diaporamas et projeter images, vidéos, sons, PDF et pages titre.

## Démarrage

Ouvrir `index.html` dans Firefox, Safari ou Chromium. L'application ne requiert aucun serveur et ne transfère pas les médias sur GitHub. Les fichiers importés sont conservés localement dans le navigateur (IndexedDB). Exporter régulièrement la bibliothèque en JSON pour garder une sauvegarde portable.

## Nouveau dans la 0.13.1

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


## Version 0.13.1 — organisation visuelle

- Suppression directe d'une diapositive depuis la grille centrale par la croix × (coin supérieur droit). Annulation possible par ⌘Z.
- Suppr/Retour arrière supprime la sélection, confirmation si plusieurs médias.
- Trois dispositions de l'éditeur : Grid (régulière), Columns (colonnes verticales) et Justify (rangées adaptatives). La disposition n'affecte pas l'ordre de projection.
- Réglage de densité (2–9), recherche par nom ou type de média et tri temporaire par nom ou type.
- Par sécurité, les déplacements manuels sont suspendus pendant une recherche ou un tri temporaire. La liste normale peut toujours être restaurée en effaçant la recherche et en choisissant « Ordre du diaporama ».
- Aucun changement au stockage IndexedDB/JSON de la bibliothèque.


### 0.13.1 — Indications clavier
Les raccourcis clavier ne sont présentés que tout en bas de Préférences. Les aides de touches ont été retirées de la projection, du pied de l’éditeur, du panneau bibliothèque et des infobulles de suppression.


## v0.13.1 — Présentations à dispositions multiples

- Mode **Éditer** : grille unique, recherche, tri temporaire, sélection multiple et ordre canonique.
- Mode **Projeter** : menu par diaporama `Slideshow`, `Grid`, `Columns`, `Justify`.
- Slideshow conserve le timer pour images/pages fixes, et la durée réelle pour audio/vidéo.
- Grid/Columns/Justify : galerie défilante sans timer, vignettes de vidéos/audio inactives ; clic pour ouvrir un média en grand, bouton Retour à la galerie.
- Options par diaporama : nombre de colonnes, espacement, couleur de fond.
- Ces options sont conservées dans IndexedDB et les sauvegardes JSON ; les anciens fichiers reçoivent les valeurs par défaut.
- Aucun raccourci affiché en dehors des Préférences.


## 0.13.1 — Export HTML autonome optimisé

**Import / Export → Exporter HTML autonome** produit un fichier HTML de consultation, autonome et en lecture seule, contenant tous les diaporamas et les médias choisis.

- Préréglages d'images 1920, 2560, 3840 pixels ou originaux ; compression WebP si elle diminue le poids sans perdre l'animation GIF ni la nature vectorielle SVG.
- Vidéos, audios, PDF et autres médias non convertis (codec inchangé).
- Présentation Slideshow, Grid, Columns, Justify ; pages titre et liens ; lecture automatique des médias avec leurs durées propres.
- Ne nécessite ni serveur ni bibliothèque externe. Les liens web restent connectés au site distant.
- Pour les grosses vidéos, le HTML peut être volumineux et peu adapté à l'hébergement web. Les navigateurs ont des limites mémoire et de taille de fichier.
- L'export HTML est un document de diffusion ; le JSON reste le format modifiable de sauvegarde.

### v0.13.1 — Éléments d’interface

Le libellé de la liste de gauche est simplement « Diaporamas ». Le bouton « Retour à la galerie » se trouve dans la navigation inférieure, dans l’application et le lecteur HTML exporté.


## 0.13.2 — Noms des images en présentation

L’option « Afficher les noms des images » figure dans Options de chaque diaporama. Activée par défaut, elle affiche les légendes dans Grid, Columns et Justify ; désactivée, elle masque ces légendes, sans modifier les noms dans l’éditeur. Ce choix est conservé dans la bibliothèque JSON et dans le lecteur HTML autonome exporté.