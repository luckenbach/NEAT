# Base Ubuntu Precise 12.04 LTS image w/ Java 8 & Maven installed
#
FROM htaox/oracle-java8:latest
MAINTAINER htaox htaox@hotmail.com

RUN git clone https://github.com/tinkerpop/tinkerpop3.git

RUN cd tinkerpop3 && mvn clean package -DskipTests

RUN cp tinkerpop3/gremlin-server/target/gremlin-server-3.0.0-SNAPSHOT-distribution.zip /opt

RUN cd /opt && unzip gremlin-server-3.0.0-SNAPSHOT-distribution.zip

RUN ln -s /opt/gremlin-server-3.0.0-SNAPSHOT /opt/gremlin-server && cd /opt/gremlin-server

EXPOSE 8182

ADD files /root/gremlin_files
RUN chmod 700 /root/gremlin_files/default_cmd
CMD ["/root/gremlin_files/default_cmd"]
