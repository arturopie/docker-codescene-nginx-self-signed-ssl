FROM debian:9
VOLUME ["/opt/codescene"]

RUN apt-get update; apt-get install -y git openjdk-8-jre
RUN apt-get install -y locales -qq && locale-gen en_US.UTF-8 en_us && dpkg-reconfigure locales && dpkg-reconfigure locales && locale-gen C.UTF-8 && /usr/sbin/update-locale LANG=C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE C.UTF-8
ENV LC_ALL C.UTF-8
ENV LC_CTYPE=C.UTF-8

RUN mkdir -p /opt/codescene
RUN mkdir -p /analysis

VOLUME /repos

ADD https://s3-eu-west-1.amazonaws.com/downloads.codescene.io/enterprise/2.3.0/codescene-enterprise-edition.standalone.jar /opt/codescene/
EXPOSE 3003
CMD ["locale"]
CMD [ "java", "-jar", "/opt/codescene/codescene-enterprise-edition.standalone.jar" ]