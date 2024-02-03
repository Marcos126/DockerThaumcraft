FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /hosteanding

RUN apt-get update && apt-get install -y wget

RUN wget -O playit https://github.com/playit-cloud/playit-agent/releases/download/v0.15.11/playit-linux-amd64

RUN chmod +x playit

ENTRYPOINT [ "./playit" ]
