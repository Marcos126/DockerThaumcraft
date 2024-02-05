FROM ubuntu:latest

RUN apt update && apt install -y gpg curl && apt clean

RUN curl -SsL https://playit-cloud.github.io/ppa/key.gpg | gpg --dearmor | tee /etc/apt/trusted.gpg.d/playit.gpg >/dev/null
RUN echo "deb [signed-by=/etc/apt/trusted.gpg.d/playit.gpg] https://playit-cloud.github.io/ppa/data ./" | tee /etc/apt/sources.list.d/playit-cloud.list
RUN apt update && apt install -y playit


COPY ./playit.toml /etc/playit/playit.toml

ENTRYPOINT [ "playit" ]

CMD [ "setup" ]