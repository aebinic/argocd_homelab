

#Commands

helm repo add treafik https://treafik.github.io/charts
helm repo update

helm install treafik treafik/treafik \
    --namespace treafik --create-namespace
    --set servive.type=NodePort \
    --set ports.web.nodePort=30080
    --set ports.websecure.nodePort=30443

k -n treafik get pods,svc
k get ingressclass