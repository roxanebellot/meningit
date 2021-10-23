---
layout: default
title: status
parent: La base
nav_order: 10
---

# `status` : Visualiser l'état

0. TOC
{:toc}

## Utilisation

```shell
$ git status
Sur la branche main
Votre branche est à jour avec 'origin/main'.

rien à valider, la copie de travail est propre
```

`status` est nos yeux : elle nous donne l'état du repo sans avoir aucun impact dessus.

On voit le **nom de la branche courante** et l'état par rapport au **remote**

## Comprendre

### Branche

```shell
$ git status
Sur la branche main
```

La branche courante. Voir **branch** et **checkout**

### Votre branche est à jour/en retard/en avance

```shell
$ git status
Sur la branche main
Votre branche est à jour avec 'origin/main'.
```

Le dernier commit de la branche est le même sur la copie locale et sur la remote (`origin`).
Voir **remote**, **pull/push**

### Rien à valider

```shell
$ git status
Sur la branche main
Votre branche est à jour avec 'origin/main'.

rien à valider, la copie de travail est propre
```

Aucune modification en cours les modifications sont validées et poussées, tout va bien.

C'est l'état qu'on cherche à rejoindre le plus souvent possible.

### Modifications qui ne seront pas validées

```shell
$ git status

Modifications qui ne seront pas validées :
  (utilisez "git add <fichier>..." pour mettre à jour ce qui sera validé)
  (utilisez "git restore <fichier>..." pour annuler les modifications dans le répertoire de travail)
    modifié :         meningit_site/index.md
```

Voir **add** et **commit**

### Fichiers non suivis

```shell
$ git status
Fichiers non suivis:
  (utilisez "git add <fichier>..." pour inclure dans ce qui sera validé)
    meningit_site/about.md
    meningit_site/base/
```

voir **add**

### Aucune modification n'a été ajoutée à la validation

```shell
$ git status
aucune modification n'a été ajoutée à la validation (utilisez "git add" ou "git commit -a")
```

Voir **add** et **commit**

## Options

### Autre branche

Par défault, on montre l'état de la branche courante, mais on peut choisir de voir l'état d'une autre branche sans s'y déplacer

```shell
$ git status --branch main
Sur la branche dev
rien à valider, la copie de travail est propre
```

`Sur la branche` affiche toujours la branche courante, mais l'état qui suit est bien l'état de la branche demandée !

Voir aussi **checkout**

### Affichage court ou long

Par défault, l'affichage est `git status --long` un affichage long. On peut demander son inverse, l'affichage court avec `-s` ou `--short`

```shell
$ git status
 M meningit_site/index.md
?? meningit_site/about.md
?? meningit_site/base/
```

## Problèmes courants

```shell
$ git status
fatal: ni ceci ni aucun de ses répertoires parents n'est un dépôt git : .git
```

Le dossier dans lequel la commande `status` a été lancé n'est pas un repo git.

Solutions :

- vérifiez le dossier dans lequel vous vous trouvez et déplacez-vous dans le dossier voulu avec `cd`
- le dossier est le bon mais le repo git n'a pas été créé, voir init/clone
