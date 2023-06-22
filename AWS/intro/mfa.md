MFA - Multi factor Authentication\
**Factors** - pieces of evidence to prove identity

Factors:
- Knowledge (username, passwords)
- Possession (bankcards, mfa apps)
- Inherent (fingerprints, face, voices)
- Location (physical and network)


Every user has his own virtual MFS (device). 
AWS generates secret key and additional information about a user and mix it to qr code, that will be used by an mfs app.

MFS app (like google authenticator) will have different mfs devices (virtual ones) to generate number codes. 

With single factor authentication (login and password), this code will be a structure for **Multi factor Authentication**.

----------------

Identity and Access Management (**IAM**) is not only used for other users, but also for defining security of a root user.

**IAM is a global resilent service.**
Every account has "own copy" of IAM which has full trust.

------

IAM allows us to create:
- User (represent people and application with certain accesses to different things on aws)
- Group (collection of related users with specific access)
- Role ()


