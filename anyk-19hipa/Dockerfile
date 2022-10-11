FROM reisingeradam/anyk:latest
LABEL maintainer="Dezso Burjan"

# Download and install 19HIPA plugin for ANYK         
RUN wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvanykitolto_programok_nav/19HIPA/NAV_19HIPA -O ~/NAV_19HIPA.jar \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_19HIPA.jar -s \
    && rm ~/NAV_19HIPA.jar
