# Barcampdockersolutin

1. Docker-Machine installieren und Verbindung zum Server herstellen: https://docs.docker.com/machine/
2. DNS-Records von Domain auf Server linken (A & AAAA Records)
3. In der Datei traefik.toml ADDYOUREMAILHERE durch die eigene ersetzen
4. Via Terminal in diesen Ordner wechseln
5. Den Zielserver für docker-machine/compose im Terminal setzen:

```
eval "$(docker-machine env YOURTARGETMACHINENAME)"
```

6. Traefik hochschubsen(Traefik müsste danach schon auf der Domain antworten):

```
docker-compose -f docker-compose.traefik.yaml up -d
```

7. Portainer hochschubsen(YOURDOMAIN durch Zieldomain ersetzen)

```
KK_DOMAINS='YOURDOMAIN' docker-compose -f docker-compose.portainer.yaml up -d
```

8. Wenn einer Meckert muss evtl. das Netzwerk von Hand auf dem Host(SSH) gesetzt werden

```
docker network create reverseproxy
```