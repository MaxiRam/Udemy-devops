FROM jenkins/jenkins
USER root
# Define variables
ENV MAVEN_VERSION 3.9.4

# Update base OS and install addtional tools
RUN apt update && apt install -y wget
RUN wget --no-verbose https://dlcdn.apache.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz -P /tmp/
RUN tar xzf /tmp/apache-maven-$MAVEN_VERSION-bin.tar.gz -C /opt/
RUN ln -s /opt/apache-maven-$MAVEN_VERSION /opt/maven
RUN ln -s /opt/maven/bin/mvn /usr/local/bin
RUN rm /tmp/apache-maven-$MAVEN_VERSION-bin.tar.gz

# Set up permissions
RUN chown jenkins:jenkins /opt/maven;
ENV MAVEN_HOME=/opt/mvn
USER jenkins