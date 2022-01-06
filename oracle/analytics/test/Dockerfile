FROM docker.io/redhat/ubi8

RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"

RUN yum -y install wget

RUN echo '1010800000  ALL=(ALL) /bin/su' >>  /etc/sudoers
     
RUN mkdir -p /u01/app/analytics
RUN mkdir -p /u01/setups
RUN chown -R 1010800000:1010800000 /u01


#RUN mkdir -p /u01/setups

#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
