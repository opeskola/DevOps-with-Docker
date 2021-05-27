FROM golang:1.16

WORKDIR /mydir
ENV PORT=8080
ENV REQUEST_ORIGIN=http://localhost:5000
COPY . .

RUN go build
RUN go test ./...
RUN useradd -m appuser

USER appuser

EXPOSE ${PORT}
CMD ["./server"]
