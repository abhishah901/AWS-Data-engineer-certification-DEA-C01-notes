![5855da304b0d8278edff9c1aa7820733.png](../../../_resources/5855da304b0d8278edff9c1aa7820733.png)

---

# Elastic Beanstalk Deployment Policies

## All at Once
- Deploys to all instances simultaneously
- **Downtime:** Yes (brief)
- **Rollback:** Manual redeploy
- **Cost:** None
- **Use:** Dev/test environments

## Rolling
- Deploys in batches
- **Downtime:** No (reduced capacity during deployment)
- **Rollback:** Manual redeploy
- **Cost:** None
- **Use:** Cost-sensitive, can tolerate reduced capacity

## Rolling with Additional Batch
- Launches extra batch first, then rolling update
- **Downtime:** No (maintains full capacity)
- **Rollback:** Manual redeploy
- **Cost:** Minimal (temporary extra instances)
- **Use:** Production, maintain capacity

## Immutable
- Launches full new ASG, swaps after health checks
- **Downtime:** No
- **Rollback:** Fast (terminate new ASG)
- **Cost:** Moderate (double capacity during deployment)
- **Use:** Mission-critical, zero risk tolerance

## Blue/Green (Traffic Splitting)
- Deploys to separate environment, routes % of traffic
- **Downtime:** No
- **Rollback:** Instant (route back)
- **Cost:** High (maintains both environments)
- **Use:** Canary testing, A/B testing

## Comparison Table

| Policy | Downtime | Rollback | Cost | Capacity Impact |
|--------|----------|----------|------|-----------------|
| All at Once | Yes | Manual | None | Full downtime |
| Rolling | No | Manual | None | Reduced |
| Rolling + Batch | No | Manual | Low | Maintained |
| Immutable | No | Fast | Medium | Maintained |
| Blue/Green | No | Instant | High | Double |

## Quick Decision Guide

- **Speed priority** → All at Once
- **Cost priority** → Rolling
- **Zero downtime + cost-effective** → Rolling with Additional Batch
- **Safety + easy rollback** → Immutable
- **Testing/canary** → Blue/Green (Traffic Splitting)