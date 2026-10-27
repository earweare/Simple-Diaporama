# Iconocratie — v0.9.4

Application HTML autonome pour organiser et projeter une bibliothèque de diaporamas.

## Utilisation

Ouvrir `index.html` dans Firefox, Safari ou Chromium. Aucun serveur, compte ni installation requis. Les fichiers importés sont stockés localement dans le navigateur via IndexedDB. **Ne pas effacer les données du site/navigateur sans exporter la bibliothèque.** Pour transférer le travail sur un autre ordinateur, utiliser « Exporter bibliothèque » puis « Importer un diapo ».

- Colonne gauche : créer, nommer, replier et ouvrir différents diaporamas ; importer et ordonner les médias par glisser-déposer. Un média peut être déplacé vers un autre diaporama par glisser-déposer.
- Format de projection : écran ou ratio 16:9, 4:3, 3:2, 1:1, 9:16 ou dimensions personnalisées. Réglages indépendants pour chaque diaporama.
- Mode d'ajustement : Adapter (sans découpe), Remplir (recadrage) ou Étirer (déformation). Les réglages s'appliquent aux médias visuels d'un même diaporama.
- Défilement automatique : lecture/pause, vitesse en secondes, option boucle.
- Raccourcis : **Espace** lecture/pause ; **↑ / ↓** diapositive précédente/suivante ; **← / →** réduire/augmenter l'intervalle d'une seconde ; **F** plein écran ; **Échap** pour le quitter. La durée s'affiche brièvement en bas à droite.
- Pages titre : bouton **+ Page titre** ; édition dans le panneau gauche, blanc sur noir en Helvetica Neue par défaut. Ajuster police, taille, couleur du texte et du fond, style de paragraphe, alignement et position. Terminer replie l’éditeur ; cliquer sur « Éditer la page » pour rouvrir les réglages. Les pages titre se déplacent comme les médias et sont conservées dans les exports JSON v0.3.
- Sauvegarde : export JSON d'un diaporama ou de toute la bibliothèque, médias inclus. L'ancien JSON v0.1 reste importable.

L'affichage de certains formats d'image, vidéo, audio et PDF dépend des codecs et des fonctionnalités du navigateur. Les fichiers non compatibles peuvent être conservés et téléchargés, mais pas nécessairement prévisualisés.

## Technique

Un seul `index.html`, aucun paquet ou accès réseau. Stockage IndexedDB local avec deux magasins (`decks`, `media`). La bibliothèque n'est pas synchronisée automatiquement entre navigateurs ou appareils.


## v0.4 — Liens Internet

Le bouton « + Lien Internet » ajoute une diapositive web. Certains sites interdisent l'intégration en iframe : le lien « Ouvrir dans un onglet » reste disponible. Les liens sont conservés dans les exports JSON, mais exigent une connexion réseau.

## v0.5 — Durée des médias

- Images, titres, PDF et pages web : temps réglable du diaporama.
- Vidéos et audios : pas de timer fixe ; passage automatique à la diapositive suivante à l’événement `ended` (fin réelle de lecture).
- Le bouton pause interrompt la lecture du média ; reprendre relance le même média.
- La navigation manuelle interrompt le média précédent.
- Si le navigateur bloque la lecture automatique avec son, cliquer une fois sur le contrôle Lecture du média.
- Les vidéos en boucle intégrée ne produisent pas d'événement `ended`, donc elles ne font pas avancer le diaporama.


## v0.6 — Nom de bibliothèque

Le nom de bibliothèque est modifiable dans la colonne gauche et conservé localement. Lors de l’export de la bibliothèque, une boîte de dialogue permet de confirmer ou modifier ce nom ; il devient le nom du fichier JSON et est conservé dans le contenu du projet. À l’import d’une bibliothèque de plusieurs diaporamas, le nom est restauré.


## v0.7 — Format repliable

La zone « Format et ajustement des médias » dans la colonne gauche est repliée au démarrage et s’ouvre au clic. Elle contient les réglages de ratio et d’ajustement, sans modifier le timer situé en dessous.


## v0.8 — Préférences

Un engrenage en haut de la colonne gauche regroupe les réglages de format et d'ajustement propres au diaporama actif, ainsi qu'une typographie commune facultative pour toutes les pages titre de la bibliothèque. Le choix de police n'efface pas les réglages individuels et peut être désactivé. Les préférences sont sauvegardées localement et dans l'export JSON de bibliothèque. Le bandeau d'avertissement pour les liens web est supprimé, mais le lien externe reste disponible.


## v0.9 — Panneau Import / Export

Les commandes de création, ajout de médias, importation, exportation et gestion des diaporamas se trouvent désormais dans une section « Import / Export », repliée par défaut en haut du panneau latéral. La liste des diaporamas dispose ainsi de davantage de hauteur.


## v0.9.1 — Importer bibliothèque

Le bouton « Importer bibliothèque » se trouve dans Import / Export, à côté de « Exporter bibliothèque ». Il ouvre un JSON de bibliothèque et ajoute ses diaporamas à la liste existante.


## 0.9.2 — Correction Préférences

Les réglages de format et d’ajustement sont désormais visibles directement dans le panneau de l’engrenage, sans second volet inaccessible.


## v0.9.3 — Identité

L’interface porte le titre « Iconocratie », avec la signature discrète « dsf©2026 » sous le titre. Le dépôt technique reste simple-diaporama.


## 0.9.4
- Minuterie et boucle déplacées dans Préférences (engrenage).
- Import / Export : Supprimer diapo remonte, Exporter bibliothèque est en dernière rangée.
- Raccourcis de vitesse inchangés ; vidéos et audios restent pilotés par leur fin effective.