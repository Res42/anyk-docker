FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install 19KATA plugin for ANYK
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/19KATA/NAV_19KATA -O ~/NAV_19KATA.jar \
    # -s: silent (non-gui) install
    && java -jar ~ -s \
    && rm ~/NAV_19KATA.jar