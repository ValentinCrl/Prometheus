# Observabilité avec Prometheus, Graphana et Thanos

# Exercie01

## Objectif

Lancer un seul conteneur Prometheus, accéder à l'interface web sur le port 9090 et vérifier que Prometheus se scrape lui-même.

Prérequis
•	Un runtime de conteneurs fonctionnel
•	Le port 9090 libre sur votre poste

#Étapes

1.	Récupérer l'image : docker pull prom/prometheus:latest

````
docker pull prom/prometheus:main-distroless
````

2.	La lancer : docker run -d --name prometheus -p 9090:9090 prom/prometheus:latest

![alt text](commande_docker.png)

3.	Ouvrir http://localhost:9090 dans votre navigateur

![alt text](url_localhost.png)

4.	Aller dans **Status > Targets** et confirmer que la cible prometheus est UP

![alt text](prometheus_status.png)

5.	Exécuter docker logs prometheus et lire la ligne de démarrage qui annonce le répertoire de stockage

Lancement de la commande
````
docker logs prometheus
`````

Dans les logs, on peut apercevoir le chargement du fichier de configuration :


````
time=2026-04-27T09:21:49.817Z level=INFO source=main.go:1650 msg="Loading configuration file" filename=/etc/prometheus/prometheus.yml

time=2026-04-27T09:21:49.817Z level=INFO source=main.go:1689 msg="Completed loading of configuration file" db_storage=12.042µs remote_storage=916ns web_handler=208ns query_engine=542ns scrape=93.291µs scrape_sd=7.875µs notify=52.292µs notify_sd=2.875µs rules=917ns tracing=1.709µs filename=/etc/prometheus/prometheus.yml totalDuration=306.125µs
```

# Exercice02

