---
layout: center
class: text-center
---

# Workspace-Scoped Deployment Model

---
layout: default
---

# Workspace Architecture

```mermaid
flowchart TD
    subgraph "OpenShift Cluster"
        subgraph "Workspace/Namespace 1"
            subgraph "Collector Deployment 1"
                col1["OTLP Collector Pod 1"]
                col1r["OTLP Collector Pod 1\nReplica"]
            end
            
            subgraph "Application Pods 1"
                app1["Application Pod 1"]
                gw1["Gateway Pod 1"]
            end
        end
        
        subgraph "Workspace/Namespace 2"
            subgraph "Collector Deployment 2"
                col2["OTLP Collector Pod 2"]
                col2r["OTLP Collector Pod 2\nReplica"]
            end
            
            app2["Application Pod 2"]
        end
    end
    
    app1 & gw1 --> col1 & col1r
    app2 --> col2 & col2r
```

---
layout: two-cols
---

# Workspace Advantages

- Complete namespace isolation
- Independent scaling
- Team-specific configurations
- Separate service accounts
- Better multi-tenant support
- Independent maintenance

::right::

# Workspace Challenges

- More configurations
- Higher resource usage
- Multiple Kafka connections
- Complex monitoring setup
- Coordination across teams
