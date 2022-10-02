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

Az image-ek alapja: <https://github.com/danielguerra69/ubuntu-xrdp>.

DockerHub: <https://hub.docker.com/r/reisingeradam/anyk>

## Docker image-ek

- ÁNYK: `reisingeradam/anyk:latest`
- ÁNYK és 19KATA (2019-es KATA bevallás): `reisingeradam/anyk:latest-19kata`
- ÁNYK és 20KATA (2020-as KATA bevallás): `reisingeradam/anyk:latest-20kata`
- ÁNYK és 19HIPA (2019-es Helyi iparűzési adó): `reisingeradam/anyk:latest-19hipa`
- ÁNYK és 20HIPA (2020-as Helyi iparűzési adó): `reisingeradam/anyk:latest-20hipa`
- ÁNYK és 21HIPA (2021-es Helyi iparűzési adó): `reisingeradam/anyk:latest-21hipa`
- ÁNYK és 22HIPAK (2022-es Helyi iparűzési adó): `reisingeradam/anyk:latest-22hipak`
- ANYK és IGAZOL (NAV igazolások: jövedelemigazolás, nemleges adóigazolás, stb): `reisingeradam/anyk:latest-igazol`
- ANYK és 2258 (2022-es 58-as nyomtatvány): `reisingeradam/anyk:latest-2258`

## Használat

Csinálj egy docker container-t az alábbi parancsokhoz hasonlóan: `docker run -p 3390:3389 reisingeradam/anyk:latest` vagy `docker run -p 3390:3389 reisingeradam/anyk:latest-20kata`.

Ha van egy `.xml` fájlod, amit be akarsz importálni, azt így lehet: `docker run -p 3390:3389 -v "<absolute path to the xml file>:/root/<file name>" reisingeradam/anyk:latest-20kata`.
Így bekerül a fájl a root home mappába.

Csatlakozz a container-hez távoli asztallal. A "számítógép" címe `localhost:3390`.

Felhasználónév/jelszó: `root`/`root`.

## Ismert problémák

### Magyar billentyűkiosztás beállítása

Lásd: <https://github.com/Res42/anyk-docker/issues/2>

Az asztalon található egy ikon `Switch to Hungarian keyboard` néven, erre kattintva átvált magyar billentyűzetkiosztásra a rendszer.

Egyébként így lehet beállítani:

1. Bal felső sarokban kattints az `Applications` menüre.
2. `Settings` → `Keyboard` almenü.
3. `Layout` fül.
4. `Use system defaults` elől szedd ki a pipát.
5. `Keyboard model`-t állítsd `Generic 105-key PC (intl.)`-re.
6. `Keyboard layout`-ot állítds `Hungarian`-ra.
7. Töröld az `English (US)`-t a `Keyboard layout` listából.
