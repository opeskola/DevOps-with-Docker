FROM ubuntu:16.04

WORKDIR /mydir

RUN apt update && apt install -y curl
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash && apt install -y nodejs && npm install

COPY . /mydir

RUN npm install
ENV API_URL=http://localhost:8000

RUN useradd -m appuser
RUN chown appuser:appuser .

USER appuser

ENTRYPOINT npm start

