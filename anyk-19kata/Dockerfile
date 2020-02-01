FROM reisingeradam/anyk:2.94.0
LABEL maintainer="Adam Reisinger"

# Download and install 19KATA plugin for ANYK
RUN wget https://www.nav.gov.hu/data/cms489660/NAV_19KATA.jar -P ~ \
    # -s: silent (non-gui) install
    && java -jar ~/NAV_19KATA.jar -s \
    && rm ~/NAV_19KATA.jar
