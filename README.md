Ansible Playbook for Running a Serf Cluster
===========================================

[![Build Status](https://travis-ci.org/jdutton/ansible-serf.png)](https://travis-ci.org/jdutton/ansible-serf)

This playbook provides the `deploy.yml` play to install and launch the [serf](http://www.serfdom.io)
agent.

The [serf pre-built binary packages](http://www.serfdom.io/downloads.html) are downloaded and
cached locally.

# Prerequisites

You must have [Ansible](http://www.ansibleworks.com) installed (see
[Ansible Installation](http://www.ansibleworks.com/docs/intro_installation.html)
for directions).  You must also either have an
[ansible inventory file](http://www.ansibleworks.com/docs/intro_inventory.html)
that enumerates the hosts in your environment or call `ansible-playbook` with the
`-i` flag, specifying comma-separated hostnames explicitly.

# Playbook Configuration

See [config/default.yml](config/default.yml) for playbook configuration variables.
Configuration variables can be set by editting [config/default.yml](config/default.yml)
or via the command-line via *extra vars* (e.g. `ansible-playbook -e`).

# Running the `deploy.yml` Play

By default the [deploy.yml](deploy.yml) play will run `serf` on *all* hosts
and start the serf agent.

```
> ansible-playbook deploy.yml
```

To limit the hosts where the serf agent is deployed, use the `-l` or `--limit` with host patterns.

```
> ansible-playbook deploy.yml -l dbservers
```
