---
layout: center
class: text-center
---

# Centralized Deployment Model

---
layout: default
---

# Centralized Architecture

```mermaid
flowchart TD
    subgraph "OpenShift Cluster"
        subgraph "Application Worker Nodes"
            subgraph "Worker Node 1"
                app1["Application Pod 1"]
                app2["Application Pod 2"]
                gw1["Gateway Pod 1"]
            end
            
            subgraph "Worker Node 2"
                app3["Application Pod 3"]
                app4["Application Pod 4"]
                gw2["Gateway Pod 2"]
            end
        end
        
        subgraph "Collector Worker Nodes"
            subgraph "Collector Node 1"
                col1["Central Collector 1"]
            end
            
            subgraph "Collector Node 2"
                col2["Central Collector 2"]
            end
        end
    end

    subgraph "Message Layer"
        kt1["Kafka Topics#Worker Node 1"]
        kt2["Kafka Topics#Worker Node 2"]
    end
    
    app1 & app2 & gw1 --> col1 & col2
    app3 & app4 & gw2 --> col1 & col2

    col1 --> kt1
    col2 --> kt2
```

---
layout: two-cols
---

# Centralized Advantages

- Efficient resource utilization
- Easier upgrades and configuration
- Better control over resources
- Simplified Kafka connection pool
- Easy collector redundancy
- Centralized monitoring

::right::

# Centralized Challenges

- Single point of failure risk
- Complex scaling requirements
- Higher cross-node network traffic
- Complex capacity planning
- Risk of collector overload


