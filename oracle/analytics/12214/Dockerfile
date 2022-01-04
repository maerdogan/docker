ENV ORACLE_BASE=/u01/app/oracle														\
	DOMAIN_HOME=$ORACLE_BASE/wlsdomains									\			
	DOMAIN_NAME="OBIEE_OCP"															\
	ADMINSERVER_NAME="AdminServer"											\
	ADMINSERVER_UN="weblogic"														\
	ADMINSERVER_UPW="welcome1"													\
	SEC_FILE_FOLDER=$DOMAIN_HOME/$DOMAIN_NAME/servers/$ADMINSERVER_NAME/security
	

FROM docker.io/alpintosh/analytics:ol8

#COPY scripts/* /u01/oracle/scripts/
#WORKDIR /u01/oracle/scripts

#RUN  ["/u01/oracle/oracle_common/common/bin/wlst.sh","/u01/oracle/scripts/create_domain.py"]
#CMD  ["/usr/bin/mkdir -p ",$SEC_FILE_FOLDER]	
#RUN  ["/usr/bin/chmod -R 755 ",$DOMAIN_HOME]
#RUN  ["/usr/bin/chmod 755 -R ",$DOMAIN_HOME]
#CMD  ["/usr/bin/sh","/u01/oracle/scripts/start_services.sh"]	
