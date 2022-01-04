FROM docker.io/redhat/ubi8:8.5


RUN microdnf install yum
RUN yum -y install zip && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip && yum -y clean all  && rm -rf /var/cache
RUN mkdir -p /u01/setups
RUN yum -y install wget
#COPY analytics/setups/* /u01/setups/
#WORKDIR /u01/setups
