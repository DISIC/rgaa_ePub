# Produire un document EPUB avec Save as DAISY/ODT2DAISY et DAISY Pipeline 2]

## Sommaire

- [Introduction](#introduction)
- [Présentation générale de la chaîne proposée](#pr-sentation-g-n-rale-de-la-cha-ne-propos-e)
- [Mise en oeuvre](#mise-en-oeuvre)
- [Save as DAISY](#save-as-daisy)
- [Installation](#installation)
- [ Utilisation](#utilisation)
- [ Sous Microsoft Word](#sous-microsoft-word)
- [En ligne de commande](#en-ligne-de-commande)
- [ODT2DAISY](#odt2daisy)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Avec LibreOffice Writer](#avec-libreoffice-writer)
- [En ligne de commande](#en-ligne-de-commande)
- [DAISY Pipeline 2](#daisy-pipeline-2)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Ressources externes et références](#ressources-externes-et-r-f-rences)
- [Licence](#licence)

## Introduction
Ce guide présente une solution permettant de produire des documents au format EPUB à partir de documents au format OpenXML (Microsoft Word) ou OpenDocument (LibreOffice Writer). Il propose des techniques permettant de produire des documents "à l'unité" grâce à des interfaces graphiques simples, ou par lot en utilisant des outils en ligne de commande.

## Présentation générale de la chaîne proposée
Les logiciels de traitement de texte Microsoft Word et LibreOffice Writer permettent de produire des documents accessibles. Ils utilisent des formats basés sur XML&nbsp;: OpenXML pour Microsoft Word (portant l'extension ".docx") et ODF (OpenDocument) pour LibreOffice Writer (portant l'extension ".odt"). OpenXML et ODF peuvent être convertis au format EPUB en passant par un format intermédiaire conçu par le consortium DAISY (Digital Accessible Information SYstem) nommé XML DTBook ou DAISY-XML.

La solution proposée pour produire un document EPUB à partir d'un document OpenXML ou ODF compte ainsi trois étapes&nbsp;:

* La création d'un document accessible sous Microsoft Word ou LibreOffice Writer&nbsp;;
* La conversion de ce document au format XML DTBook avec Save as DAISY pour Microsoft Word ou ODT2DAISY pour LibreOffice Writer&nbsp;;
* La conversion du document XML DTBook au format EPUB 3.0.1 avec DAISY Pipeline 2.

## Mise en oeuvre

### Save as DAISY
Save as DAISY est un logiciel libre développé conjointement par Microsoft, Sonata Software et le consortium DAISY.
La dernière version (2.5.5.1 à ce jour) est disponible sur <a href="http://www.daisy.org/project/save-as-daisy-ms-word-add-in">le site du consortium DAISY</a> où l'on peut télécharger des versions binaires pour Windows 32bits et 64bits. À noter qu'une version distincte est disponible pour Office 2013. Il existe une version spécifique fonctionnant "<a href="https://sourceforge.net/projects/openxml-daisy/files/DAISYTranslator%20Word%20Add-Ins/Release%202.1.1/DaisyTranslator_CommandLine_24March2009.zip/download">en ligne de commande</a>. Le code source est téléchargeable sur <a href="http://sourceforge.net/projects/openxml-daisy/">le dépôt Sourceforge du projet</a>. 

Le but de ce programme est de convertir un document au format OpenXML vers un document XML DTBook conforme à la norme DAISY 2005.
Deux versions sont disponibles~: un <span lang="en">plug in</span> pour Microsoft Word qui ajoute à l'interface un élément "Save as DAISY" permettant de convertir le fichier en cours d'édition, et une version en ligne de commande utilisable en mode <span lang="en">batch</span>, permettant de convertir plusieurs fichiers en un seul appel au programme.

#### Installation
Pré-requis&nbsp;:

* Microsoft Windows XP ou version supérieure (NB&nbsp;: Save as DAISY ne fonctionne pas avec Microsoft Office pour Mac OS X)
* Microsoft Office 2007 ou version supérieure pour Windows (NB&nbsp;: Save as DAISY ne fonctionne pas avec Microsoft Office pour Mac OS X)
* Microsoft .NET Framework 3.0 (disponible sur le site de Microsoft)

Pour installer Save as DAISY&nsbp;:

* Installer Microsoft .NET Framework 3.0 s'il ne l'est pas déjà&nbsp;;
* Télécharger la version de Save as DAISY appropriée pour votre système d'exploitation et votre version de Microsoft Office&nbsp;;
* Exécuter le programme téléchargé et suivre les instructions fournies par le programme d'installation&nbsp;;
* Si le <span lang="en">plug-in</span> Save as DAISY n'apparaît pas dans l'onglet <span lang="en">Accessibility</span> du ruban de Microsoft Word, il peut être nécessaire de relancer le processus d'installation de Microsoft Office (insérer le CD ou relancer l'installation par réseau), puis de sélectionner l'élément permettant d'ajouter de nouvelles options à la version déjà présente sur le système (le nom varie suivant les versions de Microsoft Office) et d'activer le "prise en charge de programmabilité .NET" lors du choix des options à ajouter.


#### Utilisation
Avant de pouvoir convertir un fichier avec Save as DAISY, il faut que celui-ci soit au format OpenXML (extension ".docx"). Si ce n'est pas le cas, par exemple lors de l'édition d'un fichier créé avec une ancienne version de Microsoft Word, il faut au préalable sauvegarder le document au format ".docx" (cliquer sur "Enregistrer sous", puis sélectionner le format Microsoft Word). Une fois ceci fait, le document peut être converti au format XML DTBook.

##### Sous Microsoft Word
Dans Microsoft Word, la marche à suivre pour convertir un document OpenXML en XML DTBook est la suivante&nbsp;:

* L’installation de Save as DAISY ajoute dans le "ruban" un onglet nommé <span lang="en">"Accessibility"</span>. Rendez vous dans cet onglet, cliquer sur le bouton <span lang="en">Import</span> pour vous assurer de conserver la structuration du document&nbsp;;
* Cliquer ensuite sur "SaveAsDAISY" et sélectionner <span lang="en">DAISY XML (from Single docx)</span>. (NB : Le bouton SaveAsDAISY est également accessible à partir du bouton Fichier. Pour cela, sous Aide, cliquer sur Compléments)&nbsp;;
* La boîte de dialogue <span lang="en">DAISY Translator</span> s’affiche&nbsp;;
* Si les propriétés du document n’ont pas été renseignées préalablement, ajouter le titre, l'auteur et l'éditeur&nbsp;;
* Après avoir précisé la destination du fichier, cliquer sur le bouton <span lang="en">Translate</span>&nbsp;;
* La conversion est alors initiée&nbsp;: si elle réussit, un fichier portant l'extension ".xml" est créé, éventuellement accompagné par des fichier images. Il arrive qu'une conversion échoue à cause d'erreurs de validation du code XML DTBook généré&nbsp;: dans ce cas, la seule solution est de le corriger manuellement ou grâce à l'éditeur oXygen XML Editor.

##### En ligne de commande

Télécharger et installer la version spécifique pour la ligne de commande mentionnée ci-dessus. Un répertoire nommé "DaisyTranslator" est créé dans le répertoire "Program files" (le nom peut varier selon le système d'exploitation). Ce répertoire contient un fichier DaisyConverter.exe, dont la syntaxe est la suivante&nbsp;:
```
  DaisyConverter.exe /I chemin_source [/O chemin_destination] [BATCH-DOCX] [/REPORT fichier_rapport] [/TITLE] [/CREATOR] [/PUBLISHER] [/UID]
```
Où les options signifient&nbsp;:

* /I Nom du fichier ou du répertoire source à convertir. Ex: D:\rep ou D:\rep\src.docx
* /O Nom du fichier ou répertoire de destination de la conversion (ex: D:\rep ou D:\rep\dest.xml)
* /BATCH-DOCX Réaliser une conversion par lot de tous les fichiers contenus dans le répertoire. À noter que les fichiers seront écrasés dans le répertoire de destination.
* /REPORT Nom d'un rapport au format texte qui contiendra le détail de(s) conversion(s) réalisée(s)
* /TITLE Titre du document
* /CREATOR Nom de l'auteur du document
* /PUBLISHER Nom de l'éditeur du document
* /UID Identifiant unique du document

Exemple&nbsp;:
```
  DaisyConverter.exe /I c:\tmp\test.docx /O c:\tmp\essai.xml
```

### ODT2DAISY
ODT2DAISY est un logiciel libre fonctionnant avec LibreOffice Writer qui permet de convertir des documents au format ODF (extension ".odt") vers le format XML DTBook. Il se présente comme une extension à LibreOffice ajoutant des éléments à l'interface graphique et comme un outil pouvant être utilisé en ligne de commande.

La dernière version (2.1.2 à ce jour) est disponible sur <a href="http://odt2daisy.sourceforge.net/downloads/">le dépôt Sourceforge</a>.

#### Installation

Pré-requis&nbsp;:

* ODT2DAISY est compatible avec Windows, Mac OS X et Linux
* LibreOffice à partir de la version 3.
* Java à partir de la version 5


Deux versions sont disponibles&nbsp;: une version fonctionnant sous LibreOffice Writer, l'autre en ligne de commande.

Pour installer la version pour LibreOffice Writer&nbsp;:

* Sur le dépôt Sourceforge, télécharger le fichier correspondant au système d'exploitation cible dans le répertoire de la <a href="http://sourceforge.net/projects/odt2daisy/files/2.1.2/">version 2.1.2</a>&nbsp;;
* Décompresser l'archive ZIP téléchargée&nbsp;;
* Ouvrir LibreOffice Writer&nbsp;;
* Aller dans le menu "Outils" puis "Gestionnaire d'extensions"&nbsp;;
* Cliquer sur "Ajouter..." et sélectionner le fichier de ODT2DAISY portant l'extension ".oxt" qui se trouve dans l'archive ZIP téléchargée&nbsp;;
* Redémarrer LibreOffice Writer.

L'installation a réussi si vous trouvez des boutons intitulés "Export direct en DAISY XML" et "Export en full DAISY" dans la barre d'outils de LibreOffice Writer.

Pour installer la version en ligne de commande&nbsp;:

* Sur le site de Sourceforge, télécharger l'archive <a href="http://sourceforge.net/projects/odt2daisy/files/2.1/odt2daisy-2.1.0.zip/download">odt2daisy-2.1.0.zip</a>
* Décompresser l'archive ZIP téléchargée&nbsp;;

#### Utilisation

##### Avec LibreOffice Writer
ATTENTION&nbsp;: avec les nouvelles version de LibreOffice, des bugs ont été constatés empêchant la réalisation de la démarche mentionnée ci-dessous. Nous l'indiquons à titre indicatif, et conseillons toutefois d'utiliser la version en ligne de commande présentée à la section suivante. Des correctifs sont en cours de préparation pour résoudre les problèmes avec les nouvelles version de LibreOffice.

Dans LibreOffice Writer, la marche à suivre pour convertir un document ODF en XML DTBook est la suivante&nbsp;:

* Dans le document à convertir, renseigner préalablement les méta-données (titre, auteur, éditeur, etc.) dans le menu "Fichier", puis "Propriétés"&nbsp;;
* L’installation de ODT2DAISY ajoute un bouton XML (Export direct au format DAISY XML) à la barre d'outils de LibreOffice Writer&nbsp;: cliquer sur ce bouton. (Il est également possible d'y accéder à partir du menu "Fichier" puis "Exporter au format DAISY XML")&nbsp;;
* Une boîte de dialogue "Enregistrer sous" s’ouvre alors. Après avoir indiqué le nom du fichier converti et précisé sa destination, cliquer sur le bouton "Enregistrer"&nbsp;;
* La conversion est alors initiée&nbsp;: si elle réussit, un fichier portant l'extension ".xml" est créé, éventuellement accompagné par des fichier images&nbsp;;

##### En ligne de commande
L'archive d'ODT2DAISY contient le fichier "odt2daisy.jar" qui doit être exécuté avec Java.

Pour convertir un fichier, utiliser la commande suivante&nbsp;:
```
  java -jar \chemin_odt2daisy\odt2daisy.jar -in \chemin_source\nom_source.odt -out \chemin_dest\nom_dest.xml
```

Les paramètres "-in" et "-out" sont obligatoirement et contiennent respectivement le nom du fichier source et celui de destination.

Des paramètres facultatifs peuvent être ajoutés&nbsp;:

* -pic Nom du répertoire qui contiendra les images (défaut&nbsp;: "images")
* -page Conserve la numérotation des pages du document source dans le fichier de destination. Ceci peut ralentir significativement le processus de conversion.
* -css Génère une feuille de style qui peut être utilisée dans un éditeur XML pour visualiser le fichier XML DTBook.
* -u Permet de préciser un identifiant unique
* -t Permet de préciser le titre
* -c Permet de préciser le nom de l'auteur
* -p Permet de préciser le nom de l'éditeur.
* -pr Permet de préciser le nom du producteur

Pour traiter des fichiers volumineux, il peut être nécessaire d'augmenter la taille de la mémoire et de la pile allouée à Java en ajoutant les paramètres "-Xmx1024m -Xss32m" à la ligne de commande&nbsp;:
```
  java -Xmx1024m -Xss32m -jar \chemin\odt2daisy.jar ...
```

Exemple&nbsp;:
```
  java -Xmx1024m -Xss32m -jar c:\tmp\odt2daisy.jar -in c:\tmp\test.odt -out c:\tmp\test.xml
```


### DAISY Pipeline 2
DAISY Pipeline 2 est une "boîte à outils" développée par le consortium DAISY contenant plusieurs convertisseurs, notamment pour produire des documents au format EPUB. Nous utilisons l'un d'entre eux pour convertir les documents au format XML DTBook produits par Save as DAISY ou ODT2DAISY au format EPUB 3.0.1.

#### Installation
La dernière version stable est la 1.9, disponible sur <a href="https://github.com/daisy-consortium/pipeline-assembly/releases/">Github</a>.

Pré-requis&nbsp;:

* DAISY Pipeline 2 fonctionne sous Windows, Linux et Mac OS X
* Java version 7 ou supérieure doit être installé sur le système


Pour installer DAISY Pipeline 2&nbsp,:

* Télécharger la version correspondant au système cible
* Sous Linux et Mac OS X, créer un répertoire et y décompresser l'archive ZIP téléchargée. Sous Windows, exécuter le programme téléchargé.

#### Utilisation

DAISY Pipeline 2 fonctionne actuellement en ligne de commande uniquement (une interface graphique est en cours de développement au moment de la rédaction de ce guide).

Pour convertir un document au format XML DTBook en EPUB, la marche à suivre est la suivante&nbsp;:

* Se placer dans le répertoire "cli" situé le répertoire créé pour installer DAISY Pipeline 2. Sous Windows, DAISY Pipeline 2 est installé dans "Prgram files\Daisy-Pipeline". (Il est aussi possible d'ajouter le répertoire "cli" à la variable <span lang="en">path</span> du système d'exploitation.
* Utiliser la commande suivante pour lancer une conversion&nbsp;: ```dp2 dtbook-to-epub3 --source fichier_source.xml --output repertoire_de_destination```

Des paramètres peuvent être ajoutés, notamment&nbsp;:

* --x-language Permet de préciser la langue du document de destination (utiliser un code du type "fr-FR")
* --x-audio Lorsque la valeur de ce paramètre est <span lang="en">"true"</span>, le document EPUB produit contient une version audio en voix de synthèse synchronisée avec le texte. Par défaut, ce paramètre vaut <span lang="en">"false"</span>&nbsp;: c'est alors une version "texte uniquement" qui est produite. DAISY Pipeline 2 détecte automatiquement les synthétiseurs disponibles sur le système utilisé.

Lorsque la conversion aboutit, le répertoire de destination contient un fichier portant l'extension ".epub"&nbsp;: ce document est conforme à la spécification EPUB 3.0.1&nbsp;: il s'agit soit d'un EPUB "texte uniquement", soit d'un EPUB "texte + audio en voix de synthèse" selon les options choisies.

Avertissement&nbsp;: la distribution de documents en voix de synthèse est parfois soumise à des restrictions liées aux licences de synthétiseurs vocaux. Il est donc recommandé de consulter avec attention le contrat de licence accompagnant le programme de synthèse vocale utilisé préalablement à toute communication d'un document contenant des données produites par le programme en question.

## Ressources externes et références

* <a href="http://www.daisy.org/project/save-as-daisy-ms-word-add-in" lang="en">Save as DAISY - MS Word Add-In</a>
* <a href="http://odt2daisy.sourceforge.net/" lang="en">odt2daisy | OpenDocument To DAISY DTBook</a>
* <a href="http://www.daisy.org/pipeline2">DAISY Pipeline 2 (page principale))</a>
* <a href="https://github.com/daisy/pipeline-assembly">DAISY Pipeline 2 (dépôt GitHub)</a>


## Licence
Ce document est la propriété du Secrétariat général à la modernisation de l'action publique français (SGMAP). Il est placé sous la [licence ouverte 1.0 ou ultérieure](http://wiki.data.gouv.fr/wiki/Licence_Ouverte_/_Open_Licence), équivalente à une licence <i lang="en">Creative Commons BY</i>. Pour indiquer la paternité, ajouter un lien vers la version originale du document disponible sur le [compte <span lang="en">Github</span> de la DInSIC](https://github.com/DISIC).
