FROM debian:stable-slim
ADD https://raw.githubusercontent.com/ILoveCatto/scripts/master/entrypoint.sh ./entrypoint.sh
RUN apt update
RUN apt -y --no-install-recommends install wget curl software-properties-common apt-transport-https gnupg ca-certificates openssl git tar fontconfig tzdata iproute2 lsb-release unzip wget
RUN curl -sL https://github.com/shyiko/jabba/raw/master/install.sh | bash && . ~/.jabba/jabba.sh \
    && jabba install adopt-openj9@1.16.0-1 \
    && jabba use adopt-openj9@1.16.0-1
RUN chmod +x entrypoint.sh

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container
CMD ["/bin/sh", "/entrypoint.sh"]