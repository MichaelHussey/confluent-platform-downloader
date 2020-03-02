# confluent-platform-downloader
Forked from https://github.com/tenfourty/yum-rpm-downloader-docker, thanks Jeremy Brown!

Dockerfile to download rpms via yumdownloader for offline installation of Confluent Platform 5.4

If you want to build this image for yourself then you can do it like this:

``docker build --rm -t confluent-platform-downloader .``

Then just run it and replace MYLOCALRPMDIR with a full path to where you want the RPMs to be saved:

``docker run -v MYLOCALRPMDIR:/rpms/ confluent-platform-downloader``

This example above just downloads Confluent Platform 5.4 plus Confluent Server

If you want to change the version of the Operating System you just need to change the FROM line - currently this has only been tested with CentOS but it should work for Fedora, RHEL and other Enterprise Linux like OSes.

```
FROM centos:latest

FROM centos:7

FROM centos:6.6

FROM centos:5.11
```

Once you have pulled down the rpms, change to the directory where you saved them. Then you can install by following the instructions from 
step no 4 onward https://docs.confluent.io/current/installation/installing_cp/rhel-centos.html
