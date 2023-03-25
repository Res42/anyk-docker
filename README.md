[![hu](https://img.shields.io/badge/lang-hu-green.svg)](https://github.com/Res42/anyk-docker/blob/master/README.md)
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/Res42/anyk-docker/blob/master/README.en.md)

**Csak végső esetben. Előbb nézd meg, hogy az [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/)ban elérhető az adott nyomtatvány.**
(Igen, a KATA bevallások elérhetőek.)

Ha szeretnéd megnézni, hogy a nyomtatványod elérhető-e ONYA-n keresztül, keress rá a [NAV weboldalán](https://nav.gov.hu/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav):

- ha a nyomtatvány részletes oldalán látod az "Online Nyomtatványkitöltő Alkalmazásban (ONYA) is elérhető" gombot, add be a [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/)-on.
  ![ONYA-ban beküldhető nyomtatvány](https://user-images.githubusercontent.com/2495806/159995313-2e5b39d9-5230-4ee7-ab01-207da801f585.png)
- ha nincs ilyen gomb, akkor marad az ÁNYK.  
  ![csak ÁNYK-ban beküldhető nyomtatvány](https://user-images.githubusercontent.com/2495806/159995784-5e1e22b0-f2d0-4197-95c1-6c1ae004f4e7.png)

Csak olyan ÁNYK nyomtatványhoz készült merge requestet fogadunk el, amit nem lehet az ONYA-ból elérni.

# anyk-docker

Docker image-ek [ÁNYK](https://www.nav.gov.hu/nav/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/abevjava_install.html)-hoz.

Az image-ek alapja: <https://github.com/linuxserver/docker-rdesktop>.

DockerHub: <https://hub.docker.com/r/reisingeradam/anyk>

## Docker image-ek

Az ubuntu multiplatform (amd64, arm64) imagek igény szerint elérhetőek 3 féle desktop felülettel (Xfce, KDE és MATE) a kővetkező image tag-ekkel a `reisingeradam/anyk` DockerHub repositoryban:

| Leírás                                                                                                                              | Xfce                     | KDE                     | MATE                     |
|-------------------------------------------------------------------------------------------------------------------------------------|--------------------------|-------------------------|--------------------------|
| ÁNYK                                                                                                                                | `base-ubuntu-xfce`       | `base-ubuntu-kde`       | `base-ubuntu-mate`       |
| ÁNYK és 19HIPA (2019-es Helyi iparűzési adó)                                                                                        | `nav19hipa-ubuntu-xfce`  | `nav19hipa-ubuntu-kde`  | `nav19hipa-ubuntu-mate`  |
| ÁNYK és 20HIPA (2020-as Helyi iparűzési adó)                                                                                        | `nav20hipa-ubuntu-xfce`  | `nav20hipa-ubuntu-kde`  | `nav20hipa-ubuntu-mate`  |
| ÁNYK és 21HIPA (2021-es Helyi iparűzési adó)                                                                                        | `nav21hipa-ubuntu-xfce`  | `nav21hipa-ubuntu-kde`  | `nav21hipa-ubuntu-mate`  |
| ÁNYK és 22HIPAK (2022-es Helyi iparűzési adó)                                                                                       | `nav22hipak-ubuntu-xfce` | `nav22hipak-ubuntu-kde` | `nav22hipak-ubuntu-mate` |
| ANYK és IGAZOL (NAV igazolások: jövedelemigazolás, nemleges adóigazolás, stb)                                                       | `navigazol-ubuntu-xfce`  | `navigazol-ubuntu-kde`  | `navigazol-ubuntu-mate`  |
| ANYK és OEPEUCARD (Európai Egészségbiztosítási Kártya)                                                                              | `oepegt-ubuntu-xfce`     | `oepegt-ubuntu-kde`     | `oepegt-ubuntu-mate`     |
| ANYK és OEP-EGT-TAGALLAM (Bejelentő lap TAJ számmal rendelkező magyar állampolgár részére, aki EGT tagállamban biztosított személy) | `oepeucard-ubuntu-xfce`  | `oepeucard-ubuntu-kde`  | `oepeucard-ubuntu-mate`  |

## Használat

Csinálj egy docker container-t az alábbi parancsokhoz hasonlóan: `docker run -p 3390:3389 reisingeradam/anyk:base-ubuntu-xfce` vagy `docker run -p 3390:3389 reisingeradam/anyk:nav22hipak-ubuntu-xfce`.

Ha van egy `.xml` fájlod, amit be akarsz importálni, azt így lehet: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/config/<file name>" reisingeradam/anyk:nav22hipak-ubuntu-xfce`.
Így bekerül a fájl a config home mappába.

Csatlakozz a container-hez távoli asztallal. A "számítógép" címe `localhost:3390`.

Felhasználónév/jelszó: `abc`/`abc`.
