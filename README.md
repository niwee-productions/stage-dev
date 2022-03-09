# Guide de stage

## L'environnement de travail
### Linux
Afin de travailler de manière rapide et agile, vous passerez sur Linux :
> :warning: **Vous aurez besoin d'une clé USB !**
* Télécharger <a href="https://www.deepin.org/en/download/" target="_blank">Deepin OS</a>
* Télécharger <a href="https://rufus.ie/en/" target="_blank">Rufus</a>
* Lancer Rufus
  * Choisir la clé d'installation
  * Choisir le fichier ISO téléchargé précédemment
  * Cliquer sur `start`

Si tout s'est bien passé, votre clé est maintenant bootable et vous pouvez lancer l'ordinateur dessus. Afin de booter sur la clé USB, vous avez plusieurs options: 
* Appuyer sur `F8` pour démarrer le bootloader
  * Séléctionner la clé USB (ZORIN OS
* Appuyer sur `F12`, `suppr` ou `F2` au lancement de l'ordinateur pour accéder au BIOS
  * Dans le bios, trouver les options de BOOT et déplacer la clé USB en tant que périphéique principal
  * Sauvegarder et redémarrer (`F10`)

Une fois sur Zorin OS, vous pouvez lancer l'installateur et choisir l'option pour installer à côté de Windows (au cas ou).

C'est terminé ! Vous avez maintenant un Linux installé sur votre machine.

### Docker
Afin d'obtenir un environnement de travail similaire aux environnements de production et pour ne pas installer plein de programmes, vous utiliserez Docker: 
* Installer <a href="https://docs.docker.com/engine/install/ubuntu/" target="_blank">Docker</a>
* Suivre les instructions de <a href="https://docs.docker.com/engine/install/linux-postinstall/" target="_blank">post-installation</a>
* Installer <a href="https://docs.docker.com/compose/install/#install-compose-on-linux-systems" target="_blank">Docker Compose</a>
* Redémarrer

## Les outils annexes
### Mise à jour du système
Pour mettre à jour votre Zorin OS, vous passerez par le terminal et utiliserez les commandes suivantes:
```bash
sudo apt update
sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt autoremove -y
```
> :warning: **Vous pouvez enchaîner des commandes avec `&&`**

### Git
Git est un logiciel de gestion de version. Il permet de suivre les modifications de votre code, de les différencier et de les partager.
Il doit être installé sur votre machine, si ce n'est pas le cas, entrez la commande suivante dans votre terminal :
```bash
sudo apt install git -y
```

Voici les commandes principales de Git :
```bash
git init   #initialise un dépôt Git
git status #affiche les modifications de votre code
git add .  #ajoute les modifications de votre code à votre dépôt
git commit #enregistre les modifications de votre code
git push   #envoie les modifications de votre code sur le dépôt distant
git pull   #récupère les modifications de votre code depuis le dépôt distant
```

> :warning: **Nous ne vérifierons/débuggerons pas du code non versionné !**

### VsCode
Visual Studio Code est un IDE pour le développement d'applications. Il permet de créer des applications web.

* Télécharger <a href="https://code.visualstudio.com/download" target="_blank">Visual Studio Code</a>

### Discord
Discord est un serveur de messagerie instantanée. Il permet de communiquer avec vos collègues, de discuter de projets et de partager des fichiers.

* Télécharger <a href="https://discordapp.com/download" target="_blank">Discord</a>
* Rejoindre le serveur <a href="https://discord.gg/xFVTvHSYF2" target="_blank">NiWee Productions</a>

## Construire votre première application avec Docker
Docker est un logiciel de gestion de conteneurs. Il permet de créer des conteneurs virtuels, de les configurer et de les déployer sur votre machine.

Pour plus d'ergonomie, nous vous avons préparé un environnement de déploiement agile: 
* <a href="https://github.com/niwee-productions/simple-php-fpm-mariadb-pma" target="_blank">Infrastructure PHP FPM / Mariadb / Nginx / PhpMyAdmin</a>

Toutes les instructions sont prêtes sur ce répo Github.

## NPM
NPM (Node Package Manager) vous permettra de récupérer toutes les dépendances nécessaires à votre application (Bootstrap, Jquery etc...).
Afin de l'installer, vous utiliserez Node Version Manager: 
```bash
sudo apt install curl -y # Installer curl (il doit déjà être installé)

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")" # Télécharger NVM

[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # Charge NVM 

source .profile # Recharger le fichier .profile
source .bashrc  # Recharger le fichier .bashrc

nvm install node # Installe NodeJS/NPM
```

Exemple d'utilisation de NPM: 
```bash
npm init                     # Créer un projet NPM
npm install --save bootstrap # Installer Bootstrap
npm install --save jquery    # Installer Jquery
npm install --global gulp    # Installer Gulp
```

Quelques précisions: 
Lors de la création d'un projet NPM, ce dernier crée le fichier `package.json` qui contient les informations de votre projet, dont ses dépendances.
> :warning: **Il est important de mettre le dossier `node_modules` dans un fichier `.gitignore` à la racine de votre projet GIT pour ne pas giter toutes les dépendences puisqu'elles sont lourdes et inutiles, on les installe avec une commande en local**

Pour installer vos dépendances après un `git clone` de votre projet, vous pouvez utiliser la commande suivante:
```bash
npm install
```

Pour mettre à jour les dépendances, vous pouvez utiliser la commande suivante:
```bash
npm update
npm update <nom de la dépendance>
```

### Pour aller plus loin
Vous pouvez utiliser des outils additionnels pour construire votre application comme :
* <a href="https://www.npmjs.com/package/gulp" target="_blank">Gulp</a>
* <a href="https://www.npmjs.com/package/grunt" target="_blank">Grunt</a>
* <a href="https://www.npmjs.com/package/bower" target="_blank">Bower</a>
* <a href="https://ohmyz.sh/" target="_blank">Oh My ZSH</a>
* <a href="https://opensource.com/article/18/8/what-how-makefile" target="_blank">Makefile</a>
* <a href="https://devhints.io/bash" target="_blank">Scripts Bash</a>
* <a href="https://www.valuebound.com/resources/blog/object-oriented-programming-concepts-php-part-1" target="_blank">Programmation Orientée Objet</a>

## C'est prêt ! 
N'hésitez pas à revenir sur ce guide en cas de besoin, et à suggérer des améliorations à ce dernier ! :wink:
