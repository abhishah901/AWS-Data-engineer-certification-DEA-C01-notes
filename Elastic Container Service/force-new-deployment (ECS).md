# --force-new-deployment (ECS)

Forces ECS service to deploy new tasks even if no task definition changed.

## Command
```bash
aws ecs update-service \
  --cluster my-cluster \
  --service my-service \
  --force-new-deployment
```

## Use Cases
- Pull latest Docker image (same tag)
- Apply updated secrets/config
- Replace unhealthy tasks
- Test deployment process
- Update underlying infrastructure

## What It Does
1. Stops current tasks
2. Launches new tasks with existing task definition
3. Follows deployment configuration (rolling, blue/green)

## Common Scenario
Updated Docker image with same tag (e.g., `latest`) → `--force-new-deployment` → ECS pulls fresh image

**vs updating task definition:** Task definition change auto-triggers deployment. Use flag when definition unchanged but need redeployment.