# AWS Application Recovery Controller (ARC)

Manages application readiness and recovery across multi-region active-active architectures.

## Components

**Readiness Check:**
- Monitors resources across regions
- Verifies capacity, configuration
- Answers: "Can this region handle traffic?"

**Routing Control:**
- Traffic shifting across regions/cells
- Manual or automated failover
- Simple on/off switches for traffic routing

**Safety Rules:**
- Prevent accidental simultaneous changes
- Assertion rules (e.g., "at least one region must be ON")
- Gating rules (prevent rapid changes)

**Cluster:**
- Regional endpoints for low-latency control

## Use Cases
- Multi-region active-active failover
- Planned maintenance (shift traffic away)
- DR orchestration
- Cell-based architecture

## Example Workflow
1. Readiness check detects region issue
2. Routing control shifts traffic to healthy region
3. Safety rules prevent turning off all regions

## vs Route 53 Health Checks
**ARC:** Application-level control, complex readiness
**Route 53:** DNS-level, simple endpoint checks

**Use:** Multi-region active-active apps needing controlled failover and readiness verification.