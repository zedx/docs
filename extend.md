# Extension de ZEDx

- [Introduction](#introduction)
- [Widget ou Module](#widget-vs-module)

<a name="introduction"></a>
## Introduction

ZEDx est rapide, léger et facile à utiliser. Afin de garantir qu'il reste ainsi, l'[équipe de développeurs] (https://github.com/zedx/zedx) réfléchit soigneusement à l'ajout de fonctionnalités au noyau du code ZEDx. Pourtant, les utilisateurs trouvent souvent la nécessité de greffer des fonctionnalités supplémentaires sur ZEDx pour répondre à leurs besoins, voilà pourquoi nous avons veillé à ce qu'ils puissent faire ce qu'ils veulent et nous avons créé ZEDx pour qu'il soit extensible aisément.

Afin de réaliser cette extensibilité, ZEDx a été construit avec des APIs riches et des points d'extension. Avec quelques connaissances en programmation, vous pouvez exploiter ces APIs pour ajouter à peu près toute fonction que vous voulez. Cette section de la documentation vise à vous enseigner comment ZEDx fonctionne, et comment utiliser les APIs afin que vous puissiez créer vos propres extensions.

<a name="widget-vs-module"></a>
## Widget ou Module

Eh bien, si vous voulez créer quelque chose qui n'a besoin d'aucune installation de base de données, d'itinéraires, de fournisseurs de services, mais juste quelle chose à afficher pour l'utilisateur final, alors vous voulez probablement créer un `widget` par exemple : `Wysiwig`, `annonces similaires`, `buttons de partage`

Un module a la possibilité de créer sa propre table de base de données, un uri personnalisé etc. par exemple un `Blog`.

> Vous pouvez également créer de nombreux widgets dans votre module.
