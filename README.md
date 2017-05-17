# Créer des documents accessibles au format EPUB

## Sommaire

- [Introduction](#introduction)
- [Les dispositifs techniques pour accéder aux contenus](#les-dispositifs-techniques-pour-accéder-aux-contenus)
- [Le RGAA et les documents en téléchargement](#le-rgaa-et-les-documents-en-téléchargement)
- [À qui s’adressent ces guides ?](#À-qui-sadressent-ces-guides)
- [Présentation des guides](#présentation-des-guides)
- [Licence](#licence)

## Introduction

La loi française n°2005-102 du 11 février 2005 pour l’égalité des droits et des chances, la participation et la citoyenneté des personnes handicapées, fait de l’accessibilité une exigence pour tous les services de communication publique en ligne de l’État, des collectivités territoriales et des établissements publics qui en dépendent.

Le RGAA (Référentiel Général d’Accessibilité pour les Administrations) a pour objectif de favoriser l’accessibilité des contenus diffusés sous forme numérique. En 2014, le RGAA a connu une refonte pour le mettre à jour et le rendre plus opérationnel. Les administrations françaises sont désormais tenues de se référer au RGAA 3.

Afin de répondre aux besoins de divers groupes et de différents contextes, trois niveaux de conformité ont été définis&nbsp;: A (le plus bas), AA et AAA. Le niveau légalement attendu est le niveau double A (AA). Les critères de succès associés au niveau AAA peuvent être pris en compte dans certains contextes, lorsque cela est possible et pertinent.

## Les dispositifs techniques pour accéder aux contenus

Un document est accessible s’il peut être consulté par n’importe quel utilisateur, quel que soit l’outil informatique dont il dispose. De plus en plus d’utilisateurs sont amenés à se servir de technologies d'assistance pour surmonter des barrières à l’accès aux contenus bureautiques ou web. Ces solutions techniques comprennent&nbsp;:

* Des aides logicielles (lecteurs d'écran, logiciels de reconnaissance vocale/dictée, etc.)&nbsp;;
* Des aides matérielles (souris adaptées, trackballs, afficheurs braille, etc.).

Les contenus et les applications doivent être compatibles avec ces diverses technologies d'assistance, leurs fonctionnalités et leurs usages.

## Le RGAA et les documents en téléchargement

Le RGAA s’applique à tout document ou application disponible en ligne&nbsp;: les sites Internet, Intranet et les applications web, mais aussi les contenus proposés en téléchargement.

Dans la thématique Consultation du RGAA, le critère 13.7 (niveau A) stipule que « chaque document bureautique en téléchargement possède, si nécessaire, une version accessible&nbsp;». La conformité à ce critère peut être atteinte notamment en fournissant une version HTML accessible ou en rendant accessible le document dans le format proposé en téléchargement.

Souvent, les documents bureautiques en téléchargement sont proposés au format PDF. Bien que des documents PDF puissent être conçus de sorte à être rendus accessibles, ce format n'est pas le plus approprié car il est souvent restitué avec difficultés par les technologies d'assistance. Le format EPUB peut ainsi constituer une alternative appréciable à PDF car, étant fortement basé sur HTML, il peut être mieux restitué&nbsp;: c'est ce qui a motivé la création des présentes ressources d'accompagnement.

## À qui s’adressent ces guides ?

Ces guides sont destinés à tout professionnel des services de l’État, des collectivités territoriales, des agences, des établissements publics, des entreprises publiques ou à toute personne souhaitant&nbsp;:

* Produire des documents accessibles&nbsp;;
* Améliorer l’accessibilité de documents existants&nbsp;;
* Fournir une alternative à PDF.

Ils s'adressent en particulier&nbsp;:

* Aux rédacteurs qui produisent des contenus actuellement mis à disposition au format PDF, et plus généralement, à toutes les personnes souhaitant communiquer au public ou en interne des documents accessibles dans un format standard autre que PDF&nbsp;;
* Aux concepteurs, développeurs d'outils de traitement automatique de documents électroniques&nbsp;;
* Aux chefs de projets intégrant des outils de Gestion Électronique des Documents (GED).

## Présentation des guides

En premier lieu, le guide [EPUB, fonctionnalités et usages](./Intro_EPUB.md) est proposé&nbsp;: il présente brièvement les principaux usages du format (consultation, production), ses principales fonctionnalités, ses aspects techniques et son intérêt dans le contexte de la production de documents accessibles.

À partir de documents produits avec Microsoft Word et LibreOffice Writer, le guide [Produire un document EPUB avec Save as DAISY/ODT2DAISY et DAISY Pipeline 2](./Daisy.md) propose de créer des documents accessibles au format EPUB, avec des <span lang="en">plug-ins</span> intégrés à Word et à LibreOffice ainsi qu'avec des outils en ligne de commande pouvant être intégrés dans des processus d'automatisation de production automatique. Ces guides supposent d'utiliser comme source un document Word ou LibreOffice accessible&nbsp;: la DInSIC propose des [guides pour créer des documents bureautiques accessibles](https://github.com/DISIC/guides-documents_bureautiques_accessibles) qui peuvent être consultés préalablement.

Trois guides sont ensuite proposés, présentant chacun les procédures détaillées et illustrées à mettre en oeuvre pour créer des documents EPUB accessibles avec les logiciels suivants&nbsp;:

* Adobe InDesign&nbsp;: [ODT - 623Ko](./Adobe-InDesign.odt), [PDF - 894Ko](./Adobe-InDesign.pdf)
* Quark XPress&nbsp;: [ODT - 394Ko](./Quark-XPress.odt), [PDF - 598Ko](./Quark-XPress.pdf)
* iBook Author&nbsp;: [ODT - 473Ko](./Apple-iBooks_Author.odt), [PDF - 648Ko](./Apple-iBooks_Author.pdf)

(À noter&nbsp;: il est recommandé d'ouvrir les fichiers proposés au format ODT avec LibreOffice&nbsp;; la restitution avec d'autres logiciels pourrait être dégradée.)

Le guide [Produire un document EPUB avec Tobi](./Tobi.md) présente ensuite une méthode permettant de produire des documents EPUB synchronisant une version texte et une version audio (pré-enregistrée par un narrateur ou générée à la volée par une voix de synthèse).

Enfin, le guide [Corriger un document EPUB](./oXygen-XML.md) présente brièvement une méthode permettant d'apporter des corrections simples (ajout d'alternatives textuelles, ajout de changement de langue, etc.) à un document EPUB produit par les outils décrits précédemment, au cas où le fichier exporté ne serait pas totalement conforme aux recommandations du RGAA.

## Licence
L'ensemble des documents constituant les présentes ressources sont la propriété du Secrétariat général à la modernisation de l'action publique français (SGMAP). Ils sont placés sous la [licence ouverte 1.0 ou ultérieure](https://www.etalab.gouv.fr/licence-ouverte-open-licence), équivalente à une licence <i lang="en">Creative Commons BY</i>. Pour indiquer la paternité, ajouter un lien vers la version originale du document disponible sur le [compte <span lang="en">Github</span> de la DInSIC](https://github.com/DISIC).
