FROM jenkinsci/blueocean as base
ENV JAVA_OPTS "-Djenkins.install.runSetupWizard=false ${JAVA_OPTS:-}"
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN install-plugins.sh < /usr/share/jenkins/ref/plugins.txt

FROM base
ENV CASC_JENKINS_CONFIG /var/jenkins_conf
VOLUME /var/jenkins_conf
COPY jenkins.yaml /var/jenkins_conf/jenkins.yaml
