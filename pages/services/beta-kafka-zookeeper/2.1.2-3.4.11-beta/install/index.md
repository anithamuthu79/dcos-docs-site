---
layout: layout.pug
navigationTitle: 
excerpt:
title: Install and Customize
menuWeight: 20

---

<!-- This source repo for this topic is https://github.com/mesosphere/dcos-commons -->


The default DC/OS Apache ZooKeeper Service installation provides reasonable defaults for trying out the service, but may not be sufficient for production use. You may require different configurations depeneding on the context of the deployment.

## Prerequisites

- If you are using Enterprise DC/OS, you may [need to provision a service account](/latest/security/service-auth/custom-service-auth/) before installing DC/OS Apache ZooKeeper Service. Only someone with `superuser` permission can create the service account.
  - `strict` [security mode](/latest/administration/installing/custom/configuration-parameters/#security) requires a service account.
  - In `permissive` security mode a service account is optional.
  - `disabled` security mode does not require a service account.
- Your cluster must have at least 3 private nodes.

# Installing from the DC/OS CLI

To start a basic test cluster of Apache ZooKeeper, run the following command on the DC/OS CLI. Enterprise DC/OS users must follow additional instructions. [More information about installing Apache ZooKeeper on Enterprise DC/OS](/latest/security/service-auth/custom-service-auth/).

```shell
dcos package install kafka-zookeeper
```

You can specify a custom configuration in an `options.json` file and pass it to `dcos package install` using the `--options` parameter.

```shell
dcos package install kafka-zookeeper --options=options.json
```

**Recommendation:** Store your custom configuration in source control.

For more information on building the `options.json` file, see the [DC/OS documentation](/latest/usage/managing-services/config-universe-service/) for service configuration access.

# Installng from the DC/OS Web Interface

You can [install Apache ZooKeeper from the DC/OS web interface](/latest/usage/managing-services/install/). If you install Apache ZooKeeper from the web interface, you must install the DC/OS Apache ZooKeeper CLI subcommands separately. From the DC/OS CLI, enter:

```shell
dcos package install kafka-zookeeper --cli
```

Choose `ADVANCED INSTALLATION` to perform a custom installation.
