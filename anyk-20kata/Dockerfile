FROM reisingeradam/anyk:2.98.0
LABEL maintainer="Adam Reisinger"

# Download and install 20KATA plugin for ANYK
RUN wget https://www.nav.gov.hu/data/cms511172/NAV_20KATA.jar -P ~ \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_20KATA.jar -s \
    && rm ~/NAV_20KATA.jar