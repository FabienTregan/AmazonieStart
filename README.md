# Création du package de démarrage

## Installation de FireFox

La borne est lancée sur une version portable de Firefox (lancement sans installation nécessaire).
A l'heure actuelle, la derniere version disponible est la 64.

 * Télécharger et décompresser [FireFox Portable version 64](https://portableapps.com/apps/internet/firefox_portable)
 * Supprimer le sous répertoire `FirefoxPortable\App\Firefox`* (resp. `FirefoxPortable\App\Firefox64`) si la version 32bit (resp. 64bit) n'est pas utilisée.
 * Renommer le répertoire `FirefoxPortable` en `BorneMusee`

## Désactivation des mises à jour

Pour éviter les messages et redémarrages intempestifs, les mises à jour sont désactivées.

/!\ Cette solution n'est envisageable pour des raisons de sécurité que dans la mesure où
le utilisateurs n'ont accès qu'à la borne et pas un accès libre à internet. Celà implique
par exemple qu'un firewall empêche le navigateur d'accéder au réseau si elle y est connecté,
ou que le clavier ne soit pas accessible.

La désactivation des mises à jour se faire en créant un fichier `policies.json` dans un répertoire nommé `distribution` placé dans le même répertoire que `firefox.exe`

 * Copier le répertoire `distribution` dans les répertoires `BorneMusee\App\Firefox` et/ou `BorneMusee\App\Firefox64`

## Permettre le passage automatique en plein ecran

 * Executer depuis le répertoire `BorneMusee` la commande `App\Firefox64\Firefox.exe -profile ".\ProfileBorne" -foreground`
 * Aller à l'adresse `about:config`
 * Mettre `full-screen-api.allow-trusted-requests-only` à `false`

## Désactivation de la barre d'adresse et de la barre d'outils et permettre le passageen mode plein écran automatique.

Ceci est fait grace au fichier `chrome\userChrome.css`, et à la ligne `user_pref("full-screen-api.allow-trusted-requests-only", false);` dans le fichier `prefs.js` à créer dans le répertoire du profile utilisateur:

 * Copier le répertoire `ProfileBorne` dans `BorneMusee`

## Script de démarrage

 * Copier le fichier `demarrage borne.bat` dans le répertoire `FirefoxPortable`
 * Editer ce fichier pour lancer la version 32bit si nécessaire

