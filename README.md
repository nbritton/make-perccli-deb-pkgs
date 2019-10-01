## Dell PERCCLI for Ubuntu Server.
# make-perccli-deb-pkgs

Make Dell PERCCLI Ubuntu Server .deb packages and local repository for self hosting.

PERCCLI doesn't exist in Dell's Linux package repositories, so we need to build .deb packages from the tar.gz files to use it properly on Ubuntu Server. This script will fetch the tar.gz files, build .deb packages from them, and then create a local package repository for self hosting the .deb files.

The tool has runtime dependancies on alien, fakeroot, apt-ftparchive (apt-utils), and dpkg-buildpackage (dpkg-dev) commands.

```bash
apt -qq install alien fakeroot apt-utils dpkg-dev;
```

Here are the basic steps to use this tool:

```bash
test -d /var/www/html || apt install -qq apache2;
mkdir -p /var/www/html/dell/perccli;
cd /var/www/html/dell/perccli;
curl -s http://www.exabit.io/ubuntu/make-perccli-deb-pkgs | bash;
chmod -R 755 /var/www/html/dell;
```
