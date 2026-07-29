Déploiement K8S : c'est un objet K8S qui décrit “Je veux faire tourner cette image conteneur, avec tel nombre d’exemplaires, et Kubernetes doit maintenir cet état.”. Il est représenté par un fichier YAML. 

kubectl : C'est l’outil en ligne de commande qui permet de piloter Kubernetes en envoyant les commandes à l'API Server K8S, qui se trouve sur le control plane.

Label : Les pods issus d'un Déploiement donné recoivent un ou plusieurs labels qui vont permettre à un Service K8S de d'effectuer la redirection de port même quand l'ip change.

Pod : C’est une sorte de petite “boîte d’exécution” Kubernetes dans laquelle tourne un ou plusieurs conteneurs.

Scheduler : Le scheduler est le composant Kubernetes (faisant partie du control plane) qui décide sur quel node un pod doit être lancé.

Service K8S : Un Service K8S est un objet K8S. Il ne tourne pas sur un node spécifique, il existe comme une règle de redirection réseau au niveau du cluster. Les pods étant amenés à changer, on ne peut pas compter sur leur adresse IP pour assurer la continuité du service de l'application. Ainsi le Service K8S sert à faire une redirection de port dynamique vers les bons pods, et à rendre l'application accessible depuis l'extérieur.
On peut créer un service via un fichier YAML (recommandé) ou via une commande. C'est d'ailleurs dans le fichier YAML que sont précisés les labels dont le Service doit s'occuper.

kubelet : Le kubelet est l’agent Kubernetes installé sur chaque node.