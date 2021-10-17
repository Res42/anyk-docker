[![hu](https://img.shields.io/badge/lang-hu-green.svg)](https://github.com/Res42/anyk-docker/blob/master/README.md)
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/Res42/anyk-docker/blob/master/README.en.md)

**Only as a last resort. First check if the form can be submitted with the [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/).**
(Yes, the KATA form can be submitted there.)

To determine if the form you would like to use is aviable to be submitted via the ONYA, look up the form at the [NAV website](https://nav.gov.hu/nav/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav):
* if the result shows a link in red that says "Online felületen is beküldhető" the form should be submitted via the [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/).
    e.g.: ![form available at ONYA](https://user-images.githubusercontent.com/2495806/137081509-c4195714-f842-4e8c-8f92-da034d06e4f4.png)
* if there is no such link the form can only be submitted via ÁNYK.
    e.g.: ![form available only for ÁNYK](https://user-images.githubusercontent.com/2495806/137081596-247d9e58-a0cc-4dea-a5a9-346a7ee48f6c.png)

# anyk-docker

Docker files for [ÁNYK](https://www.nav.gov.hu/nav/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/abevjava_install.html).

Built on <https://github.com/danielguerra69/ubuntu-xrdp>.

DockerHub: <https://hub.docker.com/r/reisingeradam/anyk>.

## Docker images

- ÁNYK only: `reisingeradam/anyk:latest`
- ÁNYK and 19KATA (KATA for 2019): `reisingeradam/anyk:latest-19kata`
- ÁNYK and 20KATA (KATA for 2020): `reisingeradam/anyk:latest-20kata`
- ÁNYK and 19HIPA (Local business tax for 2019): `reisingeradam/anyk:latest-19hipa`
- ÁNYK and 20HIPA (Local business tax for 2020): `reisingeradam/anyk:latest-20hipa`
- ANYK and IGAZOL (Tax agency certificates): `reisingeradam/anyk:latest-igazol`

## How to use

Run the following command: `docker run -p 3390:3389 reisingeradam/anyk:latest` or `docker run -p 3390:3389 reisingeradam/anyk:latest-20kata`.

Or if you have an `.xml` file to import into the ÁNYK: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/root/<file name>" reisingeradam/anyk:latest-20kata`.
With this the XML will be in the root home directory.

Connect with a remote desktop app to `localhost:3990` (the port may be changed in the docker run command or in the docker-compose.yml).

User/password: `root`/`root`.

## Known issues

### How to change the keyboard layout to Hungarian

1. Click `Applications` in the top left corner of the desktop.
2. Click `Settings` → `Keyboard`.
3. Switch to the `Layout` tab.
4. Remove the check from `Use system defaults`.
5. Set the `Keyboard model` to `Generic 105-key PC (intl.)`.
6. Add `Hungarian` to the `Keyboard layout` list.
7. Remove `English (US)` from the `Keyboard layout` list.
