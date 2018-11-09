# Deploy web servers on gce

Set of yaml scripts to setup 3 webservers and a load balancer on google cloud.

## Getting Started

You should download this project and create a folder structure, then encrypt yml file that contains password for satellite. A few yml files were used to setup and subscribe a server into a Red Hat Satellite. you can exclude those, not needed to deploy the servers on google cloud.

### Prerequisites

must have installed ansible 2.6

```
[davidsg@srv3 ~]$ yum install -y ansible
```

Create the following folder structure on your home dir work.

```
[davidsg@srv3 ~]$ mkdir workdir
```

Place the folders and files as follow:

+--- ansible.cfg
+--- apache.yaml
+--- apache_lab
|   +--- defaults
|   |   +--- main.yml
|   +--- files
|   +--- handlers
|   |   +--- main.yml
|   +--- meta
|   |   +--- main.yml
|   +--- README.md
|   +--- tasks
|   |   +--- main.yml
|   +--- templates
|   |   +--- apache_httpdconf.j2
|   |   +--- apache_indexhtml.j2
|   +--- tests
|   |   +--- inventory
|   |   +--- test.yml
|   +--- vars
|   |   +--- main.yml
+--- authorized_keys.yml
+--- gce-apache.yml
+--- gce-lb-apache.yml
+--- gce-lb.yml
+--- gce-test.yml
+--- gce-web-delete.yml
+--- ifcfg-ethX.txt
+--- sat_hosts.yml
+--- set_hostname.yml
+--- set_ip.yml
+--- set_update.retry
+--- set_update.yml
+--- vars
|   +--- gce_vars.yml
|   +--- vars.yml




### Installing

Go to workdir

```
[davidsg@srv3 ~]$ cd workdir
```

run the ansible-playbook command

```
[davidsg@srv3 workdir]$ ansible-playbook gce-lb-apache.yml
```

open google cloud and verify

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Once tested, you can destroy the servers

```
[davidsg@srv3 workdir]$  ansible-playbook gce-web-delete.yml
```

verify at google cloud portal.

### And coding style tests


## Deployment


## Built With


## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags).

## Authors

* **Alejandro Callejas** - *Initial work* - [PurpleBooth](https://github.com/Alejandro.Callejas)


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
