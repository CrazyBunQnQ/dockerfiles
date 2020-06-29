FROM arm32v7/debian:9.12
MAINTAINER CrazyBunQnQ
CMD ["bash"] /bin/sh -c apt-get update && apt-get install -y --no-install-recommends ca-certificates curl netbase wget && rm -rf /var/lib/apt/lists/*
ADD jdk-8u251-linux-arm32-vfp-hflt.tar.gz /usr/local/
ENV JAVA_HOME /usr/local/jdk1.8.0_251
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin
ENV LANG=C.UTF-8