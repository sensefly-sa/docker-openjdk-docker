FROM openjdk:10

ENV DOCKER_VERSION 18.06.1-ce
ENV DOCKER_COMPOSE_VERSION 1.22.0

RUN apt-get update && \
    apt-get -y upgrade

# We install newest docker into our docker in docker container
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-$DOCKER_VERSION.tgz -C /usr/local/bin \
  && chmod +x /usr/local/bin/docker \
  && rm -f docker-$DOCKER_VERSION.tgz

# Install docker compose
RUN curl -fsSLO https://github.com/docker/compose/releases/download/$DOCKER_COMPOSE_VERSION/docker-compose-Linux-x86_64 \
    && cp docker-compose-Linux-x86_64 /usr/local/bin/docker-compose \
    && chmod +x /usr/local/bin/docker-compose \
    && rm -f docker-compose-Linux-x86_64
