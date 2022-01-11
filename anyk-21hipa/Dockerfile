FROM reisingeradam/anyk:latest
LABEL maintainer="Agoston Kerkovits"

# Download and install 21HIPA plugin for ANYK
RUN wget https://www.nav.gov.hu/data/cms539367/NAV_21HIPA.jar -P ~ \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_21HIPA.jar -s \
    && rm ~/NAV_21HIPA.jar