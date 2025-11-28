FROM ubuntu:latest

RUN apt-get update && \
    apt-get install -y fortune fortunes-min && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

CMD ["/usr/games/fortune"]