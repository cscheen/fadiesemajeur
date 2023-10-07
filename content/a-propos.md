---
title: "À propos"
date: "2023-05-24"
lastmod: "2023-10-07"
description: "Présentation du site"
images: ["/img/fisdur.png"]
type: "page"
draft: false
---

{{< contents >}}

Une sente à chamois qui s’évanouit aux premiers frimas d’automne, un chemin
de traverse balisé, des investigations menées avec minutie, selon les règles
de l’art en lexicographie, ou encore les vicissitudes d’un moteur de
recherche, vous ont indiqué les coordonnées de ce recoin de la toile qui
héberge mon site ou *blog* personnel.

Soyez la bienvenue ou le bienvenu.

Sur ce site, je publie de temps en temps des billets consacrés à des sujets
qui me tiennent à cœur --- musique, science, philosophie,&nbsp;etc.

La
[page d’accueil](/)
propose la liste rétrochronologique des billets publiés.
Le menu, dans la barre de navigation, permet d’accéder à
l’[index thématique](/sujets/)
et à
l’[index onomastique](/noms/).
On y trouve encore la liste des
[projets](/projets/)
auxquels je me consacre en amateur --- ils concernent le pianiste Vladimir
Sofronitsky et sont hébergés dans deux dépôts distincts de ma
[page](https://github.com/cscheen)
sur
[GitHub](https://github.com/).
Enfin, le menu permet aussi de prendre connaissance des
[mentions légales](/mentions-legales/),
en particulier les éléments d’identification, la politique de
confidentialité, la protection des données à caractère personnel et les
mentions de droit d’auteur.

## Une brève histoire des lieux

Le défrichage de ce lopin de terre a commencé le
{{< fulldate "2014-10-14" >}}, avec un système de gestion de contenu (en
anglais *Content Management System*, CMS) fondé sur le langage de
programmation
[PHP](https://www.php.net/),
pour les pages dynamiques, et sur le système de gestion de bases de données
relationnelles
[MySQL](https://www.mysql.com/).
À cette époque, le site tout entier était consacré à la musique classique ou
{{< quote "musique savante occidentale" >}}&#8239;; son nom, *fa dièse
majeur*, évoquait la surabondance de grandes œuvres de musique composées
dans la tonalité en question.

Vers le début de l’année&nbsp;2017, le château de cartes du CMS, alourdi par
la base de données et fragilisé par le langage de *script*, s’est effondré,
victime d’un acte de la flibuste.
Il faut encore avouer que les idiosyncrasies du nouvel éditeur de texte du
CMS, une suggestion bien vite transformée en un impératif, n’invitaient
guère à l’interaction, surtout si l’on a ses habitudes avec
[GNU Emacs](https://www.gnu.org/software/emacs/)
et que l’on ne souhaite pas en changer.
Ce fut l’aube d’une période de jachère, émaillée de quelques tentatives de
sauvetage.

Les choses seraient sans doute restées en l’état sans la découverte d’un
générateur de site statique (en anglais *Static Site Generator*, SSG).
Sources dans un format non propriétaire, liberté de choix de l’éditeur de
texte, absence de langage de *script*&#8239;[^JavaScript] et de base de
données, infrastructure par construction plus résistante du point de vue de
la sécurité, simplicité de la procédure pour le respect du
{{< abbr "RGPD" "Règlement général sur la protection des données" >}} en
Europe, contrôle des sources grâce à un logiciel de gestion de versions (en
anglais *Source-Control Management*, SCM), dépôt de celles-ci sur un service
d’hébergement et de gestion de développement, déploiement *via* un service
conçu pour l’hébergement de sites statiques --- tout cela semblait idéal.
Seule la location du nom de domaine demeurait un passage obligé.

En outre, certains affirment aujourd’hui que
{{< quote "le *blog* est mort" >}}, siphonné par les réseaux sociaux, à
l’instar des groupes sur Usenet jadis et ensuite des forums de
discussion&nbsp;: raison de plus pour reprendre un travail intempestif.

## Une architecture roide et linéaire

D’ordinaire, un *blog* est une liste rétrochronologique de billets
représentés selon une ou plusieurs hiérarchies --- séries, catégories,
étiquettes,&nbsp;etc.
Celui-ci ne fait pas exception&nbsp;: le
[classement](/)
rétrochronologique y est conservé et, bien que l’on n’y trouve aucune série,
catégorie ou étiquette,
l’[index thématique](/sujets/)
et
l’[index onomastique](/noms/)
utilisent le principe des taxinomies pour une telle représentation
hiérarchique.
Le classement et la catégorisation fleurent bon l’esprit de système et le
naphtalène&#8239;; on aurait peine à y trouver quoi que ce soit d’organique.
En fermant les yeux, on imaginerait presque Procuste qui prépare sa scie et
son marteau.
En outre, un billet publié ressemble à une idée à peine arrivée à maturité.
Au lieu de la laisser vivre sa vie, l’ordre rétrochronologique la condamne à
la submersion par le flot de billets ultérieurs, avec lesquels elle
n’entretient peut-être que des relations à la marge.
Les idées nouvelles effaceraient les anciennes, sans doute avec l’espoir de
ne pas être elles-mêmes englouties&nbsp;: midi s’arrêterait sur le pas de
leur porte...
Une topologie se fait encore attendre&#8239;[^Obsidian] qui serait plus
adaptée aux processus de la réflexion.

## Une texture plus fluide et souple

Les pensées ne se développent en effet pas le long de lignes dépourvues de
recoupements, de ramifications, de synapses en quelque sorte, paramétrées
par un temps irréversible et inexorable, et donc indifférent.
En&nbsp;1817, un poème de Goethe&#8239;[^Goethe] suggère pour ce problème
une réponse, en évoquant la
{{< quote "Forme marquée d’un sceau et qui, en vivant, évolue" >}}.

> *Δαιμων, Dämon*
>
> *Wie an dem Tag, der dich der Welt verliehen,<br>
> Die Sonne stand zum Gruße der Planeten,<br>
> Bist alsobald und fort und fort gediehen<br>
> Nach dem Gesetz, wonach du angetreten.<br>
> So mußt du sein, dir kannst du nicht entfliehen,<br>
> So sagten schon Sibyllen, so Propheten;<br>
> Und keine Zeit und keine Macht zerstückelt<br>
> Geprägte Form, die lebend sich entwickelt.*

> Δαιμων, le démon
>
> Tel était, en ce jour qui t’a donné au monde,<br>
> Le soleil quand eut lieu le salut des planètes.<br>
> Tel aussitôt tu t’es développé sans cesse<br>
> Au gré de cette loi qui réglait ta venue.<br>
> Il te faut être ainsi, tu ne peux pas te fuir,<br>
> C’est ce qu’ont dit déjà sibylles et prophètes&#8239;;<br>
> Et nul temps, nul pouvoir ne morcelle la forme<br>
> Marquée d’un sceau et qui, en vivant, évolue.

Rien n’empêche de réécrire d’anciens billets, en mentionnant par exemple la
date de leur modification la plus récente.
De même, rien n’empêche de revenir sur d’anciennes idées lors de l’écriture
de nouveaux billets, à la manière d’un camaïeu voire d’un palimpseste.
En tout cas, on peut s’efforcer de faire honneur à la fois au sceau et à
l’évolution.

## Crédits informatiques

Le site est produit au moyen de logiciels libres.
Le tableau suivant indique leur fonction et mentionne leur principale
ressource sur la toile ainsi que le nom de leur auteur.

Fonction | Logiciel | Auteur
---------|----------|-------
Syntaxe de mise en forme | [Markdown][] | [Gruber][]
Gestion de versions | [Git][] | [Torvalds][], [Hamano][]
Édition de texte | [GNU Emacs][] | [Stallman][]
Mode majeur d’édition | [markdown-mode][] | [Blevins][]
Générateur de site statique | [Hugo][] | [Francia][], [Pedersen][]
Infrastructure logicielle CSS | [Bulma][] | [Thomas][]
Suppression de code inutilisé | [PurgeCSS][] | [Full Human][]
Transformation CSS avec JS | [PostCSS][] | [Sitnik][]
Environnement d’exécution JS | [Node.js][] | [Dahl][]
Gestionnaire de paquets | [npm][] | [Schlueter][]
Police de caractères (texte) | [Ysabeau][] | [Thalmann][]
Police d’icônes (symboles) | [Feather Icons][] | [Bemis][]
Production de polices .woff | [sfnt2woff-zopfli][] | [Stein][]
Production de polices .woff2 | [woff2_compress][] | [Google][]
Gestion de projet | [GNU Make][] | [Feldman][]
Langage de *script* | [GNU Awk][] | [Aho][], [Weinberger][], [Kernighan][]
Recherche de motifs | [GNU Grep][] | [Thompson][]

[Markdown]: <https://daringfireball.net/projects/markdown/>
[Git]: <https://git-scm.com/>
[GNU Emacs]: <https://www.gnu.org/software/emacs/>
[markdown-mode]: <https://jblevins.org/projects/markdown-mode/>
[Hugo]: <https://gohugo.io/>
[Bulma]: <https://bulma.io/>
[PurgeCSS]: <https://purgecss.com/>
[PostCSS]: <https://postcss.org/>
[Node.js]: <https://nodejs.org/>
[npm]: <https://www.npmjs.com/>
[Ysabeau]: <https://github.com/CatharsisFonts/Ysabeau>
[Feather Icons]: <https://feathericons.com/>
[sfnt2woff-zopfli]: <https://github.com/bramstein/sfnt2woff-zopfli>
[woff2_compress]: <https://github.com/google/woff2>
[GNU Make]: <https://www.gnu.org/software/make/>
[GNU Awk]: <https://www.gnu.org/software/gawk/>
[GNU Grep]: <https://www.gnu.org/software/grep/>

[Gruber]: <https://daringfireball.net/>
[Torvalds]: <https://www.linuxfoundation.org/>
[Hamano]: <https://github.com/gitster>
[Stallman]: <https://stallman.org/>
[Blevins]: <https://jblevins.org/>
[Francia]: <https://spf13.com/>
[Pedersen]: <https://bep.is/en/>
[Thomas]: <https://jgthms.com/>
[Full Human]: <https://full-human.com/>
[Sitnik]: <https://sitnik.ru/en/>
[Dahl]: <https://tinyclouds.org/>
[Schlueter]: <https://izs.me/>
[Thalmann]: <https://www.myfonts.com/collections/catharsis-fonts-foundry>
[Bemis]: <https://colebemis.com/>
[Stein]: <http://www.bramstein.com/>
[Google]: <https://opensource.google/>
[Feldman]: <https://www.schmidtfutures.com/person/stuart-feldman/>
[Aho]: <http://www.cs.columbia.edu/~aho/>
[Weinberger]: <https://en.wikipedia.org/wiki/Peter_J._Weinberger>
[Kernighan]: <https://www.cs.princeton.edu/~bwk/>
[Thompson]: <https://en.wikipedia.org/wiki/Ken_Thompson>

Le code n’utilise pas de thème au sens propre, mais la mise en pages doit
beaucoup à une série de
[billets](https://pakstech.com/series/blog-with-hugo/)
de *blog* rédigés par
[Janne Kemppainen](https://pakstech.com/)
à propos de Hugo.
Les sources sont hébergées dans un
[dépôt](https://github.com/cscheen/fadiesemajeur)
de ma
[page](https://github.com/cscheen)
sur
[GitHub](https://github.com/)
et le site est déployé grâce à
[Netlify](https://www.netlify.com/).
Un
[billet](/billets/colophon/)
se consacre au fonctionnement du site {{< quote "sous le capot" >}}.

[^JavaScript]: Il reste un fragment de code JavaScript
({{< abbr "JS" "JavaScript" >}}, 704&nbsp;octets avant sa
{{< quote "minification" >}}) qui se charge de la présentation d’une partie
de la barre de navigation pour les périphériques d’affichage de taille
restreinte&#8239;; on le trouve dans la
[documentation](https://bulma.io/documentation/components/navbar/)
de l’infrastructure logicielle {{< abbr "CSS" "Cascading Style Sheets" >}}
Bulma.

[^Obsidian]: Elle a peut-être même déjà été proposée, sous la forme des
graphes de connaissance, des cartes de contenu et des
{{< quote "liens retours" >}} (en anglais *backlinks*) d’un système comme
[Obsidian](https://obsidian.md/),
permettant l’élaboration non linéaire d’un {{< quote "second cerveau" >}} ou
{{< quote "jardin numérique" >}}.
Un déploiement de ce système est possible grâce à
[Quartz](https://quartz.jzhao.xyz/).
Je ne suis cependant pas encore certain que des billets de *blog*, au sens
classique du terme, y soient à leur place&nbsp;: il me semble que l’accent y
est plutôt placé sur ce qui prend forme.

[^Goethe]: {{< smallcaps "Goethe" >}} (Johann Wolfgang von), *Urworte.
Orphisch* ({{< quote "Paroles originelles. Orphique" >}}), 1817.
Traduction en français par {{< smallcaps "Lefebvre" >}} (Jean-Pierre),
*Anthologie bilingue de la poésie allemande*.
Éditions Gallimard, Bibliothèque de la Pléiade, Paris, France, 1995.
