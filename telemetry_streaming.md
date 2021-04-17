# Telemetry Streaming

Post following declaration to : 
https://(bigip hostname or ip)/mgmt/shared/telemetry/declare

```
{
    "class": "Telemetry",
    "My_System": {
        "class": "Telemetry_System",
        "systemPoller": {
            "interval": 60
        }
    },
    "Kafka_consumer": {
        "class": "Telemetry_Consumer",
        "type": "Kafka",
        "host": "microk8s.demo.local",
        "protocol": "binaryTcp",
        "port": 9092,
        "topic": "f5-telemetry"
    },
    "controls": {
     "class": "Controls",
     "logLevel": "debug",
     "memoryThresholdPercent": 65
     }
}
```
