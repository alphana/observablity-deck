---
layout: center
class: text-center
---

# Runtime Deployment Models Comparison

---
layout: default
---

# Node-Based Models Characteristics

## Common Traits
- Node-level resource management
- Cluster-wide deployment strategies
- Network optimization potential

```mermaid
flowchart TD
    subgraph "Node-Based Approaches"
        subgraph "DaemonSet"
            ds[Collector] --> n1[Node 1]
            ds2[Collector] --> n2[Node 2]
        end
        
        subgraph "Centralized"
            n3[App Node 1] --> c1[Collector Node 1]
            n4[App Node 2] --> c1
        end
    end
```

---
layout: two-cols
---

# Pod-Based Models Characteristics

## Common Traits
- Pod-level isolation
- Direct application integration
- Fine-grained control

::right::

```mermaid
flowchart TD
        subgraph "Sidecar"
            subgraph "Pod 1"
                app1[App] --> col1[Collector]
            end
            subgraph "Pod 2"
                app2[App] --> col2[Collector]
            end
        end

```

```mermaid
flowchart TD
        subgraph "Workspace"
            subgraph "Namespace"
                app3[App 1] --> colW[Workspace Collector]
                app4[App 2] --> colW
            end
        end
```

---
layout: two-cols
---

# Hybrid Approaches Characteristics

## Common Traits
- Multi-level data processing
- Flexible deployment options
- Combined benefits

::right::

```mermaid
flowchart TD
        subgraph "DaemonSet + Central"
            ds1[Node Collector 1] --> agg[Central Aggregator]
            ds2[Node Collector 2] --> agg
        end
        
```

```mermaid
flowchart TD
    
        subgraph "Workspace + DaemonSet"
            dsw1[Node Collector] --> wc[Workspace Collector]
            dsw2[Node Collector] --> wc2[Workspace Collector 2]
        end
```

---
layout: default
---

# Runtime Performance Comparison

|Aspect|Node-Based|Pod-Based|Hybrid|
|------|----------|---------|------|
|Network Efficiency|High|Medium|High|
|Resource Utilization|Efficient|Variable|Balanced|
|Scaling Complexity|Low|Medium|High|
|Data Processing Locality|Node-level|Pod-level|Multi-level|
|Maintenance Overhead|Low|High|Medium|

---
layout: two-cols
---

# Resource Impact By Model

Node-Based:
```yaml
DaemonSet:
  - Fixed per node
  - Predictable sizing
  - Node-level quotas

Centralized:
  - Concentrated resources
  - Efficient pooling
  - Dedicated nodes
```

::right::

<br>
<br>
<br>

Pod-Based:
```yaml
Sidecar:
  - Per-pod overhead
  - Linear scaling
  - Container resources

Workspace:
  - Namespace quotas
  - Independent scaling
  - Shared resources
```

---
layout: two-cols
---

# Best Practices by Model Type

## Node-Based Deployments
- Monitor node resources
- Plan node capacity
- Network optimization
- Node affinity rules

## Pod-Based Deployments
- Container resource limits
- Inter-pod communication
- Namespace quotas
- Pod affinity rules

::right::

<br>
<br>
<br>
<br>
<br>
<br>
<br>

## Hybrid Deployments
- Multi-level monitoring
- Tiered resource planning
- Cross-component optimization
- Complex affinity rules

---
layout: end
class: text-center
---

# Decision Framework

1. Start with Scale Analysis
2. Consider Isolation Requirements
3. Evaluate Operational Capacity
4. Choose Base Model
5. Consider Hybrid if Needed