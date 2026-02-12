Amazon Redshift supports encryption at rest and in transit. For encryption at rest, it uses keys managed through AWS Key Management Service (KMS). 

When you create a table in Redshift, you can choose to encrypt your data at rest by selecting an encryption key. If you don’t choose a key, Redshift takes the default key for the account.