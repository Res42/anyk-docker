[![hu](https://img.shields.io/badge/lang-hu-green.svg)](https://github.com/Res42/anyk-docker/blob/master/README.md)
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/Res42/anyk-docker/blob/master/README.en.md)

**Only as a last resort. First check if the form can be submitted with the [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/).**
(Yes, the KATA form can be submitted there.)

To determine if the form you would like to use is available to be submitted via the ONYA, look up the form at the [NAV website](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav):

- if there is a button on the form's details page that says "Online Nyomtatványkitöltő Alkalmazásban (ONYA) is elérhető" the form should be submitted via the [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/).  
   e.g.: ![form available at ONYA](https://user-images.githubusercontent.com/2495806/159995313-2e5b39d9-5230-4ee7-ab01-207da801f585.png)
- if there is no such button the form can only be submitted via ÁNYK.  
   e.g.: ![form available only for ÁNYK](https://user-images.githubusercontent.com/2495806/159995784-5e1e22b0-f2d0-4197-95c1-6c1ae004f4e7.png)

We will only accept a merge request for a new ÁNYK form which cannot be submitted with ONYA.

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
- ÁNYK and 21HIPA (Local business tax for 2021): `reisingeradam/anyk:latest-21hipa`
- ANYK and IGAZOL (Tax agency certificates): `reisingeradam/anyk:latest-igazol`
- ANYK and 2258 (Form 58 for 2022): `reisingeradam/anyk:latest-2258`

## How to use

Run the following command: `docker run -p 3390:3389 reisingeradam/anyk:latest` or `docker run -p 3390:3389 reisingeradam/anyk:latest-20kata`.

Or if you have an `.xml` file to import into the ÁNYK: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/root/<file name>" reisingeradam/anyk:latest-20kata`.
With this the XML will be in the root home directory.

Connect with a remote desktop app to `localhost:3390` (the port may be changed in the docker run command or in the docker-compose.yml).

User/password: `root`/`root`.

## Known issues

### How to change the keyboard layout to Hungarian

See: <https://github.com/Res42/anyk-docker/issues/2>

There is an icon on the desktop named `Switch to Hungarian keyboard`, if you use this icon then the system will change the keyboard layout to Hungarian.

Or if you prefer setting it manually:

1. Click `Applications` in the top left corner of the desktop.
2. Click `Settings` → `Keyboard`.
3. Switch to the `Layout` tab.
4. Remove the check from `Use system defaults`.
5. Set the `Keyboard model` to `Generic 105-key PC (intl.)`.
6. Add `Hungarian` to the `Keyboard layout` list.
7. Remove `English (US)` from the `Keyboard layout` list.
