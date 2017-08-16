FROM debian

RUN apt-get update && \
	apt-get install git -y && \
	apt-get install wget -y

RUN apt-get update && \
	apt-get-get install -y mysql-server mysql-client

WORKDIR /usr/local

RUN wget https://storage.googleapis.com/golang/go1.8.3.linux-amd64.tar.gz
RUN tar -xvzf go1.8.3.linux-amd64.tar.gz

ENV GOROOT=/usr/local/go
ENV GOPATH=/usr/gogs
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin

WORKDIR $GOPATH/src/github.com/gogits
RUN git clone --depth=1 -b develop https://github.com/gogits/gogs
RUN go build

EXPOSE 3000
CMD ["./gogs", "web"]
