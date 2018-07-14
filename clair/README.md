Clair
===
A static analysis tool by CoreOS. Clair works by pulling your images, and scanning it's image layers for known CVE's.

Clair's functionality can be broken down into two functions, an aggregator for CVEs, and an [API](https://coreos.com/clair/docs/2.0.1/api_v1.html) that clients can use to control clair. A typical workflow would look something like this:

- build your image
- tag your image with your build tag
- use clair's api to request that clair pulls your build's image from your registry
- use clair's api to request that clair analyzes your build's image
- analyze results

Alternatively, you can use a docker registry that integrates clair natively, so your workflow is to just push your image. [CoreOS's Quay](https://quay.io/), and [VMware's Harbor](https://github.com/vmware/harbor) both support Clair.

clair's datasources for CVEs pulls data for a myriad of base images including:
- alpine
- debian/ubuntu
- rhel/fedora/centos
- oracle

These options and more can be configured for clair, see this example config for more information:
[config.yaml.sample](https://github.com/coreos/clair/blob/master/config.yaml.sample)


Note:
You can configure which datasources to use for CVE data. Read more about [drivers and datasources](https://github.com/coreos/clair/blob/master/Documentation/drivers-and-data-sources.md).

---
![]()
---

# Integrations

https://coreos.com/clair/docs/latest/integrations.html

Use Gitlab CI:
https://docs.gitlab.com/ee/ci/examples/container_scanning.html

# Clair Lab

This lab borrows heavily from Clairctl's contrib, which can be found here:
https://github.com/jgsqware/clairctl/tree/master/contrib

To get started, let


Vulnerable images:
https://hub.docker.com/search/?isAutomated=0&isOfficial=0&page=1&pullCount=0&q=vulnerables&starCount=0
