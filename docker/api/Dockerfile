FROM golang:1.14

WORKDIR /go/src/

RUN apt-get update \
  && apt-get install

RUN go get -u github.com/gin-gonic/gin \
  && go get github.com/jinzhu/gorm \
  && go get github.com/go-sql-driver/mysql \
  && go get github.com/codegangsta/gin \
  && go get github.com/ramya-rao-a/go-outline \
  && go get -u github.com/mdempsky/gocode \
  && go get github.com/uudashr/gopkgs/cmd/gopkgs \
  && go get -u github.com/newhook/go-symbols \
  && go get golang.org/x/tools/cmd/gorename \
  && go get -u github.com/cweill/gotests/... \
  && go get github.com/fatih/gomodifytags \
  && go get -u github.com/josharian/impl \
  && go get -u github.com/davidrjenni/reftools/cmd/fillstruct \
  && go get github.com/haya14busa/goplay/cmd/goplay \
  && go get github.com/godoctor/godoctor \
  && go get -u github.com/go-delve/delve/cmd/dlv \
  && go get -u github.com/stamblerre/gocode \
  && go get github.com/rogpeppe/godef \
  && go get -u github.com/sqs/goreturns \
  && go get golang.org/x/lint/golint \
  && apt-get install -y mariadb-client

RUN export GO111MODULE=on
RUN go get google.golang.org/grpc

RUN apt-get install unzip

# RUN PROTOC_ZIP=protoc-3.7.1-linux-x86_64.zip
RUN curl -OL https://github.com/protocolbuffers/protobuf/releases/download/v3.7.1/protoc-3.7.1-linux-x86_64.zip
RUN unzip -o protoc-3.7.1-linux-x86_64.zip -d /usr/local bin/protoc
RUN unzip -o protoc-3.7.1-linux-x86_64.zip -d /usr/local 'include/*'
RUN rm -f protoc-3.7.1-linux-x86_64.zip
RUN go get -u github.com/golang/protobuf/protoc-gen-go
