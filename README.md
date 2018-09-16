# traefik-multisites

Conditions préalables:

* Un VPS sous Ubuntu 16.04.
* Un utilisateur non-root, compatible avec sudo.
* Une installation fonctionnelle de Docker

# Etape N°1. Installer Docker
Pour installer Docker proprement, utilisez cette commande :

    sudo curl -sS https://get.docker.com/ | sh
  
Cette commande va mettre à jour votre système et installer la dernière version stable de Docker.

Autoriser Docker et le démarrer :

    sudo systemctl enable docker
    sudo systemctl start docker

# Etape N°2. Installer Traefik via docker-compose

Tout d'abord, vous devez installer docker-compose si vous ne l'avez pas déjà fait.

    curl -L https://github.com/docker/compose/releases/download/1.16.1/docker-compose-`uname -s`-`uname -m` > ./docker-compose
    sudo mv ./docker-compose /usr/bin/docker-compose
    sudo chmod +x /usr/bin/docker-compose

Pour exécuter Traefik en utilisant docker-compose :

git clone 

On va modifier le fichier docker-compose.yml avec vos propres informations (domaine) :

    sudo nano docker-compose.yml
    
Puis on modifie le fichier traefik.toml avec les informations propres (domaine et adresse mail):

    sudo nano traefik.toml
    
On crée ensuite le répertoire et le fichier nécessaire pour les certificats TLS :
    
    touch /root/acme.json
    chmod 600 /root/acme.json

# Etape 3. Lancement

On crée le réseau traefik pour Docker : 

    docker network create traefik
    
Et depuis le répertoire cloné on lance : 
    
    docker-compose up -d 
    
Résultat : 

<img src="https://github.com/gabrielsagnard/traefik-multisites/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-09-16%20a%CC%80%2009.11.09.png" width="500px"></img>
