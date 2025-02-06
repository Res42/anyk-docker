[![hu](https://img.shields.io/badge/lang-hu-green.svg)](https://github.com/Res42/anyk-docker/blob/master/README.md)
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/Res42/anyk-docker/blob/master/README.en.md)

**Only as a last resort. First check if the form can be submitted with the [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/).**
(Yes, the KATA form can be submitted there.)

To determine if the form you would like to use is available to be submitted via the ONYA, look up the form at the [NAV website](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav):

- if there is a button on the form's details page that says "Online Nyomtatványkitöltő Alkalmazásban (ONYA) is elérhető" the form should be submitted via the [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/).  
   e.g.: ![form available at ONYA](https://user-images.githubusercontent.com/2495806/159995313-2e5b39d9-5230-4ee7-ab01-207da801f585.png)
- if there is no such button the form can only be submitted via ÁNYK.  
   e.g.: ![form available only for ÁNYK](https://user-images.githubusercontent.com/2495806/159995784-5e1e22b0-f2d0-4197-95c1-6c1ae004f4e7.png)

We will only accept a merge request for a new ÁNYK form which cannot be submitted with [ONYA](https://onya.nav.gov.hu/) or with [MO](https://mo.hu/).

# anyk-docker

Docker files for [ÁNYK](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/AbevJava).

Built on <https://github.com/linuxserver/docker-rdesktop>.

DockerHub: <https://hub.docker.com/r/reisingeradam/anyk>.

## Docker images

The ubuntu multiplatform (amd64, arm64) images are available with 3 different desktop environments (Xfce, KDE and MATE) with the following image tags in the `reisingeradam/anyk` DockerHub repository:

| Description                                                                                                                                                                                                                                                    | Xfce                                                                                     | KDE                     | MATE                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ----------------------- | ------------------------ |
| [ÁNYK](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/AbevJava)                                                                                                                                      | `base-ubuntu-xfce`                                                                       | `base-ubuntu-kde`       | `base-ubuntu-mate`       |
| [ÁNYK and 19HIPA (Local business tax for 2019)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/19HIPA)                                                                                              | `nav19hipa-ubuntu-xfce`                                                                  | `nav19hipa-ubuntu-kde`  | `nav19hipa-ubuntu-mate`  |
| [ÁNYK and 20HIPA (Local business tax for 2020)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/20HIPA)                                                                                              | `nav20hipa-ubuntu-xfce`                                                                  | `nav20hipa-ubuntu-kde`  | `nav20hipa-ubuntu-mate`  |
| [ÁNYK and 21HIPA (Local business tax for 2021)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/21HIPA)                                                                                              | `nav21hipa-ubuntu-xfce`                                                                  | `nav21hipa-ubuntu-kde`  | `nav21hipa-ubuntu-mate`  |
| [ÁNYK and 22HIPAK (Local business tax for 2022)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/22hipak)                                                                                            | `nav22hipak-ubuntu-xfce`                                                                 | `nav22hipak-ubuntu-kde` | `nav22hipak-ubuntu-mate` |
| [ÁNYK and 23HIPAK (Local business tax for 2023)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/23HIPAK)                                                                                            | `nav23hipak-ubuntu-xfce`                                                                 | `nav23hipak-ubuntu-kde` | `nav23hipak-ubuntu-mate` |
| [ÁNYK and 24HIPAK (Local business tax for 2024)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/24HIPAK)                                                                                            | `nav24hipak-ubuntu-xfce`                                                                 | `nav24hipak-ubuntu-kde` | `nav24hipak-ubuntu-mate` |
| [ANYK and IGAZOL (Tax agency certificates)](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/igazol)                                                                                                  | `navigazol-ubuntu-xfce`                                                                  | `navigazol-ubuntu-kde`  | `navigazol-ubuntu-mate`  |
| [ANYK and OEP-EGT-TAGALLAM (Form for a Hungarian citizen with a TAJ number who is an insured person in an EEA member state)](https://neak.gov.hu/felso_menu/lakossagnak/ellatas_magyarorszagon/jogosultsag_az_ellatasra/kulfoldon_munkat_vallalok_bejelentese) | `oepegt-ubuntu-xfce`                                                                     | `oepegt-ubuntu-kde`     | `oepegt-ubuntu-mate`     |
| [ANYK and OEPEUCARD (European Health Insurance Card)](https://neak.gov.hu/felso_menu/lakossagnak/ellatas_kulfoldon/az_europai_egeszsegbiztositasi_kartya)                                                                                                      | [Available online](https://mo.hu/szuf_ugyleiras?id=8a523149-1ef3-4270-8462-c12585cafbc9) | Removed                 | -                        |

## How to use

Run the following command: `docker run -p 3390:3389 reisingeradam/anyk:base-ubuntu-xfce` or `docker run -p 3390:3389 reisingeradam/anyk:nav22hipak-ubuntu-xfce`.

Or if you have a `.xml` file to import into the ÁNYK: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/config/<file name>" reisingeradam/anyk:nav22hipak-ubuntu-xfce`.
With this the XML will be in the root home directory.

Connect with a remote desktop app to `localhost:3390` (the port may be changed in the docker run command or in the docker-compose.yml).

User/password: `abc`/`abc`.

### seccomp config

In some cases an extra parameter is needed to properly run the container, see <https://github.com/Res42/anyk-docker/issues/98>.

The example commands with this new parameter: `docker run -p 3390:3389 --security-opt seccomp=unconfined reisingeradam/anyk:base-ubuntu-xfce` or `docker run -p 3390:3389 --security-opt seccomp=unconfined reisingeradam/anyk:nav22hipak-ubuntu-xfce`.
