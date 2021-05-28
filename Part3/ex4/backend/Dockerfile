FROM golang:alpine

WORKDIR /app
ENV REQUEST_ORIGIN=http://localhost:5000
COPY . /app

RUN go build && \
    adduser -S appuser

USER appuser

EXPOSE 8080
CMD ["./server"]
