---
layout: center
class: text-center
---

# Hybrid Deployment Model

---
layout: default
---

# Hybrid Architecture

```mermaid
flowchart TD
    subgraph "OpenShift Cluster"
        subgraph "Worker Node 1"
            ds1["DaemonSet\nCollector"]
            app1["Application Pod 1"]
            gw1["Gateway Pod 1"]
        end
        
        subgraph "Worker Node 2"
            ds2["DaemonSet\nCollector"]
            app2["Application Pod 2"]
            gw2["Gateway Pod 2"]
        end
        
        subgraph "Aggregation Layer"
            agg1["Central Collector 1"]
            agg2["Central Collector 2"]
        end
    end
    
    app1 & gw1 --> ds1
    app2 & gw2 --> ds2
    ds1 & ds2 --> agg1 & agg2
```

---
layout: two-cols
---

# Hybrid Advantages

- Balanced efficiency
- Two-tier collection
- Better fault isolation
- Flexible updates
- Separate scaling layers
- Enhanced reliability

::right::

# Hybrid Challenges

- Complex initial setup
- Two collector types
- Complex troubleshooting
- Careful capacity planning
- Higher maintenance overhead

---
layout: default
---

# Component Configuration

DaemonSet Collectors:
```yaml {all|3-7|9-13}
resources:
  requests:
    cpu: "200m"
    memory: "256Mi"
  limits:
    cpu: "500m"
    memory: "512Mi"
```

Aggregation Collectors:
```yaml
resources:
  requests:
    cpu: "500m"
    memory: "512Mi"
  limits:
    cpu: "1000m"
    memory: "1Gi"
```

---
layout: two-cols
---

# Deployment Strategy

1. DaemonSet Layer:
   - One collector per node
   - Local data collection
   - Basic preprocessing

2. Aggregation Layer:
   - Load-balanced collectors
   - Data aggregation
   - Advanced processing
   - Kafka integration

::right::

<br>
<br>
<br>

3. Scaling Strategy:
   - Automatic node coverage
   - HPA for aggregation layer
