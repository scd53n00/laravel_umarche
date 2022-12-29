FROM httpd:latest

ARG USER="laravel"
ARG UID="1000"
ARG GROUP="laravel"
ARG GID="1000"
ARG WORKSPACE="/usr/local/apache2/"
ARG LOGDIR="/var/log/"
ARG USERSPACE="/home/laravel/"

WORKDIR $WORKSPACE

RUN groupadd -g $GID $GROUP && useradd -m -s /bin/bash -u $UID -g $GID $USER
RUN usermod -u $UID $USER && groupmod -g $GID $GROUP
RUN chown -R $UID:$GID $WORKSPACE
RUN chown -R $UID:$GID $LOGDIR
RUN chown -R $UID:$GID $USERSPACE

COPY ./conf /usr/local/apache2/conf/
EXPOSE 80