FROM cloudbees/jnlp-slave-with-java-build-tools

USER root

RUN apt-get update -qqy \
  && apt-get -qqy --no-install-recommends install docker.io \
  && usermod -a -G staff jenkins

USER jenkins