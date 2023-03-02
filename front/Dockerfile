FROM node:18.13.0-bullseye

ENV CHOKIDAR_USEPOLLING=true
ENV WATCHPACK_POLLING=true
ENV FAST_REFRESH=true

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install locales -y
RUN apt-get install -y tzdata
RUN npm install -g npm@9.2.0

# Language configuration
RUN echo "America/Recife" > /etc/timezone
RUN sed -i -e 's/# pt_BR.UTF-8 UTF-8/pt_BR.UTF-8 UTF-8/' /etc/locale.gen && \locale-gen
RUN dpkg-reconfigure -f noninteractive tzdata

RUN mkdir /workspace
# COPY package.json /workspace
WORKDIR /workspace