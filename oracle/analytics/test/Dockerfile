FROM docker.io/redhat/ubi8-minimal

RUN microdnf install yum
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"


RUN /usr/sbin/groupadd oracle && /usr/sbin/adduser -m -g /home/oracle -d /u01 -s /bin/bash oracle
RUN chown -R oracle:oracle /home/oracle
RUN echo 'oracle  ALL=(ALL) /bin/su' >>  /etc/sudoers

RUN  groupadd --gid 1000 alp && \
     adduser --uid 1000 --gid alp alp

USER oracle

#RUN mkdir -p /u01/setups

#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
