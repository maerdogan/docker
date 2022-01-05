FROM docker.io/redhat/ubi8-minimal

RUN microdnf install yum
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache




RUN /usr/sbin/addgroup -S oracle && /usr/sbin/adduser -S oracle -G oracle
RUN chown -R oracle:oracle /home/oracle/
RUN echo 'oracle  ALL=(ALL) /bin/su' >>  /etc/sudoers

RUN echo '1010800000  ALL=(ALL) /bin/su' >>  /etc/sudoers

RUN /usr/sbin/groupadd --gid 1000 alp && \
    /usr/sbin/adduser --uid 1000 --gid alp alp
     
RUN mkdir -p /u01/app/analytics
RUN mkdir -p /u01/setups
RUN chown -R oracle:oracle /u01/app/analytics
RUN chown -R oracle:oracle /u01/setups

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"

USER oracle

#RUN mkdir -p /u01/setups

#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
