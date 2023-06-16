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

With single authentication (login and password), this code will be structure for **Multi factor Authentication**.