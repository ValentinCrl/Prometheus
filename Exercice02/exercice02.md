# Exercice 2 : Écrire votre premier prometheus.yml

## Objectif

Remplacer la configuration par défaut par votre propre prometheus.yml. Définir un intervalle de scrape global de 10s, un external label environment=lab, et recharger Prometheus sans le redémarrer.

## Prérequis
•	Exercice 1 terminé

## Étapes
6.	Arrêter le conteneur précédent : docker rm -f prometheus
```
docker rm -f prometheus
````

7.	Créer un fichier prometheus.yml sur l'hôte avec les paramètres demandés


8.	Lancer un nouveau conteneur avec --web.enable-lifecycle et le fichier monté sur /etc/prometheus/prometheus.yml

9.	Modifier le fichier puis déclencher un rechargement : curl -X POST http://localhost:9090/-/reload

10.	Confirmer la modification dans Status > Configuration
