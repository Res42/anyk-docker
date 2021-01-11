FROM reisingeradam/anyk:2.98.0
LABEL maintainer="Adam Reisinger"

# Download and install 20HIPA plugin for ANYK
RUN wget https://www.nav.gov.hu/data/cms508913/NAV_20HIPA.jnlp -P ~ \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_20HIPA.jar -s \
    && rm ~/NAV_20HIPA.jar