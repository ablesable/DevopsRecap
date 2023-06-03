Ubuntu has APT package manager.
Debian has dpkg package manager, also available on ubuntu, cause ubuntu is based on debian.
Redhat has rpm.
Alpine has APK.

## More friendly package manager
Aptitude is based on APT. To install it on linux:
`$ sudo apt install aptitude`

## apt
`$ apt-get install ` is older version that `$ apt install`.\
`$ apt search (appname)` is for searching similar versions of the app.\
`$ apt show (appname)` shows information about some app.\
`$ apt update` update information about available packages. **Better to run this before apt install**\
`$ apt list` list every installed packages.\
`$ apt list upgradable` list everything upgradable.\
`$ apt upgrade` upgrade everything.\
Apt needs to be preceded by sudo. apt-get not necessarily.
 