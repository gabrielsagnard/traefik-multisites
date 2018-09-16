# traefik-multisites

Conditions préalables:

Un VPS sous Ubuntu 16.04.
Un utilisateur non-root, compatible avec sudo.
Une installation fonctionnelle de Docker

Etape N°1. Installer Docker
Pour installer Docker proprement, utilisez cette commande :

$ sudo curl -sS https://get.docker.com/ | sh
Cette commande va mettre à jour votre système et installer la dernière version stable de Docker.

Autoriser Docker et le démarrer :

sudo systemctl enable docker
sudo systemctl start docker

Etape N°2. Installer Traefik via docker-compose

Tout d'abord, vous devez installer docker-compose si vous ne l'avez pas déjà fait.

curl -L https://github.com/docker/compose/releases/download/1.16.1/docker-compose-`uname -s`-`uname -m` > ./docker-compose
sudo mv ./docker-compose /usr/bin/docker-compose
sudo chmod +x /usr/bin/docker-compose

Pour exécuter Traefik en utilisant docker-compose :
