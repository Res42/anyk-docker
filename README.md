**Csak végső esetben. Előbb nézd meg, hogy az [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/)ban elérhető az adott nyomtatvány.**
(Igen, a KATA bevallások elérhetőek.)

# anyk-docker

Docker files for [ÁNYK](https://www.nav.gov.hu/nav/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/abevjava_install.html).

Built on <https://github.com/danielguerra69/ubuntu-xrdp>.

DockerHub: <https://hub.docker.com/r/reisingeradam/anyk>

## Known issues

### How to change the keyboard layout to Hungarian

1. Click `Applications` in the top left corner of the desktop.
2. Click `Settings` --> `Keyboard`.
3. Switch to the `Layout` tab.
4. Remove the check from `Use system defaults`.
5. Set the `Keyboard model` to `Generic 105-key PC (intl.)`.
6. Add `Hungarian` to the `Keyboard layout` list.
7. Remove `English (US)` from the `Keyboard layout` list.

## How to use without downloading the repository

Run the following command: `docker run -p 3390:3389 reisingeradam/anyk:latest` or `docker run -p 3390:3389 reisingeradam/anyk:latest-20kata`.

Or if you have an `.xml` file to import into the ÁNYK: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/root/<file name>" reisingeradam/anyk:latest-20kata`. With this the XML will be in the root home directory.

## How to run locally

1. Start one of the docker images with `docker-compose up`.
2. Connect with a remote desktop app to `localhost:3990` (the port may be changed in the docker-compose.yml)
3. User/password: `root`/`root`

## Docker images

- ÁNYK only: <https://github.com/Res42/anyk-docker/tree/master/anyk>
- ÁNYK and 19KATA (KATA for 2019): <https://github.com/Res42/anyk-docker/tree/master/anyk-19kata>
- ÁNYK and 20KATA (KATA for 2020): <https://github.com/Res42/anyk-docker/tree/master/anyk-20kata>
- ÁNYK and 20HIPA (Helyi iparuzesi ado for 2020): <https://github.com/Res42/anyk-docker/tree/master/anyk-20hipa>
