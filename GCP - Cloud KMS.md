Google's Cloud Key Management Service is a managed service that allows users to manage cryptographic keys for their cloud services 

* Enables users to easily decrypt, encrypt, sign, and verify data by providing secure key storage, key generation, and key management functionlities (Ex: *Creating, managing, and destroying cryptographic keys*, *Encrypting and decrypting data using the user's managed cryptographic keys*, *Automatic cryptographic key rotation to help minimize the risk of key compromise*, *etc.*)
* Provides an API to encrypt, decrypt, or sign data
* Can use existing cryptographic keys that were created on premises
* Requires the KMS API to be enabled

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png0

# KMS Key Types

| KMS Key Type | Description |
| --- | --- |
| Google-Managed Key | No configuration required by the user |
| Customer-Managed Key | The user uses a key that they generated using KMS |
| Customer-Supplied Key | The user adds a key that they generated on-premises to KMS |
