# Availability Zones (AZs)

Isolated data centers within an AWS Region.

## Key Characteristics
- One or more physical data centers per AZ
- Physically separated (miles apart)
- Low-latency connections between AZs in same Region
- Independent power, cooling, networking
- Named: us-east-1a, us-east-1b, etc.

## Purpose
- High availability
- Fault tolerance
- Disaster recovery within Region

## Important Notes
- Each Region has 3+ AZs (typically 3-6)
- AZ names mapped differently per AWS account (your 1a ≠ my 1a)
- Deploy across multiple AZs for HA
- Services like RDS Multi-AZ span AZs automatically