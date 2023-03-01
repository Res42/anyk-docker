FROM reisingeradam/anyk:latest
LABEL maintainer="Adam Reisinger"

# Download and install the OEP EU Card plugin for ANYK
RUN wget "http://www.neak.gov.hu/pfile/file?path=/nyomtatvanytar/nyomtatvanytar/emagyarorszag/NEAK_igenylolap_eu_kartyahoz&inline=true" -O ~/OEP_igenylolap_eu_kartyahoz_1_4.jar \
    # -s: silent (non-gui) install
    && java -jar ~/OEP_igenylolap_eu_kartyahoz_1_4.jar -s \
    && rm ~/OEP_igenylolap_eu_kartyahoz_1_4.jar
