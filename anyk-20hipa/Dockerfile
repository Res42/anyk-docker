FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install 20HIPA plugin for ANYK
RUN wget https://www.nav.gov.hu/data/cms508913/NAV_20HIPA.jar -P ~ \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_20HIPA.jar -s \
    && rm ~/NAV_20HIPA.jar