FROM ubuntu

RUN apt-get update && \
  apt-get install -y openjdk-8-jdk-headless && \
  apt-get install unzip -y && \
  apt-get install wget -y

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app/

RUN wget http://download.jboss.org/wildfly/15.0.1.Final/wildfly-15.0.1.Final.tar.gz && \
  tar -xvzf wildfly-15.0.1.Final.tar.gz && \
  sed -i 's#<inet-address value="${jboss\.bind\.address:127\.0\.0\.1}"/>#<any-address/>#g' /usr/src/app/wildfly-15.0.1.Final/standalone/configuration/standalone.xml

CMD /usr/src/app/wildfly-15.0.1.Final/bin/standalone.sh
