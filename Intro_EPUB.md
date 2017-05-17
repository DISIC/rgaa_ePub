# Format EPUB&nbsp;: fonctionnalités et usages

## Sommaire

<!-- MarkdownTOC depth="4" -->

- [Introduction](#introduction)
- [Présentation du format EPUB](#pr%C3%A9sentation-du-format-epub)
	- [Introduction](#introduction-1)
	- [Usages](#usages)
	- [Fonctionnalités](#fonctionnalit%C3%A9s)
	- [Aspects techniques](#aspects-techniques)
- [Les avantages d'EPUB sur PDF](#les-avantages-depub-sur-pdf)
- [Vérification de l'accessibilité d'un document EPUB](#v%C3%A9rification-de-laccessibilit%C3%A9-dun-document-epub)
- [Ressources externes et références](#ressources-externes-et-r%C3%A9f%C3%A9rences)
- [Licence](#licence)

<!-- /MarkdownTOC -->


## Introduction
Ce guide présente brièvement le format EPUB. Il est destiné aux personnes qui souhaitent connaître les principaux usages et fonctionnalités de ce format ainsi que son intérêt dans la perspective de communiquer des documents accessibles.

## Présentation du format EPUB

### Introduction
EPUB est un format conçu et développé par l'<span lang="en">International Digital Publishing Forum (IDPF)</span>, un consortium regroupant des membres du secteur des industries culturelles et numériques, des associations, des bibliothèques, des universités, etc.

Nous nous référons ici à la version 3.0.1 des spécifications du format EPUB, publiées le 26 juin 2014. La version 3.0.1 apporte des modifications mineures à la version 3.0 (11 octobre 2011) et adoptée par l'<span lang="en">International Standards Organization (ISO)</span> sous la référence ISO/IEC TS 30135.

### Usages
EPUB est un format de publication électronique. Il est largement adopté par les éditeurs pour publier des livres numériques, mais peut être utilisé dans un contexte plus large, pour publier tout type de documents&nbsp;: rapports, brochures, magazines, supports de cours, etc.

EPUB est actuellement une alternative sérieuse à PDF. À titre d'exemple, l'ISO propose une grande partie de ses textes normatifs au format EPUB, en plus des versions PDF et imprimées.

Les documents au format EPUB peuvent être consultés sur une grande variété de matériels et de logiciels compatibles&nbsp;: liseuses, tablettes, téléphones, PC, etc.

Des documents EPUB peuvent être produits en utilisant des logiciels de traitement de texte usuels (Microsoft Word, LibreOffice Writer, etc.) après installation de <span lang="en">plug ins</span> prenant en charge la conversion vers ce format, des logiciels de publication (Adobe InDesign, Quark Xpress, etc.) ou bien en utilisant des outils intégrés dans des chaînes de traitement automatique des documents.

La version 3.0 d'EPUB est une refonte majeure du format qui a permis de prendre en compte de nombreuses exigences pour en faire un excellent candidat pour communiquer des documents accessibles&nbsp;: le consortium <span lang="en">Digital Accessible Information SYstem (DAISY)</span>, qui regroupe des organisations produisant et diffusant des contenus accessibles aux personnes handicapées, a en effet contribué largement à la réalisation des spécifications d'EPUB 3.0.

### Fonctionnalités
EPUB possède des fonctionnalités qui en font une alternative sérieuse à PDF pour publier des documents. Beaucoup de ses fonctionnalités ont un impact positif sur l'accessibilité et rendent la consultation des documents plus aisée qu'elle ne l'est lorsque d'autres formats sont utilisés, notamment PDF.

EPUB permet deux types d'affichage&nbsp;:

* Ajustable (<span lang="en">reflowable</span>), qui permet d'adapter le contenu à l'appareil de lecture (téléphone, tablette, PC, etc.) et aux besoins de l'utilisateur (choix de la taille et de la couleur des caractères par exemple)
* Fixe (<span lang="en">fixed layout</span>) qui permet de reproduire fidèlement des documents mettant en œuvre une mise en page complexe qu'il est souhaitable de conserver (les bandes dessinées par exemple)

EPUB est un format multimédia. En plus du texte, on peut y inclure du son et de la vidéo, et synchroniser ces différents médias ensemble. Il existe ainsi plusieurs "types" de documents EPUB&nbsp;: texte seul, audio seul, audio + texte, etc. La synchronisation est particulièrement utile pour l'accessibilité&nbsp;: elle permet par exemple à des personnes dyslexiques d'écouter un document lu par une synthèse vocale tout en visualisant les éléments prononcés grâce au surlignage du texte synchronisé avec la version audio.

EPUB définit une sémantique spécifique pour structurer des éléments textuels pour lesquels il n'existe pas de balises HTML5, comme les notes de bas de page, les numéros de page, les annotations, etc. Certains contenus peuvent être "passés" (<span lang="en">skippable contents</span>)&nbsp;: cela permet par exemple à un utilisateur aveugle de spécifier qu'il ne souhaitera pas entendre le numéros de page afin de ne pas interrompre le flot du texte.

Lors de la consultation, l'utilisateur peut poser des signets dans le document et a la possibilité de reprendre la lecture à l'endroit où il s'est arrêté.

Pour les documents audio enregistrés par un locuteur, EPUB impose aux appareils ou logiciels de lecture de mettre en œuvre des procédés permettant à l'utilisateur d'accélérer ou de ralentir le débit de la voix, sans altération du son (augmentation ou diminution de la hauteur). Pour rendre la consultation de livres audio en voix de synthèse optimale, il est possible pour un producteur de documents de définir la prononciation exacte d'un mot ou d'une expression en utilisant un alphabet phonétique.

Des polices peuvent être incluses dans un document EPUB. Cela permet par exemple de garantir la présence de polices qui facilitent la lecture pour les personnes dyslexiques.

Enfin, il est possible de créer des contenus interactifs tels que des questionnaires, et l'IDPF définit des extensions permettant de traiter des problématiques propres à des contenus spécifiques&nbsp;: index, dictionnaires, glossaires, documents scolaires (EDUPUB), etc.

### Aspects techniques
Un document EPUB porte l'extension <q>.epub</q>. C'est une archive ZIP contenant différents éléments, parmi lesquels on trouve notamment&nbsp;:

* Un <span lang="en">pakcage</span> qui inclut notamment des méta-données sur le documents
* Des fichiers HTML5 pour le texte, utilisant un profil défini par l'IDPF pour enrichir la sémantique du langage, éventuellement complété par des contenus utilisant un langage spécifique&nsbp;:
  * SSML (<span lang="en">Speech Synthesis Markup Language)</span>, utilisé dans le HTML5 pour personnaliser la prononciation par une synthèse vocale
  * MathML, utilisé dans le HTML5 pour les formules mathématiques
* Des fichiers images (SVG, JPEG, PNG, etc.)
* Des fichiers audio (MP3, OGG, WAVE, etc)
* Des fichiers vidéo (MP4, AAC, etc.)
* Des fichiers SMIL (<span lang="en">Synchronized Multimedia Integration Language</span>), servant à synchroniser les différents médias
* Des feuilles de styles CSS permettant de personnaliser la présentation du document
* Des scripts utilisant le langage JavaScript pour créer des contenus interactifs
* Des polices de caractères (WOFF et OpenType)

## Les avantages d'EPUB sur PDF
PDF est à l'origine un format destiné à l'impression. Il a évolué au fil du temps et permet aujourd'hui de contenir des informations qui permettent de préciser la sémantique des éléments textuels du document (les niveaux de titre par exemple).

Cependant, les fonctionnalités d'EPUB décrites précédemment et les moyens techniques mobilisés pour les mettre en oeuvre rendent ce format plus approprié que PDF dans la perspective de fournir une version accessible d'un document&nbsp;:

* Un document EPUB peut être consulté aisément sur des appareils différents (PC, tablettes, liseuses, téléphones, etc.) grâce au caractère ajustable du format alors qu'un document PDF est souvent lié à une taille d'affichage fixe (la page A4 par exemple)&nbsp;;
* Les outils permettant la restitution de document EPUB sont plus nombreux que ceux proposés pour PDF et sont souvent mieux supportés par les aides techniques utilisées par les personnes handicapées&nbsp;;
* La sémantique d'EPUB est plus riche.

## Vérification de l'accessibilité d'un document EPUB
EPUB se basant sur HTML5, CSS et JavaScript et pouvant intégrer des contenus multimédia, le RGAA&nbsp;3 est partiellement applicable pour vérifier l'accessibilité d'un document. Les thématiques suivantes peuvent ainsi être appliquées dans leur quasi-totalité&nbsp;: images, couleurs, multimédia, tableaux, liens, scripts, éléments obligatoires, structuration de l'information, présentation de l'information et consultation.


## Ressources externes et références
La version 3.0.1 des spécifications du format EPUB&nbsp;:

* <a href="http://www.idpf.org/epub/301/spec/epub-publications.html" lang="en">EPUB Publications 3.0.1</a>
* <a href="http://www.idpf.org/epub/301/spec/epub-contentdocs.html" lang="en">EPUB Content Documents 3.0.1</a>
* <a href="http://www.idpf.org/epub/301/spec/epub-ocf.html" lang="en">EPUB Open Container Format (OCF) 3.0.1</a>
* <a href="http://www.idpf.org/epub/301/spec/epub-mediaoverlays.html" lang="en">EPUB Media Overlays 3.0.1</a>

La Norme ISO basée sur EPUB 3.0&nbsp;:

* <a href="http://www.iso.org/iso/home/store/catalogue_ics/catalogue_detail_ics.htm?ics1=35&ics2=240&ics3=30&csnumber=53255" lang="en">ISO/IEC TS 30135-1:2014</a>

## Licence
Ce document est la propriété du Secrétariat général à la modernisation de l'action publique français (SGMAP). Il est placé sous la [licence ouverte 1.0 ou ultérieure](http://wiki.data.gouv.fr/wiki/Licence_Ouverte_/_Open_Licence), équivalente à une licence <i lang="en">Creative Commons BY</i>. Pour indiquer la paternité, ajouter un lien vers la version originale du document disponible sur le [compte <span lang="en">Github</span> de la DInSIC](https://github.com/DISIC).
