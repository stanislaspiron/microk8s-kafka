# microk8s-kafka

1. Change hostname in kafka/kafka-deployment.yml

2. Deploy Kafka
```
kubectl apply -f kafka/
```

3. Patch NGINX ingress controller to forward connections to kafka-service

```
kubectl -n ingress patch daemonset nginx-ingress-microk8s-controller --patch "$(cat ingress/kafka-patch-ingress-daemonset.yaml)"
kubectl -n ingress patch configmap nginx-ingress-tcp-microk8s-conf --patch "$(cat ingress/kafka-patch-ingress-tcp-configmap.yaml)"

