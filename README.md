# Traefik on Docker Swarm

Traefik deployed on Docker Swarm as a reverse proxy with SSL from Let's Encrypt.

## Getting Started

SSH into the swarm,

add files in repo to the root folder,
make sure there is an empty acme.json file in the traefik folder.
```
sudo touch /media/traefik/acme.json
sudo chmod 600 /media/traefik/acme.json
```

### Prerequisites

Docker Swarm with a Manager node and at least one Worker node


### Installing

deploy traefik
```
docker stack deploy --compose-file traefik-stack.yml traefik
```

remove traefik
```
docker stack rm traefik
```

deploy drewmakes
```
docker stack deploy --compose-file drewmakes-stack.yml drewmakes
```

remove drewmakes
```
docker stack rm drewmakes
```

Traefik Dashboard at port 8080
http://157.230.191.89:8080/dashboard/#/


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to

Maxence Henneron had most up to date version I could find, his also works with SSL
https://dev.to/maxencehenneron/automatic-dns-and-ssl-management-with-traefik-8cc

Jason Raimondi almost got SSL working for me, his github was a useful comparison.
https://jasonraimondi.com/posts/docker-compose-traefik-lets-encrypt/
https://github.com/jasonraimondi/docker-compose-traefik-example/tree/master/lets-encrypt-example

Mohamed Labouardy got me up and running without SSL
https://labouardy.com/docker-swarm-networking-and-dynamic-reverse-proxy/