#Empty Wildfly application server

This image contains empty Wildfly 10.1 server.
What is added in comparison to jboss/wildfly:10.1.0.Final
* Deploy dir - possibility do copy your war file easily to deployment directory  with COPY target/your-app.war $DEPLOY_DIR
* Timezone configuration - using enviroment variable to setup container timezone (Default timezone Europe/Prague) `docker run -d --name wildfly -p 8080:8080 -e TZ=America/Toronto tonda100/wildfly-empty`
* Garbage Collector log - gc.log in folder /opt/jboss/wildfly/standalone/log/
* Heap Dump on OOO - dump will be in /opt/jboss/wildfly/standalone/log/wildfly.hprof file
Can be started with command:

`docker run -d --name wildfly -p 8080:8080 tonda100/wildfly-empty`

##Building of an image

Clone the repository from [GitHub](https://github.com/tonda100/wildfly-empty)

`docker build -t tonda100/wildfly-empty .`