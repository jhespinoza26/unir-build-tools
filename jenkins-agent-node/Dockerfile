FROM jenkins/inbound-agent as agent

FROM node:14.17.0-alpine3.13

RUN apk -U add openjdk11-jre docker git make

COPY --from=agent /usr/local/bin/jenkins-agent /usr/local/bin/jenkins-agent
COPY --from=agent /usr/share/jenkins/agent.jar /usr/share/jenkins/agent.jar

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]