FROM reisingeradam/anyk:latest
LABEL maintainer="Agoston Kerkovits"

# Download and install 21HIPA plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/21HIPA/NAV_21HIPA -O ~/NAV_21HIPA.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_21HIPA.jar -s \
    && rm ~/NAV_21HIPA.jar
