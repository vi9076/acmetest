# acmetest
Unit test project for **acme.sh** project https://github.com/Neilpang/acme.sh



# Here are the latest status:

| Platform | Status| Last Run Time| Comments|
-----------|-------|--------------|---------|
|freebsd| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/freebsd.svg?1544720709)| Thu, 13 Dec 2018 17:05:09 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/freebsd.out) |
|openbsd| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/openbsd.svg?1544749875)| Fri, 14 Dec 2018 01:11:15 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/openbsd.out) |
|pfsense| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/pfsense.svg?1544750170)| Fri, 14 Dec 2018 01:16:10 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/pfsense.out) |
|solaris| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/solaris.svg?1544750499)| Fri, 14 Dec 2018 01:21:39 GMT| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/solaris.out) |
|windows-cygwin| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/windows-cygwin.svg?1544751272)| Fri, 14 Dec 2018 01:34:32 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/windows-cygwin.out) |
|ubuntu:latest| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/ubuntu-latest.svg?1544751508)| Fri, 14 Dec 2018 01:38:28 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/ubuntu-latest.out) |
|ubuntu:16.04| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/ubuntu-16.04.svg?1544751956)| Fri, 14 Dec 2018 01:45:56 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/ubuntu-16.04.out) |
|ubuntu:14.04| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/ubuntu-14.04.svg?1544752168)| Fri, 14 Dec 2018 01:49:28 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/ubuntu-14.04.out) |
|debian:latest| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/debian-latest.svg?1544752380)| Fri, 14 Dec 2018 01:53:00 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/debian-latest.out) |
|debian:9| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/debian-9.svg?1544752587)| Fri, 14 Dec 2018 01:56:27 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/debian-9.out) |
|debian:8| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/debian-8.svg?1544753002)| Fri, 14 Dec 2018 02:03:22 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/debian-8.out) |
|debian:7| ![](https://cdn.rawgit.com/Neilpang/acmetest/master/status/debian-7.svg?1544753214)| Fri, 14 Dec 2018 02:06:54 UTC| [Passed](https://github.com/Neilpang/acmetest/blob/master/logs/debian-7.out) |

# How to run tests

First point at least 2 of your domains to your machine, 
for example: `aa.com` and `www.aa.com`

And make sure 80 port is not used by anyone else.

```
cd acmetest
TestingDomain=aa.com   TestingAltDomains=www.aa.com  ./letest.sh
```

# How to run tests in all the platforms through docker.

You must have docker installed, and also point 2 of your domains to your machine.

Then test all the platforms :

```
cd acmetest
TestingDomain=aa.com   TestingAltDomains=www.aa.com  ./rundocker.sh  testall
```

The script will download all the supported platforms from the official docker hub, then run the test cases in all the supported platforms.

Then test single docker platform :

```
cd acmetest
TestingDomain=aa.com   TestingAltDomains=www.aa.com  ./rundocker.sh  testplat   centos:latest
```

# Run tests with ngrok automatically

If you don't want to use 2 domains to test, we can use ngrok to test with temp domain.

Please register an free account at https://ngrok.com/

You will get your ngrok auth token.  Then:

```
export NGROK_TOKEN="xxxxxxxxxx"

./letest.sh

```








