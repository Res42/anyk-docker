FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install IGAZOL plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/igazol/NAV_igazol.jar -O ~/NAV_IGAZOL.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_IGAZOL.jar -s \
    && rm ~/NAV_IGAZOL.jar