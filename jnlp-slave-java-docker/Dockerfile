FROM cloudbees/jnlp-slave-with-java-build-tools
MAINTAINER Jeremy T. Bouse <Jeremy.Bouse@SterlingTS.com>

USER root

RUN apt-get update -qqy \
  && addgroup --system --gid 497 docker \
  && apt-get -qqy --no-install-recommends install docker.io \
  && usermod -a -G docker jenkins \
  && usermod -a -G staff jenkins

USER jenkins