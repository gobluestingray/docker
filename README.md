About this Repo
======

This is a fork of [Odoo's `docker` repository](https://github.com/odoo/docker).

This fork was created because Odoo's upstream changes were breaking their `11.0`
build by causing some unfixable permissions problems. As a workaround, this repo
is keeping Odoo's Docker images at a stable point in history so that they can be
depended on for stability.

This repo will make little to now changes from Odoo's base images. Any
Blue Stingray or project-specific changes should be made in [the `odoo_images`
repository](https://github.com/gobluestingray/odoo_images) rather than here.

In order to pull from this image, update your `Dockerfile` to use the correct
`FROM` image, such as:

```
bluestingray/upstream:11.0
```

About the Upstream Repo
======

This is the Git repo of the official Docker image for [Odoo](https://registry.hub.docker.com/_/odoo/). See the Hub page for the full readme on how to use the Docker image and for information regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs), specifically in [docker-library/docs/odoo](https://github.com/docker-library/docs/tree/master/odoo).
