FROM jenkinsci/blueocean


ENV JAVA_OPTS "-Djenkins.install.runSetupWizard=false ${JAVA_OPTS:-}"
ENV CASC_JENKINS_CONFIG /var/jenkins_conf
VOLUME /var/jenkins_conf

# RUN echo 2.0 > /usr/share/jenkins/ref/jenkins.install.UpgradeWizard.state

COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
COPY jenkins.yaml /var/jenkins_conf/jenkins.yaml
RUN install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
VOLUME /run/secrets/secrets.properties
