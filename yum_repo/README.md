yum_repo Role
=============

The yum_repo role is a general purpose role to configure common yum repositories. 
Depending on the repository, a number of different options are available.
To install repository defaults, as defined by the repository manager, simply calling the role
with the repository name, unless otherwise noted below.

All repositories use the *name* variable for the repository name
*baseurl* Can be given where you want to specify a particular mirror to use. Typically, this
variable replaces any defaults up the to repository folder in the mirror.

e.g.
```yaml
---
hosts: all
roles:
  - { role: yum_repo, name: epel, epel_stable: 0, epel_testing: 1 }
```

Supported repositories
--------------------

###EPEL

[Extra Packages for Enterprise Linux](http://fedoraproject.org/wiki/EPEL). Current supports 6.x series
distributions.

#### Required variables

* *name*: epel

####Optional variables

* *baseurl*: Option mirror to use rather than the usual mirror list

Default enable repositories - set to 0 to disable

* *epel_stable*

Disabled repositories - set to 1 to enable

* *epel_testing* 
* *epel_source*
* *epel_debuginfo*
* *epel_testing_source*
* *epel_testing_debuginfo*

###JPackage

The [JPackage](http://www.jpackage.org) repository is somewhat stale but still required by Spacewalk

#### Required variables

* *name*: jpackage

###Spacewalk

The [Spacewalk](http://spacewalk.redhat.com) repository contains packages for the Spacewalk software, the upstream of Red Hat's Satellite server.

#### Required variables

* *name*: spacewalk

####Optional variables

Default enable repositories - set to 0 to disable

* *spacewalk*

