FROM docker.io/redhat/ubi8

RUN dnf -y install python3
#RUN python -m pip 
RUN pip3 install gdown
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"

RUN yum -y install wget

RUN echo '1010800000  ALL=(ALL) /bin/su' >>  /etc/sudoers
     
RUN mkdir -p /u01/app/analytics
RUN mkdir -p /u01/setups

WORKDIR /u01/setups

### JDK & FMW FILES
RUN gdown --id 1QWO_i64wzYs3htdfjCmyFHhE0aTIZMNM --output fmw_12c.jar
RUN gdown --id 1mEsplfS0KlXiiZXQA_fs7liJJsGphmw8 --output java8_301.tar.gz
RUN gdown --id 1CTGoz1-ZYOgMGusOYi5QfzlWGdz5x95w --output analytics_5.9.0.jar
RUN gdown --id 1NsYf7nsVcpLJFCwq2eAUWMRXcZ7J3ge- --output installation_files.zip

### DB FILES
RUN gdown --id 18LCsiMWQT2msNdLYDweaAjHfYtVDvzSw --output apex.zip
RUN gdown --id 18uDj7gebBK2PH9IZ14ukva9kXOk9GJY3 --output oracledb_21c.zip

RUN chown -R 1010800000:1010800000 /u01


#RUN mkdir -p /u01/setups

#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
