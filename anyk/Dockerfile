FROM danielguerra/ubuntu-xrdp:18.04
LABEL maintainer="Adam Reisinger"

# Install Java 8
RUN apt-get update && apt-get install -y \
    openjdk-8-jre \
    && rm -rf /var/lib/apt/lists/* && apt-get clean -y

RUN echo "root:root" | chpasswd \
    # Create 'Desktop' folder so the ANYK installer can create a shortcut there
    && mkdir ~/Desktop \
    # Download and install ANYK
    && wget https://nav.gov.hu/pfile/programFile?path=/nyomtatvanyok/letoltesek/nyomtatvanykitolto_programok/nyomtatvany_apeh/keretprogramok/AbevJava -O ~/abevjava_install.jar \
    # -s: silent (non-gui) install
    # -u: create user settings
    && ls -la \
    && ls -la ~ \
    && java -jar ~/abevjava_install.jar -s -u \
    && rm ~/abevjava_install.jar

COPY ./files/hun-keyboard.sh /usr/bin/hun-keyboard.sh
COPY ./files/hun-keyboard.desktop /root/Desktop/hun-keyboard.desktop
RUN chmod +x /usr/bin/hun-keyboard.sh

# Overwrite entrypoint bash file: removed the user creation script there
COPY ./files/docker-entrypoint.sh /usr/bin/docker-entrypoint.sh
RUN chmod +x /usr/bin/docker-entrypoint.sh
