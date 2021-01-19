# **Copy Certificates**
## Description
Copy certificates from the user certificate store to the system store.
Chances are you want the Move Certificates plugin, however there are some situations where you want to copy instead - in which case you are in the right place!
(for example, the firefox mobile browser (fennec / fenix) uses the system cert store for validating its sync server SSL cert, but the user cert store for web SSL, so you need your custom CA in both places)

## Changelog
v2.0
* Copy the cert instead of moving

v1.9
* Dynamically determine correct SELinux context for cert from device itself.
* AdGuard users may need to reinstall their HTTPS filtering certificate.

v1.8
* Merged pull request: Fix SELinux contexts

v1.7

* Merged pull request: Prevent placeholder from being moved to system store
* Merged pull request: System store certs should be owned by user and group root

v1.6

* Updated to newest module installer template 

v1.5

* Updated module template to 17000

v1.4

* Remove unnecessary placeholders

v1.3

* Create system store module directory instead of mkdir command

v1.2

* Create system store directory if it does not already exist

v1.1

  * Added more info to README

v1

  * Initial release

## Notes
If for some reason you do not want all your certificates moved from the user store to the system store, you can specify which certificate to move in `/common/post-fs-data.sh` by replacing the * with the name of the certificate; i.e.,
```
mv -f /data/misc/user/0/cacerts-added/12abc345.0 $MODDIR/system/etc/security/cacerts
```


