# yum-rpm-downloader-docker
Dockerfile to download rpms via yumdownloader for offline installation

If you want to build this image for yourself then you can do it like this:

``docker build --rm -t yum-rpm-downloader-docker .``

Then just run it and replace MYLOCALRPMDIR with a full path to where you want the RPMs to be saved:

``docker run -v MYLOCALRPMDIR:/rpms/ yum-rpm-downloader-docker``

This example above just downloads ansible, git and curl and their dependencies, but of course you have your own list of packages you want so instead you can pass them at the end of this command, so for example if you want to install openldap, openldap-clients and openldap-servers just do the following:

``docker run -v MYLOCALRPMDIR/rpms:/rpms/ yum-rpm-downloader-docker openldap openldap-clients openldap-servers``

Pull requests welcome, please raise issues in github if you find any.
