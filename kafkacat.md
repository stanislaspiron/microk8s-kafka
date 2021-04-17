# Kafkacat

To check Telemetry streaming usage in kafka, log in kafkacat pod and get events from topic f5-telemetry
1. Get pod name:

```
$ kubectl get pod 
NAME                                     READY   STATUS    RESTARTS   AGE
kafka-cat-bf44dd754-nfjhf                1/1     Running   0          2d
zookeeper-deployment-1-6d6b94b84-jgcgd   1/1     Running   0          2d
kafka-broker0-5ddf5cbb56-f6pb6           1/1     Running   0          37m
```

2. excecute following command
```
kubectl exec -it kafka-cat-bf44dd754-nfjhf -- kafkacat -b kafka-service:9092 -t f5-telemetry
```
