---
layout: center
class: text-center
---

# DaemonSet Deployment Model

---
layout: default
---

# DaemonSet Architecture

```mermaid
flowchart TD
    subgraph "OpenShift Cluster"
        subgraph "Worker Node 1"
            ds1["OTLP Collector\nDaemonSet Pod"]
            app1["Application Pod 1"]
            app2["Application Pod 2"]
            gw1["Gateway Pod 1"]
        end
        
        subgraph "Worker Node 2"
            ds2["OTLP Collector\nDaemonSet Pod"]
            app3["Application Pod 3"]
            app4["Application Pod 4"]
            gw2["Gateway Pod 2"]
        end
    end
    
    subgraph "Message Layer"
        kt1["Kafka Topics#Worker Node 1"]
        kt2["Kafka Topics#Worker Node 2"]
    end
    
    app1 & app2 & gw1 --> ds1
    app3 & app4 & gw2 --> ds2
    ds1 --> kt1
    ds2 --> kt2
```

---
layout: two-cols
---

# DaemonSet Advantages

- One collector per node
- Predictable resource allocation
- Simple capacity planning
- Better network efficiency
- Easy monitoring per node
- Simple configuration management

::right::

# DaemonSet Challenges

- Fixed overhead per node
- Less flexible scaling
- Need node resources regardless of load
- Node failure impacts collection
- All collectors update simultaneously


---
layout: default
---

# Maintenance Considerations

- Single DaemonSet manifest to maintain
- Rolling updates by OpenShift
- Uniform configuration across nodes
- Simple health monitoring
- Easy backup and recovery
- Automated pod placement

