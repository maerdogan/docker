FROM docker.io/redhat/ubi8:8.5


RUN dnf install yum
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache
RUN mkdir -p /u01/setups
RUN yum -y install wget

USER ROOT

RUN addgroup oracle
RUN usermod -a -G oracle oracle
RUN usermod -g root oracle
# Chown all the files to the app user.
RUN chown -R oracle:oracle /u01
CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"

RUN usermod -a -G root oracle
USER oracle
#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
