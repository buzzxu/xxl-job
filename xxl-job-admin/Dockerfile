FROM buzzxu/tomcat:9-slim

MAINTAINER buzzxu <downloadxu@163.com>

RUN mkdir -p /data/applogs/xxl-job/

ARG WAR_FILE

COPY ${WAR_FILE} /usr/local/tomcat/webapps/job-admin.war