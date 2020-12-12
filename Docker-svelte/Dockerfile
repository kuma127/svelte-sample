FROM node:10

RUN apt update
RUN mkdir /code
WORKDIR /code
COPY . /code/

ENTRYPOINT ["sh", "/code/Docker-svelte/start-server.sh"]