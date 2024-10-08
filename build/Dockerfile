ARG DESKTOP

FROM lscr.io/linuxserver/rdesktop:ubuntu-$DESKTOP AS base

ARG DOWNLOAD_URL

# Update (Firefox, CA, curl, tzdata), install packages (Java 8 for ANYK) and set timezone
RUN apt-get update && apt-get --only-upgrade -y install firefox ca-certificates curl tzdata \
    && apt-get install -y openjdk-8-jre \
    && ln -fs /usr/share/zoneinfo/Europe/Budapest /etc/localtime \
    && dpkg-reconfigure -f noninteractive tzdata \
    && apt-get autoremove -y && apt-get clean -y && rm -rf /tmp/* /var/lib/apt/lists/* /var/tmp/* /var/log/*

RUN echo "Installing..." \
    # Create 'Desktop' folder for user 'root' so the ANYK installer can create a shortcut there
    && mkdir /root/Desktop \
    # Download and install ANYK
    && curl $DOWNLOAD_URL -o ~/abevjava_install.jar \
    # -s: silent (non-gui) install
    # -u: create user settings
    && java -jar ~/abevjava_install.jar -s -u \
    && rm ~/abevjava_install.jar \
    # Change rights to default user 'abc'
    && chown -R abc:abc /usr/share/abevjava/ \
    && chown -R abc:abc /root/.abevjava/ \
    && chown abc:abc /etc/abevjavapath.cfg \
    # Create 'Desktop' folder for default user
    && mkdir /config/Desktop \
    # Copy the ANYK shortcut to the user Desktop
    && cp /root/Desktop/ÁNYK.desktop /config/Desktop/

RUN echo "[Desktop Entry]" > /etc/xdg/autostart/setxkbmap.desktop \
    && echo "Type=Application" >> /etc/xdg/autostart/setxkbmap.desktop \
    && echo "Name=SetKeyBoard HU" >> /etc/xdg/autostart/setxkbmap.desktop \
    && echo "Comment=Sets the keyboard to HU" >> /etc/xdg/autostart/setxkbmap.desktop \
    && echo "Hidden=false" >> /etc/xdg/autostart/setxkbmap.desktop \
    && echo "X-MATE-Autostart-enabled=true" >> /etc/xdg/autostart/setxkbmap.desktop \
    && echo "Exec=setxkbmap -layout hu -model pc105" >> /etc/xdg/autostart/setxkbmap.desktop

FROM reisingeradam/anyk:base-ubuntu-$DESKTOP AS plugin

ARG DOWNLOAD_URL

RUN curl $DOWNLOAD_URL -o ~/plugin.jar \
    # -s: silent (non-gui) install
    && java -jar ~/plugin.jar -s \
    && rm ~/plugin.jar \
    # Change rights to default user
    && chown -R abc:abc /usr/share/abevjava/
