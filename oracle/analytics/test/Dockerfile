FROM docker.io/redhat/ubi8-minimal

RUN microdnf install yum
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"



RUN addgroup -S oracle && adduser -S oracle -G oracle
RUN chown -R oracle:oracle /home/oracle/
RUN echo 'oracle  ALL=(ALL) /bin/su' >>  /etc/sudoers


RUN mkdir -p /u01/setups
RUN yum -y install wget

RUN chmod -R 755 oracle:oracle /u01/
#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
USER oracle
