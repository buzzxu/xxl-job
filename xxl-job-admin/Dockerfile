#docker run -it --name xxl-job -p 8080:8080 -v /data/logs/xxl-job/tomcat/logs:/usr/local/tomcat/logs buzzxu/xxl-job-admin:1.9.2-SNAPSHOT --mysql-host 192.168.1.121 --mysql-password 123 /bin/bash
FROM buzzxu/tomcat:9-slim
MAINTAINER buzzxu <downloadxu@163.com>

ARG WAR_FILE

COPY ${WAR_FILE} /job-admin.war

COPY start.sh /usr/local/tomcat/

RUN apt-get update && apt-get install -y unzip

RUN unzip -oq /job-admin.war -d job-admin \
    && mv job-admin /usr/local/tomcat/webapps/ \
    && rm -rf /job-admin.war

RUN apt-get --purge remove -y  unzip \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 8080

ENTRYPOINT ["/bin/bash","start.sh"]

