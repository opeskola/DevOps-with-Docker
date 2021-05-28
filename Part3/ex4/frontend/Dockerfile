FROM ubuntu:18.04

WORKDIR /mydir

ENV API_URL=http://localhost:8000

COPY . /mydir

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_14.x | bash && apt-get install -y nodejs && npm install && \
    apt-get purge -y --auto-remove curl && \ 
    rm -rf /var/lib/apt/lists/* && \
    useradd -m appuser && \
    chown appuser:appuser .    

USER appuser

ENTRYPOINT npm start

