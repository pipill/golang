FROM pipill/armhf-golang:1.8

RUN [ "cross-build-start" ]

RUN mkdir -p /go/src/app

RUN [ "cross-build-end" ]

WORKDIR /go/src/app

# this will ideally be built by the ONBUILD below ;)
CMD ["go-wrapper", "run"]

ONBUILD COPY . /go/src/app
ONBUILD RUN go-wrapper download
ONBUILD RUN go-wrapper install
