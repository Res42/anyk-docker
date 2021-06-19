[![hu](https://img.shields.io/badge/lang-hu-green.svg)](https://github.com/Res42/anyk-docker/blob/master/README.md)
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/Res42/anyk-docker/blob/master/README.en.md)

**Csak végső esetben. Előbb nézd meg, hogy az [Online Nyomtatványkitöltő Alkalmazás](https://onya.nav.gov.hu/)ban elérhető az adott nyomtatvány.**
(Igen, a KATA bevallások elérhetőek.)

# anyk-docker

Docker image-ek [ÁNYK](https://www.nav.gov.hu/nav/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/abevjava_install.html)-hoz.

Az image-ek alapja: <https://github.com/danielguerra69/ubuntu-xrdp>.

DockerHub: <https://hub.docker.com/r/reisingeradam/anyk>

## Docker image-k

- ÁNYK: `reisingeradam/anyk:latest`
- ÁNYK és 19KATA (2019-es KATA bevallás): `reisingeradam/anyk:latest-19kata`
- ÁNYK és 20KATA (2020-as KATA bevallás): `reisingeradam/anyk:latest-20kata`
- ÁNYK és 20HIPA (2020-as Helyi iparűzési adó): `reisingeradam/anyk:latest-20hipa`
- ANYK és IGAZOL (NAV igazolások: jövedelemigazolás, nemleges adóigazolás, stb): `reisingeradam/anyk:latest-igazol`

## Használat

Csinálj egy docker container-t az alábbi parancsokhoz hasonlóan: `docker run -p 3390:3389 reisingeradam/anyk:latest` vagy `docker run -p 3390:3389 reisingeradam/anyk:latest-20kata`.

Ha van egy `.xml` fájlod, amit be akarsz importálni, azt így lehet: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/root/<file name>" reisingeradam/anyk:latest-20kata`.
Így bekerül a fájl a root home mappába.

Csatlakozz a container-hez távoli asztallal. A "számítógép" címe `localhost:3990`.

Felhasználónév/jelszó: `root`/`root`.

## Ismert problémák

### Magyar billentyűkiosztás beállítása

1. Bal felső sarokban kattints az `Applications` menüre.
2. `Settings` → `Keyboard` almenü.
3. `Layout` fül.
4. `Use system defaults` elől szedd ki a pipát.
5. `Keyboard model`-t állítsd `Generic 105-key PC (intl.)`-re.
6. `Keyboard layout`-ot állítds `Hungarian`-ra.
7. Töröld az `English (US)`-t a `Keyboard layout` listából.
