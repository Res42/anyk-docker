FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install IGAZOL plugin for ANYK
RUN wget https://nav.gov.hu/data/cms276234/NAV_IGAZOL.jar -P ~ \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_IGAZOL.jar -s \
    && rm ~/NAV_IGAZOL.jar