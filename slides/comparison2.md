---
layout: center
class: text-center
---

# Deployment Models Comparison

---
layout: default
---

# Resource Impact Comparison

|Model|Collector Instances|Resource Overhead|Scalability|Maintenance Cost|
|-----|------------------|-----------------|------------|----------------|
|DaemonSet|240 (80 per cluster)|Medium|Limited|Low|
|Centralized|3-10 per cluster|Low|High|Medium|
|Sidecar|2,080 - 8,320|Highest|Automatic|Highest|
|Hybrid|240 + 6-10|Medium-High|Flexible|Medium-High|
|Workspace|2-3 per workspace|Medium|Independent|Medium|

---
layout: default
---

# Operational Comparison

|Model|Configuration Complexity|Monitoring|Troubleshooting|Update Strategy|
|-----|----------------------|----------|---------------|---------------|
|DaemonSet|Low|Simple|Easy|Rolling per node|
|Centralized|Medium|Centralized|Medium|Rolling per pod|
|Sidecar|Highest|Complex|Complex|With application|
|Hybrid|High|Two-tier|Complex|Phased approach|
|Workspace|Medium|Per workspace|Medium|Independent|

---
layout: two-cols
---

# Best For Scenarios

DaemonSet:
- Simple management
- Consistent workloads
- Node-level isolation

Centralized:
- Resource efficiency
- Simple configuration
- Limited nodes

::right::

Sidecar:
- High isolation needs
- Custom configurations
- Direct control

Workspace:
- Multi-tenant clusters
- Team independence
- Compliance requirements

---
layout: center
class: text-center
---

# Recommendations

1. For Your Scale:
   - DaemonSet Model (Primary Choice)
   - Workspace Model (If strict isolation needed)

2. Why DaemonSet:
   - Simplest maintenance
   - Predictable scaling
   - Clear ownership
   - Easy troubleshooting

3. Considerations:
   - Monitor resource usage
   - Plan for growth
   - Regular updates
   - Clear procedures

---
layout: end
class: text-center
---

# Questions?

[Documentation & Resources]
