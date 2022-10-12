FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install 20HIPA plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/20HIPA/NAV_20HIPA -O ~/NAV_20HIPA.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_20HIPA.jar -s \
    && rm ~/NAV_20HIPA.jar
