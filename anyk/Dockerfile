FROM danielguerra/ubuntu-xrdp:18.04
LABEL maintainer="Adam Reisinger"

# Install Java 8
RUN apt-get update && apt-get install -y \
    crudini \
    openjdk-8-jre \
    && rm -rf /var/lib/apt/lists/*

# Overwrite entrypoint bash file: removed the user creation script there
COPY ./shared/docker-entrypoint.sh /usr/bin/docker-entrypoint.sh

RUN echo "root:root" | chpasswd \
    # Create 'Desktop' folder so the ANYK installer can create a shortcut there
    && mkdir ~/Desktop \
    # Download and install ANYK
    && wget https://www.nav.gov.hu/data/cms36637/abevjava_install.jar -P ~ \
    # -s: silent (non-gui) install
    # -u: create user settings
    && java -jar ~/abevjava_install.jar -s -u \
    && rm ~/abevjava_install.jar

RUN chmod +x /usr/bin/docker-entrypoint.sh