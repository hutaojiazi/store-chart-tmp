# argocd-helm-chart

docker build docker/. -t hutaojiazidocker/h365:0.1


argocd app create spring --repo https://github.com/hutaojiazi/store-chart-tmp.git --path . --dest-server https://kubernetes.default.svc --dest-namespace default


kubectl port-forward svc/spring-petclinic -n default 9090:8080
