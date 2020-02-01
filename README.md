# anyk-docker

Docker files for [ÁNYK](https://www.nav.gov.hu/nav/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/abevjava_install.html).

Built on <https://github.com/danielguerra69/ubuntu-xrdp>.

## How to use

1. Start one of the docker images with `docker-compose up`.
2. Connect with a remote desktop app to `localhost:3990` (the port may be changed in the docker-compose.yml)
3. User/password: `root`/`root`

## Docker images

- ÁNYK only: <https://github.com/Res42/anyk-docker/blob/master/anyk>
- ÁNYK and 19KATA (KATA for 2019): <https://github.com/Res42/anyk-docker/blob/master/anyk-19kata>
