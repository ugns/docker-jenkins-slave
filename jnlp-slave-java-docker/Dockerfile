FROM cloudbees/jnlp-slave-with-java-build-tools
MAINTAINER Jeremy T. Bouse <Jeremy.Bouse@SterlingTS.com>

USER root

# Install Docker and setup docker GID group membership for jenkins
# Install jQuery and create jq-linux64 symlink
# Upgrade aws-cli
RUN apt -qqy update \
  && apt -qqy upgrade \
  && pip install --upgrade awscli
  && apt -qqy autoremove \
  && addgroup --system --gid 497 docker \
  && apt -qqy --no-install-recommends install docker.io jq \
  && usermod -a -G docker jenkins \
  && usermod -a -G staff jenkins \
  && ln -sf /usr/bin/jq /usr/bin/jq-linux64 \
  && rm -rf /var/lib/apt/lists/*

USER jenkins