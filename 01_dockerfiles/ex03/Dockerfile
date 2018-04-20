FROM debian

RUN apt-get update;
RUN apt-get upgrade -y;
RUN apt-get install git wget -y;

WORKDIR $HOME/local
RUN wget https://storage.googleapis.com/golang/go1.8.linux-amd64.tar.gz
RUN tar -xzvf go1.8.linux-amd64.tar.gz

ENV GOROOT=$HOME/local/go
ENV GOPATH=$HOME/gogs
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin
RUN mkdir -p $GOPATH/src/github.com/gogits
RUN cd $GOPATH/src/github.com/gogits
RUN go get -u github.com/gogits/gogs

WORKDIR $GOPATH/src/github.com/gogits/gogs
RUN go build

ENV USER=root

EXPOSE 3000

CMD ["./gogs", "web"]
