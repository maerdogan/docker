FROM docker.io/redhat/ubi8

#RUN dnf -y install python3
#RUN python -m pip 
#RUN pip3 install gdown

dnf -y install telnet
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache


RUN yum -y install wget && yum -y clean all  && rm -rf /var/cache
CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"
