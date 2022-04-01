FROM adoptopenjdk/openjdk11-openj9:jdk-11.0.11_9_openj9-0.26.0-ubi

COPY yum.repos.d/centos8.repo /etc/yum.repos.d/centos8.repo
RUN dnf install -y libX11 libXext libXrender libjpeg xz xorg-x11-fonts-Type1 xorg-x11-fonts-75dpi git-core \
    && dnf install -y \
        https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox-0.12.6-1.centos8.x86_64.rpm \
        https://download.docker.com/linux/centos/8/x86_64/stable/Packages/docker-scan-plugin-0.17.0-3.el8.x86_64.rpm \
        https://download.docker.com/linux/centos/8/x86_64/stable/Packages/docker-ce-cli-20.10.13-3.el8.x86_64.rpm \
    && dnf clean all \
    && rm -rf /var/cache/yum \
    # See https://docs.openshift.com/container-platform/3.9/creating_images/guidelines.html
    && mkdir /app \
    && chgrp -R 0 /app \
    && chmod -R g=u /app \
    && useradd pdfuser

