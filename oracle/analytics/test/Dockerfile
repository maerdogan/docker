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

RUN gdown --id 1QWO_i64wzYs3htdfjCmyFHhE0aTIZMNM --output fmw_12c.zip
RUN gdown --id 1mEsplfS0KlXiiZXQA_fs7liJJsGphmw8 --output java8.zip
RUN gdown --id 1CTGoz1-ZYOgMGusOYi5QfzlWGdz5x95w --output analytics.zip
RUN gdown --id 18LCsiMWQT2msNdLYDweaAjHfYtVDvzSw --output apex.zip

RUN chown -R 1010800000:1010800000 /u01


#RUN mkdir -p /u01/setups

#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
