---
layout: center
class: text-center
---

# Runtime Classification of Deployment Models

---
layout: two-cols
---

# 1. Node-Based Models

## DaemonSet Model
- One collector per node
- Predictable deployment
- Node-level isolation

## Centralized Model
- Dedicated collector nodes
- Cluster-wide collection
- Resource optimization

::right::

# 2. Pod-Based Models

## Sidecar Pattern
- One collector per pod
- Highest isolation
- Direct container access

## Workspace Deployment
- Deployment per workspace/namespace
- Team/project isolation
- Independent scaling

---
layout: two-cols
---

# 3. Hybrid Approaches

## DaemonSet + Centralized
- Local collection (DaemonSet)
- Central aggregation layer
- Two-tier architecture

## Workspace + DaemonSet
- Workspace-level collectors
- Node-level preprocessing
- Multi-level isolation

::right::

<br>
<br>

## Custom Combinations
- Mixed deployment strategies
- Use-case specific designs
- Specialized requirements

---
layout: default
---

# Runtime Characteristics

|Model Type|Data Flow|Resource Distribution|Scaling Unit|
|----------|---------|-------------------|------------|
|Node-Based|Node → Storage|Per Node/Dedicated|Node/Cluster|
|Pod-Based|Pod → Storage|Per Pod/Workspace|Pod/Workspace|
|Hybrid|Multi-tier|Mixed|Multiple Levels|

---
layout: two-cols
---

# Deployment Decision Factors

1. Scale Requirements
  - Node count
  - Pod density
  - Data volume

2. Isolation Needs
  - Security requirements
  - Multi-tenancy
  - Team structure

::right::

<br>
<br>
<br>

3. Operational Model
  - Team expertise
  - Maintenance capacity
  - Monitoring capabilities

4. Performance Requirements
  - Latency sensitivity
  - Network constraints
  - Resource efficiency