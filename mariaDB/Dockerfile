
FROM ubuntu:18.04
MAINTAINER Ankita Chandel <ankita1.cloudcapstone@gmail.com>
RUN apt-get update && apt-get install -y gnupg2  build-essential software-properties-common
RUN apt-get update && apt-get -y upgrade && DEBIAN_FRONTEND=noninteractive
RUN sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
RUN sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el] http://mirrors.accretive-networks.net/mariadb/repo/10.3/ubuntu bionic main'
RUN apt-get update && apt-get install -y \ mariadb-server mariadb-client
RUN usermod -G 0 --append mysql
USER mysql
VOLUME /var/lib/mysql
ENTRYPOINT ["docker-entrypoint"]
CMD ["mysqld"]
