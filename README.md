# Iconocratie — v0.9.8

Application HTML autonome pour organiser et projeter une bibliothèque de diaporamas.

## Utilisation

Ouvrir `index.html` dans Firefox, Safari ou Chromium. Aucun serveur, compte ni installation requis. Les fichiers importés sont stockés localement dans le navigateur via IndexedDB. **Ne pas effacer les données du site/navigateur sans exporter la bibliothèque.** Pour transférer le travail sur un autre ordinateur, utiliser « Exporter bibliothèque » puis « Importer bibliothèque ».

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


## v0.9.5 — Enchaînement des diaporamas

Dans Préférences, activer **Enchaîner les diaporamas** pour poursuivre automatiquement la lecture avec le prochain diaporama non vide de la bibliothèque. **Boucler toute la bibliothèque** reprend au premier après le dernier. La boucle individuelle par diaporama est ignorée en mode enchaînement. Les titres et images utilisent le timer ; les vidéos et les sons avancent à la fin réelle du média.

L’ordre des diaporamas peut être changé par glisser-déposer de leur en-tête ou avec les petites flèches ↑ ↓. L’ordre est conservé localement et respecté à l’export JSON.

### v0.9.6 — Sélection multiple

Cliquer pour sélectionner une diapositive, ⌘/Ctrl-clic pour ajouter/retirer, Maj-clic pour sélectionner une plage dans un même diaporama. Glisser une diapositive sélectionnée déplace l’ensemble du groupe ; la cible peut être un autre diaporama, même replié (déposer sur son en-tête). L’ordre relatif est conservé.


## v0.9.7 — Annuler / Rétablir

Raccourcis clavier uniquement : `⌘ Z` pour annuler, `⌘ ⇧ Z` pour rétablir. Historique de 50 étapes pendant la session ; les raccourcis sont documentés en bas des Préférences.

## v0.9.8 — Bibliothèques

- **Nouvelle bibliothèque** crée une collection vide et la nomme.
- **Importer bibliothèque** remplace la bibliothèque courante après confirmation, sans créer de diaporama parasite.
- **Sauver bibliothèque** télécharge la bibliothèque au nom du dernier fichier utilisé ou sous le nom courant.
- **Exporter bibliothèque** propose de choisir un nouveau nom.
- **Importer un diapo** ajoute un diaporama au lieu de remplacer la bibliothèque.

Firefox télécharge le fichier JSON ; il ne peut pas écraser silencieusement un fichier déjà présent sur le disque.
