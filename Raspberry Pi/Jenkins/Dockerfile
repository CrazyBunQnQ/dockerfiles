FROM crazybun/maven:3.6.3
ARG CrazyBunQnQ

EXPOSE 8080

RUN apt-get update; apt-get --yes install \
    apt-transport-https \
    curl \
    git \
    ca-certificates \
    gnupg-agent \
    software-properties-common && \
    curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
    add-apt-repository "deb [arch=armhf] https://download.docker.com/linux/debian $(lsb_release -cs) stable" && \
    apt-get update && \
    apt-get --yes install \
    docker-ce docker-ce-cli containerd.io && \
    apt-get clean && apt-get autoremove -q && \
    rm -rf /var/lib/apt/lists/* /usr/share/doc /usr/share/man /tmp/*

# 设置镜像时区环境变量, 并设置时区
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ENV JENKINS_HOME /usr/local/jenkins

RUN mkdir -p /usr/local/jenkins
RUN useradd --no-create-home --shell /bin/sh jenkins
RUN chown -R jenkins:jenkins /usr/local/jenkins/
#ADD http://mirrors.jenkins-ci.org/war-stable/latest/jenkins.war /usr/local/jenkins.war
ADD jenkins.war /usr/local/jenkins.war
RUN chmod 644 /usr/local/jenkins.war

CMD ["java", "-jar", "/usr/local/jenkins.war"]