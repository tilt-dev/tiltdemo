FROM golang:1.10

WORKDIR /go/src/github.com/windmilleng/tiltdemo/cmd/demoserver2

ADD ./cmd .

RUN go install github.com/windmilleng/tiltdemo/cmd/demoserver2

ENTRYPOINT /go/bin/demoserver2
