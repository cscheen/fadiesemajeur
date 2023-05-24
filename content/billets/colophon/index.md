---
title: "Colophon"
date: "2023-05-24T07:43:15+02:00"
lastmod: "2023-05-24T07:43:15+02:00"
description: "Fonctionnement du site"
sujets: ["Informatique"]
noms: [
    "Bemis (Cole)",
    "Betz (Zachary Wade)",
    "Kemppainen (Janne)",
    "Modi (Kaushal)",
    "Thalmann (Christian)"
]
images: ["/img/fisdur.png"]
type: "billets"
draft: false
---

{{< contents >}}

## Éléments de base

Le site est produit par le générateur de site statique
[Hugo](https://gohugo.io/)
avec l’infrastructure logicielle {{< abbr "CSS" "Cascading Style Sheets" >}}
[Bulma](https://bulma.io/).
Les sources du contenu, dans le sous-répertoire `content/`, sont des
fichiers de texte simples qui obéissent à la syntaxe de mise en forme
[Markdown](https://daringfireball.net/projects/markdown/).
Toutes les sources, à l’exception de celles qui sont renseignées dans le
fichier d’exclusion `.gitignore` (à la racine du dépôt), sont placées sous
le contrôle du système de gestion de versions
[Git](https://git-scm.com/).

La mise en pages, sans thème au sens propre, doit beaucoup à une série de
[billets](https://pakstech.com/series/blog-with-hugo/)
de *blog* rédigés par
[Janne Kemppainen](https://pakstech.com/)
à propos de Hugo.
Le partiel en charge de la production des {{< quote "liens retours" >}} (en
anglais
[*backlinks*](https://help.obsidian.md/Plugins/Backlinks))
est dû à
[Kaushal Modi](https://scripter.co/parsing-backlinks-in-hugo/).
Ce partiel cherche les {{< quote "liens retours" >}} éventuels vers le
billet courant dans toutes les autres pages du site, et est lui-même appelé
depuis le modèle (en anglais
[*template*](https://gohugo.io/templates/single-page-templates/))
utilisé par tous les billets du site&nbsp;: il est donc susceptible d’une
inflation combinatoire en&nbsp;*O*(*n*<sup>2</sup>), où&nbsp;*n* représente
le nombre de pages du site.
(Voir tableau suivant.)

Nom de fichier | Fonction | Chemin d’accès
---------------|----------|---------------
`backlinks.html` | Recherche des liens retours | `layouts/partials/`
`single.html` | Modélisation de chaque billet | `layouts/billets/`

La police de caractères est
[Ysabeau](https://github.com/CatharsisFonts/Ysabeau)&#8239;[^Ysabeau]
et celle d’icônes est
[Feather Icons](https://feathericons.com/)&#8239;[^Feather].
Toutes deux sont disponibles au format {{< abbr "TTF" "TrueType" >}}&nbsp;:
il est nécessaire de les produire au format
{{< abbr "WOFF" "Web Open Font Format" >}}, ce qui est assuré par les
programmes
[`sfnt2woff-zopfli`](https://github.com/bramstein/sfnt2woff-zopfli)
(norme&nbsp;1.0) et
[`woff2_compress`](https://github.com/google/woff2)
(norme&nbsp;2.0).

## Suppression du code CSS inutilisé

Le site n’utilise pas toutes les classes CSS de Bulma.
Un
[billet](https://zwbetz.com/how-to-use-purgecss-with-hugo/)
de *blog*, rédigé par
[Zachary Wade Betz](https://zwbetz.com/),
indique comment employer
[PurgeCSS](https://purgecss.com/)
afin de supprimer le code inutilisé et de servir ainsi un fichier CSS aussi
réduit que possible.
Outre Hugo, le seul prérequis est l’environnement d’exécution JavaScript
[Node.js](https://nodejs.org/en)
et son gestionnaire de paquets
[npm](https://www.npmjs.com/).

Du côté de Hugo, il suffit d’agir sur la section de configuration de
`build`, afin de créer un fichier `hugo_stats.json` (à la racine du dépôt)
qui mentionne tous les `tags`, `classes` et `ids` contenus dans les modèles
`*.html` du projet.
Voici l’extrait correspondant dans le fichier de configuration `hugo.toml`
(à la racine du dépôt)&nbsp;:

{{< highlight toml >}}
[build]
    writeStats = true
{{< /highlight >}}

Du côté de Node.js, il faut installer les trois extensions requises, à
partir de la racine du dépôt&nbsp;:

{{< highlight bash >}}
$ npm install postcss postcss-cli @fullhuman/postcss-purgecss
{{< /highlight >}}

Il faut ensuite configurer PurgeCSS au moyen du fichier `postcss.config.js`
(à la racine du dépôt).
Attention&nbsp;: le code JavaScript en charge de la présentation d’une
partie de la barre de navigation, pour les périphériques d’affichage de
taille restreinte, ajoute son propre élément (une classe), à savoir
`is-active`, qui doit donc se trouver dans la `safelist` du fichier de
configuration de PurgeCSS.

On peut enfin revenir à Hugo, et en particulier au partiel
`layouts/partials/head.html` qui contient les lignes suivantes pour la
production du fichier CSS final, avec une {{< quote "empreinte digitale" >}}
et une vérification de l’intégrité de la ressource&nbsp;:

{{< highlight html >}}
{{ $options := (dict "outputStyle" "compressed" "includePaths" (slice "bulma/sass")) -}}
{{ $style := resources.Get "style.scss" | resources.ToCSS $options | resources.PostCSS -}}
{{ if hugo.IsProduction -}}
    {{ $style = $style | resources.Fingerprint "sha256" | resources.PostProcess -}}
{{ end -}}
<link rel="stylesheet" type="text/css" href="{{ $style.RelPermalink }}" integrity="{{ $style.Data.Integrity }}">
{{< /highlight >}}

(Dans le sous-répertoire `assets/`, le fichier `style.scss` importe en effet
`bulma/bulma.sass`, entre autres opérations.)

## Gestion du projet

Le fichier `Makefile` (à la racine du dépôt) permet de gérer le projet grâce
au programme
[GNU Make](https://www.gnu.org/software/make/).
Les cibles sont les suivantes&nbsp;:
*   `help`.
Affiche toutes les cibles du `Makefile` avec leurs messages d’aide
respectifs.
Cette cible invoque elle-même les programmes
[GNU Awk](https://www.gnu.org/software/gawk/)
et
[GNU Grep](https://www.gnu.org/software/grep/),
qui doivent donc être présents sur le système&#8239;;
*   `ginit`.
Initialise un dépôt Git dans le répertoire de travail, si ce n’est pas déjà
le cas.
Si le dépôt est déjà initialisé, affiche son statut Git&#8239;;
*   `depend`.
Installe PostCSS, PurgeCSS et leurs dépendances avec npm, comme indiqué
[plus haut](#suppression-du-code-css-inutilisé)&#8239;;
*   `clean`.
Supprime les sous-répertoires `public/` et `resources/` ainsi que leurs
contenus éventuels&#8239;;
*   `fonts`.
Produit les polices de caractères aux formats {{< fullcaps "WOFF" >}} et
{{< fullcaps "WOFF2" >}}, à partir des sources dans le sous-répertoire
`ttf/`.
Utilise `sfnt2woff-zopfli` pour la norme&nbsp;1.0 et `woff2_compress` pour
la norme&nbsp;2.0.
Recopie les licences pour Ysabeau et Feather.
Les programmes `sfnt2woff-zopfli` et `woff2_compress` doivent donc être
présents sur le système&#8239;;
*   `build` (dépend des cibles `ginit` et `clean`).
Construit le site et le publie dans le sous-répertoire `public/`&#8239;;
*   `serve` (cible par défaut&#8239;; dépend des cibles `ginit` et `clean`).
Construit le site et le sert grâce au serveur *Web* intégré de Hugo.

## Déploiement sur Netlify

Les sources du site se trouvent dans un
[dépôt](https://github.com/cscheen/fadiesemajeur)
sur
[GitHub](https://github.com/).
Le site est déployé sur
[Netlify](https://www.netlify.com/)
*via* le fichier de configuration `netlify.toml` (à la racine du dépôt).

[^Ysabeau]: Une police de caractères sans empattements, dite *antique* ou
*linéale* (en anglais *sans-serif*), conçue par Christian
[Thalmann](https://www.myfonts.com/collections/catharsis-fonts-foundry)
et inspirée par
[Garamond](https://fr.wikipedia.org/wiki/Garamond_(police_d'écriture)).

[^Feather]: En fait, la police d’icônes est obtenue à partir d’une
collection d’icônes au format {{< abbr "SVG" "Scalable Vector Graphics" >}},
dessinées par Cole
[Bemis](https://colebemis.com/).
Pour le format TrueType (TTF), on peut utiliser
[Fontello](https://fontello.com/)
ou
[IcoMoon](https://icomoon.io/).
