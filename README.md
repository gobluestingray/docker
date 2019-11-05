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

The upstream repo is the Git repo of the official Docker image for [Odoo](https://registry.hub.docker.com/_/odoo/). See the Hub page for the full readme on how to use the Docker image and for information regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs), specifically in [docker-library/docs/odoo](https://github.com/docker-library/docs/tree/master/odoo).

Building and Running Images from this Repo
======

This is a minimal repo with a directory for building each version of Odoo. If a
directory does not have a `docker-compose.yml`, then you will need to add a
basic one, as described in [Odoo's Docker Hub instructions](https://hub.docker.com/_/odoo)
section titled **Docker Compose examples**.

Assuming the version has a `docker-compose.yml`, then the build process looks
like this:

```
> git clone https://github.com/gobluestingray/docker
> cd docker/11.0
> docker-compose build
```

Once the container builds successfully, you can run the container:

```
> docker-compose up -d
```

The Odoo instance can be accessed at at `localhost:8069` (or whatever port is
defined in the `docker-compose.yml` or `Dockerfile` for that version). If you're
not sure, you can use `docker-compose ps` to help you. In the example below, the
Odoo instance would be accessible at `0.0.0.0:8069` (same as `localhost:8069`).

```
> docker-compose ps
  Name                 Command                 State                Ports
------------------------------------------------------------------------------------
docker_db_1    docker-entrypoint.sh postgres   Up      5432/tcp
docker_web_1   /entrypoint.sh odoo             Up      0.0.0.0:8069->8069/tcp, 8071/tcp
```

Tagging and Pushing Images to Docker Hub
======

See [the relevant section of the `odoo_images` repository](https://github.com/gobluestingray/odoo_images/#pushing-images-to-docker-hub).
