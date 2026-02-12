# GSI vs LSI (ELI5)

## Local Secondary Index (LSI)
Like having a backup way to sort your bookshelf.

- Same partition key, different sort key
- Created at table creation only (can't add later)
- Shares table's throughput
- Strong consistency available

**Example:** Table with UserID (partition) + Timestamp (sort)
LSI: UserID (partition) + Score (sort) - find top scores per user

## Global Secondary Index (GSI)
Like having a completely different bookshelf.

- Different partition key and/or sort key
- Can add anytime after table creation
- Has own throughput (separate billing)
- Eventual consistency only

**Example:** Table with UserID (partition) + Timestamp (sort)
GSI: Email (partition) + LoginDate (sort) - find users by email

## Quick Decision
- **Same partition key needed?** → LSI
- **Different partition key?** → GSI
- **Need to add later?** → GSI (can't add LSI after creation)
- **Strong consistency required?** → LSI

Most common: **GSI** (more flexible)