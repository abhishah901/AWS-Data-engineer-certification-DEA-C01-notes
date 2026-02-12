# Transit Gateway

## What It Is
Regional virtual router - hub connecting VPCs and on-premises networks

## Core Concept
Hub-and-spoke topology instead of mesh

**Without TGW (mesh):**
5 VPCs = 10 peering connections

**With TGW (hub):**
5 VPCs = 5 attachments to central hub

## Key Features

**Transitive Routing:**
VPC-A can reach VPC-C through TGW (A→TGW→C)
VPC Peering cannot do this

**Multi-Account:**
Share via AWS Resource Access Manager (RAM)
One account owns TGW, others attach VPCs

**Attachments:**
- VPCs
- VPN connections
- Direct Connect gateways
- Other Transit Gateways (peering)

**Route Tables:**
Central routing control
Define which attachments can reach which

## Setup Pattern

1. Create Transit Gateway (in central/network account)
2. Share via AWS RAM to other accounts
3. Create VPC attachments in each account
4. Update VPC route tables (destination: other VPC CIDRs, target: TGW)
5. Configure TGW route tables

## Requirements

**No overlapping CIDRs:**
Must renumber VPCs if IPs overlap
Cannot route duplicate IP ranges

**Dedicated subnet:**
Best practice: separate subnet per VPC attachment

## Use Cases

- 3+ VPCs needing connectivity
- Hybrid cloud (VPCs + on-premises)
- Centralized network management
- Future growth expected
- Multi-account Organizations

## Exam Signals

"Multiple VPCs"
"Scalable, long-term solution"
"May add more VPCs"
"Centralized management"
"AWS Organizations, multi-account"
"Transit connectivity" or "transitive routing"

## vs VPC Peering

**Transit Gateway:**
- Scales linearly (n attachments)
- Transitive routing
- Central management
- Higher cost

**VPC Peering:**
- Scales poorly (n² connections)
- Non-transitive
- Per-connection management
- Lower cost for 2 VPCs

## Common Exam Pattern

Question: "Connect multiple VPCs across accounts, may grow"
Wrong: VPC Peering (doesn't scale)
Right: Transit Gateway + AWS RAM

## Cost Structure

- Attachment fee per hour
- Data processing charge per GB
- More expensive than peering but worth it at scale