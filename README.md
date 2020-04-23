# Jetson Nano Docker Setup

## Setup

Todos

1. sudo apt-get update && sudo apt-get upgrade
2. mkdir ~/.ssh && touch ~/.ssh/authorized_keys
3. add your public ssh key for easier login
4. install nvm
5. install docker-compose, tmux `sudo apt-get install docker-compose tmux`

```bash
git clone git@github.com:technologiestiftung/otc-jetson-nano-docker.git
cd otc-jetson-nano-docker
#(maybe run the odc install process outlined in the repo)
# see https://github.com/opendatacam/opendatacam/issues/184
git clone git@github.com:technologiestiftung/otc-mongo-replicaset-init.git
git clone git@github.com:technologiestiftung/otc-mongo-listener.git
git clone git@github.com:technologiestiftung/otc-toolkit.git
git clone git@github.com:technologiestiftung/otc-mongoku.git
# run the open-traffic-count-toolkit/docker-compose-builder
cd otc-toolkit/docker-compose-builder
npm run build
node dist/cli.ts -o ../../
# this will generate a
# docker-compose.yml
# and
# docker-compose.overrides.yml
sudo docker-compose up
```
