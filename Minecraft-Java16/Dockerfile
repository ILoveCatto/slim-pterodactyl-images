FROM debian:stable-slim

RUN apt update
RUN apt -y --no-install-recommends install curl software-properties-common apt-transport-https gnupg ca-certificates openssl git tar fontconfig tzdata iproute2 lsb-release unzip wget
RUN curl -sL https://github.com/shyiko/jabba/raw/master/install.sh | bash && . ~/.jabba/jabba.sh \
    && jabba install adopt-openj9@1.16.0-1 \
    && jabba use adopt-openj9@1.16.0-1
RUN curl https://raw.githubusercontent.com/ILoveCatto/slim-pterodactyl-images/master/Minecraft-Java16/entrypoint.sh

USER container
ENV  USER=container HOME=/home/container

WORKDIR /home/container

CMD ["/bin/bash", "/entrypoint.sh"]