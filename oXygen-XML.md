# Corriger un document EPUB

## Sommaire

- [Introduction](#introduction)
- [Présentation de oXygen XML](#pr-sentation-de-oxygen-xml)
- [Installation de oXygen XML](#installation-de-oxygen-xml)
- [Édition d'un document EPUB&nbsp;: trois vues possibles](#dition-d-un-document-epub-nbsp-trois-vues-possibles)
- [Quelques exemples](#quelques-exemples)
    - [Modifier un paragraphe](#modifier-un-paragraphe)
    - [Ajouter une alternative à une image](#ajouter-une-alternative-une-image)
    - [Ajouter un code de langue](#ajouter-un-code-de-langue)
    - [Fusionner deux éléments](#fusionner-deux-l-ments)
- [Enregistrer le document](#enregistrer-le-document)
- [Licence](#licence)
## Introduction

Il arrive que des outils d'édition ne proposent pas toutes les fonctionnalités nécessaires pour produire un document EPUB complètement accessible (c'est par exemple le cas de Quark XPress qui ne permet pas d'ajouter une alternative à une image), ou bien que certaines informations soient perdues lors de l'export en EPUB. Ainsi, nous recommandons de réaliser une évaluation de conformité au regard du RGAA avant de mettre le document EPUB à disposition du public. EPUB 3 utilise les langages HTML, CSS et JavaScript&nbsp;: évaluer l'accessibilité d'un tel document consiste ainsi à vérifier l'ensemble des fichiers HTML le constituant en passer en revue les critères du rGAA (niveau AA au moins). Une telle évaluation ne fait pas l'objet de ce guide.

Le présent guide fournit des informations et méthodes permettant de corriger d'éventuelles erreurs identifiées lors de l'évaluation d'un document EPUB, avec l'outil oXygen XML Editor. Un fichier EPUB étant une archive ZIP contenant des fichiers HTML, il est également possible de réaliser de telles corrections manuellement, en désarchivant le document EPUB, en éditant les fichiers HTML souhaités et en les réarchivant au format ZIP. Toutefois, oXygen XML Editor offre une interface d'édition facile à utiliser, prend nativement en charge l'ouverture et l'enregistrement au format EPUB et permet de garantir la conformité et la cohérence du document EPUB ainsi corrigé au regard de la grammaire HTML et des spécifications du format.

## Présentation de oXygen XML

La suite oXygen XML propose des outils d'édition et de conversion de documents XML. Elle supporte le format EPUB (versions 2 et 3) ainsi que la grammaire XML DTBook (format produit par Save as DAISY et ODT2DAISY). Une version d'évaluation valable 30 jours est disponible gratuitement. oXygen XML est téléchargeable à l'adresse suivante&nbsp;: <a href="https://www.oxygenxml.com/download.html">https://www.oxygenxml.com/download.html</a>

## Installation de oXygen XML

* Télécharger le logiciel pour votre plateforme (Windows 32 ou 64 bits, Mac OS, Linux)
* Lancer le programme d'installation
* Lors du premier lancement du programme, demander une clé pour une version d'évaluation puis saisir cette clé pour activer le logiciel

## Édition d'un document EPUB&nbsp;: trois vues possibles

Pour ouvrir un document EPUB :

* Lancer le programme oXygen XML Editor.
* Dans le menu Fichier, valider sur Ouvrir, puis choisir le fichier EPUB à modifier
* Dans le panneau intitulé "Navigateur d'archive", choisir le dossier puis le fichier HTML à éditer

oXygen XML Editor propose alors trois vues différentes du code&nbsp;:

* La vue Texte, qui permet d'avoir une vision "brute" du code HTML&nbsp;: elle permet de visualiser le code comme le permet un éditeur "classique"&nbsp;;
* La vue Grille, qui permet d'afficher le document sous forme structurée et arborescente&nbsp;: les éléments fils et les attributs d'un élément sont affichés sous forme de colonnes et le contenu d'un élément peut être masqué ou affiché selon les besoins. Le contenu situé dans les éléments peut être modifié facilement sans avoir à interagir avec le balisage du document. La structure du document peut être modifiée via des opérations de type <span lang="en">"drag and drop"</span>.
* La vue Auteur, qui permet de visualiser le code HTML formaté en CSS, tel qu'il devra apparaître à l'utilisateur final et propose un éditeur de type WYSIWYG

## Quelques exemples
Dans ses différentes vues, oXygen XML Editor permet d'insérer, de supprimer, de fusionner et de modifier des éléments.

### Modifier un paragraphe

Il est possible de modifier le contenu d'un paragraphe&nbsp;:

* Se placer dans la vue Auteur&nbsp;;
* Se positionner dans le paragraphe à modifier et valider sur Entrée&nbsp;;
* Plusieurs possibilités sont alors proposer&nbsp;: scinder le paragraphe (qui va créer deux éléments "p" distincts), ou ajouter un élément (avec une liste de propositions d'éléments valides dans le contexte du paragraphe).

### Ajouter une alternative à une image

Pour ajouter ou modifier une alternative textuelle à une image, se placer dans la vue Auteur&nbsp;:

* Cliquer gauche sur l'image; elle apparaît en surbrillance dans le panneau Sommaire situé sous le panneau "Navigateur d'archive"&nbsp;;
* Dans le panneau Sommaire, cliquer droit sur l'image en surbrillance puis choisir "éditer les attributs";&nbsp;;
* Ajouter ou modifier le contenu de l'attribut "alt" avec le texte souhaité.
* Éléments du menu contextuel : Ajouter un enfant, insérer avant, insérer après, couper, copier coller coller avant coller après, supprime,r commenter, etc.

### Ajouter un code de langue

Pour ajouter un code de langue à un texte situé dans un paragraphe&nbsp;:

* Se placer en vue Auteur
* Sélectionner le texte auquel doit être attribué un code de langue
* Cliquer droit
* Choisir Refactorisation, puis Encadrer par des balises (Ctrl + E)
* Choisir "span" dans la liste de balises proposées
* Le texte apparaît entouré par le balises "span"&nbsp;: le sélectionner
* Cliquer droit et choisir "éditer les attributs"
* Dans le menu déroulant, choisir l'attribut "lang" et lui attribuer la valeur "en" par exemple

### Fusionner deux éléments

Dans la vue Texte&nbsp;:

* Sélectionner l'ensemble des éléments à fusionner (par exemple une succession de deux "span")
* Cliquer droit sur Refactorisation, puis choisir Concaténer les éléments

## Enregistrer le document

oXygen XML Editor assure la cohérence du balisage du document. Il n'est pas nécessaire de se soucier, lorsqu'on utilise les vues Grille et Auteur, de la gestion des balises ouvrantes et fermantes&nbsp;: elle est prise en charge par le logiciel.

## Licence
Ce document est la propriété du Secrétariat général à la modernisation de l'action publique français (SGMAP). Il est placé sous la [licence ouverte 1.0 ou ultérieure](http://wiki.data.gouv.fr/wiki/Licence_Ouverte_/_Open_Licence), équivalente à une licence <i lang="en">Creative Commons BY</i>. Pour indiquer la paternité, ajouter un lien vers la version originale du document disponible sur le [compte <span lang="en">Github</span> de la DInSIC](https://github.com/DISIC).
