FROM jenkins/inbound-agent as agent

FROM maven:3.8.4-jdk-11-slim

RUN apt-get update && \
    apt-get install -y \
    git \
    libfontconfig1 \
    libfreetype6

COPY --from=agent /usr/local/bin/jenkins-agent /usr/local/bin/jenkins-agent
COPY --from=agent /usr/share/jenkins/agent.jar /usr/share/jenkins/agent.jar

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]