# docker-odoo

## Requirements

### Docker

Install Docker by packagemanager

`apt-get install docker`

### Docker Compose

Install Docker Compose by Python pip. To get latest stable version.

`pip3 install docker-compose`

## Project Bootstrap

1. Fork this repo to `<PROJECT>-docker-odoo`
2. `git clone <PROJECT>-docker-odoo`
3. cd `<PROJECT>-docker-odoo`
4. Edit `docker-compose.yml`. Change (Odoo) ports mapping.
5. Edit `docker/db/Dockerfile`.
    - Change **PostreSQL** version.
6. Edit `docker/odoo/Dockerfile`
    - Change **Ubuntu** version
    - Add/change OS and Python packages

## Build (init)

Following commands/actions can run at same time.

1. `./init`
2. Put the Odoo sources under `<PROJECT>-docker-odoo/odoo`
    - `git clone <GIT-REPO>`
3. Put the Odoo addons (custom, external) under `<PROJECT>-docker-odoo/addons`

## Start services (run)

- `./run`

## Wkhtmltopdf

In case of troubles (layout, styling), rename or remove the `report.url` System parameter.

## Python debugger (pdb)

The debugger is running inside the container, so we need to attach into the container to use it.

1. Find the container id using docker container ps and copy the first two or three letters of the container id column.
2. Use the command `docker attach CONTAINER_ID` to attach to the container.

Ensure following are set in `docker-compose.yml`:

```
stdin_open: true
tty: true
```

## (?) Filesystem mapping Docker Container => Host

Following on host:

- Edit: `/etc/docker/daemon.json`
`{'userns-remap': 'bob'}`

Check uid/groupid user. Change to 1000000 (very big int).

- Edit: `/etc/subuid`
`bob:<UID>:1000000`

- Edit: `/etc/subgid`
bob:<GID>:1000000
