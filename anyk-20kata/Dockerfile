FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install 20KATA plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/20KATA/NAV_20KATA.jar -O ~/NAV_20KATA.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_20KATA.jar -s \
    && rm ~/NAV_20KATA.jar