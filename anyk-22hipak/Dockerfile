FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install 22HIPAK plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/22hipak/nav_22hipak -O ~/NAV_22HIPAK.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_22HIPAK.jar -s \
    && rm ~/NAV_22HIPAK.jar