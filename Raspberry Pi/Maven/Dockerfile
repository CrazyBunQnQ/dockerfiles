FROM crazybun/arm-oracle-jdk:8u251
MAINTAINER CrazyBunQnQ
CMD ["bash"] /bin/sh -c apt-get update && apt-get install -y --no-install-recommends ca-certificates curl netbase wget && rm -rf /var/lib/apt/lists/*
ADD apache-maven-3.6.3-bin.tar.gz /tmp/apache-maven.tar.gz
RUN mkdir -p /usr/share/maven /usr/share/maven/ref && \
    mv /tmp/apache-maven.tar.gz/apache-maven-3.6.3/* /usr/share/maven && \
    rm -rf /tmp/apache-maven.tar.gz && \
    ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
ENV MAVEN_HOME=/usr/share/maven
ENV MAVEN_CONFIG=/root/.m2
