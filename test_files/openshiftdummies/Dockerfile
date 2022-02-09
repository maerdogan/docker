FROM ubi8 AS builder
RUN mkdir /disk
WORKDIR /disk
RUN curl --silent --remote-name $(dnf config-manager --dump image-to-include | awk '/baseurl =/{print $3}')
RUN chmod 0444 /disk/*
RUN chown 107:107 /disk/*

FROM scratch
COPY --from=builder /disk/* /disk/
LABEL com.redhat.component="rhel-guest-image-container" \
      com.redhat.source_code="https://access.redhat.com/downloads/content/479/ver=/rhel---8/x86_64/product-sources" \
      name="container-native-virtualization/rhel-guest-image-container" \
      version="8.5.0" \
      summary="RHEL guest image container" \
      io.openshift.expose-services="" \
      io.openshift.tags="cnv" \
      io.k8s.display-name="rhel-guest-image-container" \
      maintainer="tgunders@redhat.com" \
      description="RHEL guest image container"

RUN dnf -y install python3
#RUN python -m pip 
RUN pip3 install gdown
RUN yum -y install zip      && yum -y clean all  && rm -rf /var/cache
RUN yum -y install unzip    && yum -y clean all  && rm -rf /var/cache
RUN yum -y install telnet   && yum -y clean all  && rm -rf /var/cache  
RUN yum -y install mlocate  && yum -y clean all  && rm -rf /var/cache

#CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"
