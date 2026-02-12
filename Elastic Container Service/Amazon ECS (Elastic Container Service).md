# Amazon ECS (Elastic Container Service)

Container orchestration service for Docker containers.

## Launch Types

**EC2:**
- You manage EC2 instances
- More control, lower cost
- Pay for EC2 instances

**Fargate:**
- Serverless, AWS manages infrastructure
- No server management
- Pay per task (vCPU/memory/duration)

## Key Components

**Cluster:**
- Logical grouping of tasks/services

**Task Definition:**
- Blueprint (JSON) defining containers
- Image, CPU, memory, ports, environment variables

**Task:**
- Running instance of task definition
- One or more containers

**Service:**
- Maintains desired count of tasks
- Load balancer integration
- Auto-scaling

## Networking Modes
- **awsvpc:** Each task gets ENI (most common)
- **bridge:** Docker default
- **host:** Use host network

## vs EKS
- **ECS:** AWS-native, simpler, proprietary
- **EKS:** Kubernetes, portable, complex

**Use ECS for:** AWS-only, simplicity, lower learning curve