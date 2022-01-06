FROM docker.io/redhat/ubi8-minimal

RUN microdnf install yum
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache
RUN yum -y visudo && yum -y clean all  && rm -rf /var/cache
RUN yum -y install find && yum -y clean all  && rm -rf /var/cache
CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"

RUN /usr/sbin/groupadd oracle && /usr/sbin/adduser -m -g oracle -d /u01 -s /bin/bash oracle

RUN chown -R oracle:oracle /u01

RUN echo 'oracle  ALL=(ALL) /bin/su' >>  /etc/sudoers


RUN yum -y install wget

RUN echo '1010800000  ALL=(ALL) /bin/su' >>  /etc/sudoers
     
RUN mkdir -p /u01/app/analytics
RUN mkdir -p /u01/setups
RUN chown -R oracle:oracle /u01

USER oracle

#RUN mkdir -p /u01/setups

#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
