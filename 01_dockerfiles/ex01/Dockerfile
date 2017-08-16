FROM debian

RUN apt-get -y update && apt-get -y upgrade && \
	apt-get -y install apt-utils && \
	apt-get -y install bzip2 wget ca-certificates && \
	apt-get -y install curl && \
	useradd teamspeak

WORKDIR /home/t3

RUN curl http://dl.4players.de/ts/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 > teamspeak-server.tar.bz2 && \
	tar -xjfv teamspeak-server.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

USER teamspeak

EXPOSE 9987/udp
EXPOSE 30033
EXPOSE 10011

ENTRYPOINT ["sh", "ts3server_minimal_runscrpit.sh"]
