# RTO vs RPO

## RPO (Recovery Point Objective)
**How much data loss is acceptable**

- Measured in time before disaster
- Answers: "How old can my recovered data be?"
- Determines backup frequency

**Example:**
- RPO = 1 hour → Can lose up to 1 hour of data
- Need backups every hour

## RTO (Recovery Time Objective)
**How long to recover**

- Measured in time after disaster
- Answers: "How quickly must I be back online?"
- Determines recovery strategy

**Example:**
- RTO = 4 hours → Must be operational within 4 hours
- Determines automation level, standby resources

## Visual
```
[Disaster Occurs]
    ↑              ↓
    |              |
   RPO            RTO
(data loss)   (downtime)
```

## AWS Examples

| Strategy | RPO | RTO |
|----------|-----|-----|
| Multi-AZ RDS | Seconds | 1-2 min |
| RDS Read Replica | Minutes | Minutes-Hours |
| EBS Snapshots | Hours | Hours |
| Backup & Restore | Hours-Days | Hours-Days |
