1. Démarrage de Minikube
La commande suivante démarre un nouveau cluster Minikube avec deux cœurs de processeur et 5000 Mo de mémoire. Le pilote Docker est utilisé pour exécuter les conteneurs dans le cluster.

minikube start --cpus=2 --memory=5000 --driver=docker
2. Application des configurations Kubernetes
La commande suivante applique la configuration Kubernetes définie dans le fichier microservices.yaml. Cette commande crée ou met à jour les ressources Kubernetes en fonction de la configuration.

kubectl apply -f microservices.yaml
3. Lancement du script d'acheminement d'entrée
Le script ingress-forward.sh est généralement utilisé pour acheminer le trafic entrant vers un service spécifique dans le cluster Kubernetes. La commande suivante lance ce script.

./ingress-forward.sh
N'oubliez pas de remplacer microservices.yaml par le chemin d'accès réel à votre fichier de configuration Kubernetes si nécessaire. De plus, assurez-vous que vous avez les permissions nécessaires pour exécuter le script ingress-forward.sh

4. Lancer kiali
kubectl -n istio-system port-forward deployment/kiali 20001:20001

5. lancer grafana
kubectl -n istio-system port-forward deployment/grafana 3000:3000


