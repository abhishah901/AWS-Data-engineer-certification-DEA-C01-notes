---
title: Encrypting objects at rest
updated: 2024-12-09 02:34:04Z
created: 2024-12-09 02:33:41Z
latitude: 40.76843420
longitude: -74.14542140
altitude: 0.0000
---

Amazon S3 provides several methods to encrypt objects stored at rest:

S3-managed encryption (SSE-S3): With this method, Amazon S3 encrypts your data using keys that it manages and controls. This is the default encryption for all new objects. Amazon handles the encryption, decryption, and key management for you.

SSE-C (Server-Side Encryption with Customer-Provided Keys): You manage and control the encryption keys, while Amazon S3 performs the encryption and decryption operations on your behalf. You have complete control over the keys, but Amazon handles the encryption/decryption process.

Server-Side Encryption with AWS Key Management Service (SSE-KMS): Provides an additional layer of security by integrating with AWS KMS for centralized key management and access controls. KMS encrypts the data keys, which S3 then uses to encrypt the objects.