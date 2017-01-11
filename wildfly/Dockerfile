FROM jboss/wildfly:10.1.0.Final

ENV WAIT_FOR_DB false
ENV DEPLOYMENTS /opt/jboss/wildfly/standalone/deployments/
# Standalone config
COPY standalone.conf $JBOSS_HOME/bin/
COPY application-roles.properties $JBOSS_HOME/standalone/configuration/
COPY application-users.properties $JBOSS_HOME/standalone/configuration/
COPY mgmt-groups.properties $JBOSS_HOME/standalone/configuration/
COPY mgmt-users.properties $JBOSS_HOME/standalone/configuration/
COPY start.sh /opt/jboss/

CMD ["/opt/jboss/start.sh", "/opt/jboss/wildfly/bin/standalone.sh", "-c", "standalone-full.xml", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0", "--debug"]
