FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install the "OEP EGT tagallam" plugin for ANYK
RUN wget http://www.neak.gov.hu/data/cms1030098/OEP_egt_tagallam_1_14.jar -O ~/OEP_egt_tagallam_1_14.jar \
    # -s: silent (non-gui) install
    && java -jar ~/OEP_egt_tagallam_1_14.jar -s \
    && rm ~/OEP_egt_tagallam_1_14.jar
