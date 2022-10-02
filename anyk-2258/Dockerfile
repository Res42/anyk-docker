FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install 2258 plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/2258/nav_2258 -O ~/NAV_2258.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_2258.jar -s \
    && rm ~/NAV_2258.jar