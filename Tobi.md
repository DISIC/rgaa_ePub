# Produire un document EPUB avec Tobi

## Sommaire

<!-- MarkdownTOC depth="4" -->

- [Introduction](#introduction)
- [Présentation générale de Tobi](#pr%C3%A9sentation-g%C3%A9n%C3%A9rale-de-tobi)
- [Installation](#installation)
- [L'interface de Tobi](#linterface-de-tobi)
- [Importer un document DAISY ou EPUB](#importer-un-document-daisy-ou-epub)
- [Naviguer dans le texte](#naviguer-dans-le-texte)
- [Modifier du texte](#modifier-du-texte)
- [Modifier la structure d'un document](#modifier-la-structure-dun-document)
- [Créer, modifier et synchroniser une version audio](#cr%C3%A9er-modifier-et-synchroniser-une-version-audio)
	- [Écouter la version audio](#%C3%89couter-la-version-audio)
	- [Produire une version audio](#produire-une-version-audio)
		- [En utilisant un logiciel de voix de synthèse](#en-utilisant-un-logiciel-de-voix-de-synth%C3%A8se)
		- [En important des fichiers existants](#en-important-des-fichiers-existants)
		- [En l'enregistrant "en direct"](#en-lenregistrant-en-direct)
			- [Enregistrement simple](#enregistrement-simple)
			- [Enregistrement continu](#enregistrement-continu)
	- [Modifier la version audio](#modifier-la-version-audio)
- [Exporter le projet](#exporter-le-projet)
- [Avant de publier le document](#avant-de-publier-le-document)
- [Ressources externes et références](#ressources-externes-et-r%C3%A9f%C3%A9rences)
- [Licence](#licence)

<!-- /MarkdownTOC -->

## Introduction
Ce guide présente une solution permettant de produire des documents au format EPUB avec le logiciel Tobi. Il s'adresse aux personnes qui souhaitent produire des documents accessibles au format EPUB 3.0.1, en version audio avec texte synchronisé ou texte seulement. La production d'une version audio peut se baser sur des fichiers pré-enregistrés par un narrateur ou bien utiliser un logiciel de synthèse vocale. L'intérêt de Tobi réside dans la possibilité de synchroniser le texte et la version audio correspondante, afin d'obtenir des documents de haute qualité&nbsp;: cet usage peut s'avérer pertinent pour des ressources pérennes, pour lesquelles le fait d'avoir une narration au format audio constitue un facteur important d'acceptabilité pour le public cible. Il peut s'agir par exemple de documents à vocation culturelle (catalogue d'exposition), éducative (livre jeunesse), etc.

## Présentation générale de Tobi
Tobi est un logiciel développé par le consortium DAISY, distribué sous licences libres (LGPL et BSD). La dernière version peut être téléchargée sur le site du <a href="http://www.daisy.org/tobi/download" lang="en">projet Tobi</a>. Les éléments présentés dans ce guide se basent sur la version 2.5.0.0 (8 mai 2015).

Le but principal de Tobi est la production de documents combinant un texte et une version audio synchronisée de ce texte. Il peut également être utilisé pour produire des documents "texte uniquement". Tobi est en mesure de produire des documents accessibles dans les formats DAISY 3.0-2005 et EPUB 3.0.1. 

NB&nbsp;: Tobi est à distinguer du logiciel Obi (ce dernier permet de produire des documents "audio uniquement").

Tobi peut être utilisé&nbsp;:

* Pour générer un document multimédia audio avec texte synchronisé à partir d'un fichier XML DTBook (produit par Save as DAISY ou ODT2DAISY). La version audio peut provenir d'un enregistrement ou bien être générée par une voix de synthèse (Tobi est compatible avec le protocole SAPI 5 utilisée par la plupart des programmes de synthèse vocale sous Windows)&nbsp;;
* Pour modifier un document au format DAISY ou EPUB&nbsp;: corriger le texte, ajouter des description aux images, etc.

En comparaison de la production automatisée par DAISY Pipeline décrite dans le guide "produire des documents accessibles avec Save as DAISY, ODT2DAISY et DAISY Pipeline", Tobi offre une interface graphique simple pour&nbsp;:

* Produire des documents synchronisés avec un enregistrement audio en "voix humaine" alors que DAISY Pipeline gère uniquement la production en voix de synthèse&nbsp;;
* Réaliser divers traitement sur le flux audio (gestion du volume, de la vitesse, etc.) qu'il soit produit en voix humaine ou en voix de synthèse&nbsp;;
* Modifier avec une interface graphique simple un document produit automatiquement par DAISY Pipeline pour y apporter d'éventuels ajustements ou corrections.

Tobi sera donc considéré dans la plupart des cas comme pertinent en tant qu'outil pour des tâches de retouches de documents en voix de synthèse, ou bien comme un outil de création de document en "voix humaine".

## Installation
Pré-requis&nbsp;:

* Microsoft Windows XP (SP2 minimum, SP3 conseillé), Vista, 7, 8, 8.1 ou 10
* Framework Microsoft .NEt (version 3.5 ou 4.0)
* DirectX (version 9 ou supérieure)
* Au moins 1GO de mémoire vive

Pour installer Tobi&nbsp;:

* Télécharger la dernière version du logiciel
* Lancer le programme d'installation (celui-ci fonctionne indifféremment pour les systèmes 32 et 64 bits)
* Suivre les instructions de l'installeur. Celui-ci est conçu pour être accessible avec un lecteur d'écran.

La dernière version stable est la 1.9, disponible sur <a href="https://github.com/daisy-consortium/pipeline-assembly/releases/">Github</a>.

Pré-requis&nbsp;:

* DAISY Pipeline 2 fonctionne sous Windows, Linux et Mac OS X
* Java version 7 ou supérieure doit être installé sur le système


Tobi utilise le programme DAISY Pipeline pour ses fonctionnalités d'export au format EPUB. Pour installer DAISY Pipeline 2&nbsp;:

* Télécharger la version correspondant au système cible
* Sous Linux et Mac OS X, créer un répertoire et y décompresser l'archive ZIP téléchargée. Sous Windows, exécuter le programme téléchargé.

## L'interface de Tobi
Tobi est compatible avec les lecteurs d'écran JAWS (à partir de la version 9) et NVDA. L'interface fournit des fonctionnalités de zoom mettant en oeuvre des techniques de vectorisation qui permettent de conserver la qualité des éléments graphiques. L'interface utilisateur est composée de trois zones dont les dimensions peuvent être ajustées. Les couleurs peuvent être modifiées dans les préférences de l'application. Tobi est entièrement contrôlable au clavier.

L'interface de Tobi est constituée des éléments suivants&nbsp;:

* En haut, une barre de menu&nbsp;;
* En dessous, une barre d'outils qui propose de raccourcis pour réaliser les opérations courantes&nbsp;;
* À gauche de la fenêtre, le panneau de navigation qui permet de se déplacer rapidement à l'intérieur d'un document (par titre, numéro de page, etc.)&nbsp;;
* À droit du panneau de navigation, un panneau affichant le contenu du document&nbsp;;
* Sous les deux panneau précédents, se situe un panneau pour l'édition du contenu audio&nbsp;: il contient une barre d'outils et une zone permettant d'afficher le signal audio&nbsp;;
* En bas de la fenêtre se trouve une barre d'état qui permet d'afficher des informations sur le document en cours de traitement.

## Importer un document DAISY ou EPUB
Tobi n'agit pas directement sur des documents DAISY ou EPUB&nbsp;: il permet de travailler sur des projets, à partir desquels on peut exporter les données dans différents formats.

Pour modifier un document DAISY ou EPUB, il est nécessaire de l'importer dans Tobi afin de créer un projet. Les formats suivants peuvent être importés dans Tobi&nbsp;:

* XML DTBook (créé par Save as DAISY ou ODT2DAISY)
* DAISY 3 audio et texte (créé par DAISY Pipeline2)
* EPUB 3 texte
* EPUB 3 "texte uniquement" (créé par DAISY Pipeline 2)
* EPUB 3 audio et texte (créé par DAISY Pipeline 2)

Pour importer un document&nbsp;:
* Aller dans le menu File puis Import (Ctrl+I).
* Dans al boîte de dialogue, rechercher les fichiers avec une extension .xml (format XML DTBook), .opf (format DAISY 3) ou .epub (format  EPUB 3).
* Sélectionner le fichier souhaité et valider sur le bouton Open.
* Tobi affiche une boîte de dialogue permettant de choisir le format des fichiers audio qui seront utilisés pour le projet. On peut choisir le taux d'échantillonage (sampling rate: plus la valeur est élevée plus la qualité du son est bonne), si l'enregistrement doit être ou non en stéréo, ou choisir de préserver le format du document original s'il contient déjà une version audio en cochant "Preserve source format". NB&nbsp;: une fois choisies, les caractéristiques audio du projet ne pourront plus être modifiées.
* Valider sur OK pour finaliser l'importation.

Un projet Tobi peut être ouvert avec le menu File puis Open (Ctr+O) et sauvegardé avec File puis Save (Ctrl+S).

Lorsque l'importation d'un fichier XML DTBook ou DAISY 3 réussit, les données du document apparaissent dans la fenêtre principale (structure du document, contenu textuel et contenu audio si disponible).

Pour EPUB, Tobi créé autant de sous-projets que de fichiers HTML contenus dans le document. Le sous-projet à visualiser peut être sélectionné dans la boîte de dialogue "Project Spine" (Ctrl+U). Chaque sous-projet d'un projet EPUB est ensuite traité par Tobi comme un projet "standard" auquel s'appliquent les procédures décrites ci-dessous.

## Naviguer dans le texte
Plusieurs moyens sont à disposition pour naviguer à l'intérieur d'un document.

Le panneau de navigation (F8) permet de se déplacer en choisissant un titre, u numéro de pages, une image ou un signet.

Plusieurs commandes permettent de naviguer de manière séquentielle dans le document&nbsp;:
* "Select next phrase" (Ctrl+;) permet d'aller à l'élément suivant
* "Previous phrase" (Ctrl+,) permet d'aller à l'élément précédent
Un autre moyen de se positionner sur un élément du document est d'utilisation la structure arborescente affiché par Tobi&nbsp;: les éléments du documents sont présentés sous la forme d'une liste qui peut être dépliée en cliquant sur le triangle positionné après le nom des éléments puis le focus déplacé dans le document en validant sur l'élément souhaité.

Il est possible de rejoindre des éléments liés à partir du texte (par exemple, pour voir une note à partir d sa référence dans le texte)&nbsp;:
* La commande "folow link" (Ctrl+L) permet de se déplacer vers l'élément référence (note, cible d'une ancre, etc.)
* La commande "Go back to link" (Ctrl+Maj+L) permet de revenir à l'élément d'origine

Dans la structure arborescente du document, on peut faire apparaître ou cacher les éléments contenus dans un élément de niveau plus élevé&nbsp;:

* Dans la vue arborescente, sélectionner un élément en cliquant sur son nom (ou en validant sur ENTER, par exemple "doctitle"
* Utiliser la commande "Expand selection" (Ctrl+Maj+,) pour afficher les sous-éléments
* Utiliser la commande "Narrow selection" (Maj+Ctrl+.) pour cacher les sous-éléments

Enfin, il est possible de se déplacer vers un élément en connaissant un mot ou une phrase qu'il contient&nbsp;:

* Utiliser la commande Find (Ctrl+F)
* Saisir le texte recherché
* Utiliser les commandes "Find next" (F3) et "Find previous" (Maj+F3) pour trouver trouver les éléments suivants et précédents contenant le texte

Tobi permet de poser des signets à l'intérieur d'un document (ils apparaîtront dans le panneau de navigation). La commande "Toggle mark" (Ctrl+k permet de poser et de supprimer un signet&nbsp;: une action de cette commande pour poser un signet, deux pour supprimer un signet existant.

## Modifier du texte
On peut effectuer des modifications dans le texte d'un document importé dans Tobi, notamment pour lui apporter des corrections simples. Pour cela&nbsp;:

* Se déplacer sur l'élément à modifier
* Utiliser la commande "Edit" (F2, ou Alt+Clic avec la souris sur l'élément à éditer)
* Une boîte de dialogue permet de réaliser la modification souhaitée
* Valider sur OK
* Si l'élément à modifier contient plusieurs sous-éléments, Tobi ouvre autant de boîtes de dialogues que de sous-éléments

## Modifier la structure d'un document
Tobi permet de modifier la structure d'un document&nbsp;: il est souhaitable de maîtriser les notions de bases de XML et de connaître le langage XML DTBook ou HTML5 pour réaliser cette opération. Dans le cas contraire, il est conseillé de réaliser les modifications structurelles en amont, avec Microsoft Word ou LibreOffice par exemple, et de réimporter le document dans Tobi.

Les commandes permettant de modifier la structure d'un document sont situées dans le menu Text puis Edit structure&nbsp;:

* Delete fragment&nbsp;: supprime l'élément sélectionné
* Copy fragment&nbsp;: copie le contenu de l'élément sélectionné dans le presse-papier
* Cut fragment&nbsp;: supprime le contenu de l'élément sélectionné et le copie dans le presse-papier
* Paste fragment&nbsp;: colle le fragment de document stocké dans le presse-papier à l'endroit souhaité (en tant que premier sous-élément, en tant que dernier sous-élément, avant la position actuelle à la même profondeur dans l'arboresence, après la position actuelle à la même profondeur de l'arborescence).
* Insert page break&nbsp;: insérer un saut de page à la position actuelle
* Insert custom XML&nbsp;: permet d'insérer de nouveaux éléments XML

NB&nbsp;: les commandes de modifications décrites ci-dessus ne peuvent être exécutées qu'en l'absence de correspondance avec une version audio. Si les modifications réalisées donnent lieu à la production de code XML ou HTML5 non valide, le validateur intégré à Tobi produira un message d'avertissement.

## Créer, modifier et synchroniser une version audio
La version audio du document est affichée dans le panneau "Audio editor" de Tobi sous la forme d'un graphique qui permet de visualiser le signal&nbsp;: le temps en abscisse, l'amplitude en ordonnée. Il est possible de zommer pour augmenter ou diminuer la portion du signal visualisé.

### Écouter la version audio
Tobi permet d'écouter la version audio correspondant à tout ou partie d'un document&nbsp;: utiliser le bouton "Play" de la barre d'outils (Espace) pour écouter l'élément sélectionné et pour écouter tout le document, utiliser le bouton "Play audio advance" (Ctrl+Alt+Maj+Alt+Espace). La lecture peut être en mise en pause (Espace).

### Produire une version audio

#### En utilisant un logiciel de voix de synthèse
Tobi permet de produire une version en voix de synthèse à partir du texte d'un document&nbsp;:

* Pour le document entier, aller dans le menu Audio puis TTS audio (Entire document) (Maj+Ctrl+G)
* Pour l'élément sélectionné seulement, aller dans le menu Audio puis TTS audio (Selected text) (Ctrl+G) ou "Genrate TTs" dans la barre d'outils

Tobi synthétise le texte en utilisant la voix par défaut définie dans les paramètres du système. La voix peut toutefois être paramétrée (si d'autres programmes de synthèse vocale sont disponibles sur le système) en allant dans le menu Preferences puis Audio Settings.

#### En important des fichiers existants
On peut importer des fichiers audio pré-enregistrés dans un projet&nbsp;:

* Utiliser la fonction Import audio file dans la barre d'outils de l'éditeur audio (Shift+Ctrl+I)
* Dans la boîte de dialogue, sélectionner les fichiers à importer parmi les formats WAV, MP3, MP4 et AAC puis valider sur Open.

Le contenu des fichiers importés sera placé à la position du curseur audio ou bien remplacera la portion de contenu audio préalablement sélectionnée.  

#### En l'enregistrant "en direct"
Tobi permet de créer des enregistrements en utilisant le microphone connecté à la machine.

##### Enregistrement simple
Utiliser le bouton Start Recording de la barre d'outils de l'éditeur audio (Ctrl+R). La séquence enregistrée sera placée à la position courante du curseur ou bien remplacera une portion préalablement sélectionnée. L'enregistrement peut être stoppé en utilisant Ctrl+R, Ctrl+Espace ou ECHAP. Ce mode permet d'enregistrer un élément. 

##### Enregistrement continu
Il est possible d'enregistrer plusieurs éléments en continu, en appuyant sur une touche afin de gérer simplement la synchronisation de l'audio avec le texte. Pour cela, utiliser le bouton Stop Recording and Continue de la barre d'outils (Maj+Ctrl+R ou R si le focus est placé dans l'éditeur audio ou dans la barre d'état).

Dans ce mode, le niveau de détail de la synchronisation peut être modifié. Pour cela, il est nécessaire de paramétrer Tobi&nbsp;:

* Le paramètre "TextAudioSyncGranularity" permet de sélectionner le niveau de dé(ail (mot, phrase, etc.)
* Le paramètre "EnableTextSyncGranularity" permet de synchroniser au niveau de plus fin lorsqu'il vaut FALSE, ou bien d'utiliser le niveau définit par le paramètre précédent s'il vaut TRUE


### Modifier la version audio
Tobi offre un grand nombre de fonctionnalités pour modifier la version audio du document. Il est par exemple possible d'effectuer des copier-collers, de découper et reconstituer des séquences, etc.

Une fonctionnalité particulière utile permet de modifier la vitesse d'une séquence&nbsp;: il faut pour cela utiliser les fonctions Increase playback rate et Decrease playback rate (Ctrl+Flèche haute et Ctrl+Flèche basse).

## Exporter le projet
Une fois un projet finalisé, il est nécessaire de l'exporter vers le format désiré&nbsp;:

* Ouvrir l'éditeur de méta-données dans le menu Edit puis Edit metadata (F11) et renseigner les informations décrivant le document (titre, auteur, éditeur, producteur, etc.)
* Pour un enregistrement au format DAISY, ouvrir le module d'export en allant dans le menu File puis Export (Ctrl+E). Pour un enregistrement au format EPUB, ouvrir le module "Project Spine" (Ctrl+U) et valider sur le bouton "Export full EPUB".
* Choisir le taux d'échantillonnage, sélectionner l'option stéréo si nécessaire et l'option permettant de créer des fichiers audio au format MP3. Cocher les cases "Include/Merge image descriptions" et "Generate SMIL note references".
* Valider sur OK. 
* Sélectionner le répertoire où sera stocké le document exporté et valider.

NB&nbsp;: les projets créés à partir de documents XML DTBook ou DAISY peuvent être convertis au format EPUB si le programme DAISY Pipeline 2 est installé. (Des informations sur ce programme sont disponibles dans le guide "Produire un document EPUB avec Save as DAISY/ODT2DAISY et DAISY Pipeline 2".) Pour cela, aller dans le menu File puis DAISY to EPUB 3 (Maj+Ctrl+C) et sélectionner le document à convertir en choisissant un fichier portant l'extension .xml ou .opf. Si le bouton permettant d'ouvrir le module "Project spine" est grisé, c'est que Tobi n'a pas pu trouver le programme DAISY Pipeline2. Pour régler ce problème&nbsp;:

* Aller dans le menu File, puis choisir "DAISY to EPUB 3"&nbsp;;
* Tobi propose de choisir le chemin du DAISY Pipeline&nbsp;: il faut choisir le fichier pipeline.bat situé par défaut dans le dossier "C:\Program Files\DAISY Pipeline 2\daisy-pipeline\bin".


## Avant de publier le document

Les fichiers portant l'extension ".epub" peuvent être publiés en l'état. En revanche, la norme DAISY ne définissant pas de "conteneur", les projets DAISY sont exportés sous la forme d'un répertoire contenant de multiples fichiers&nbsp;: il est conseillé de créer une archive ZIP avec le contenu du répertoire proposé par Tobi.

## Ressources externes et références

* <a href="http://www.daisy.org/project/tobi" lang="en">Tobi project</a>
* <a href="http://www.daisy.org/tobi/tobi-user-reference-manual" lang="en">Tobi user reference manual</a>

## Licence
Ce document est la propriété du Secrétariat général à la modernisation de l'action publique français (SGMAP). Il est placé sous la [licence ouverte 1.0 ou ultérieure](http://wiki.data.gouv.fr/wiki/Licence_Ouverte_/_Open_Licence), équivalente à une licence <i lang="en">Creative Commons BY</i>. Pour indiquer la paternité, ajouter un lien vers la version originale du document disponible sur le [compte <span lang="en">Github</span> de la DInSIC](https://github.com/DISIC).
