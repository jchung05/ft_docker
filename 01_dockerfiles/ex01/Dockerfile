FROM debian

RUN apt-get update; \
	apt-get upgrade -y; \
	apt-get install -y wget bzip2; \
	wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2; \
	tar -vxjf teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2;

EXPOSE 9987/udp 30033 10011

WORKDIR /teamspeak3-server_linux_amd64

CMD ./ts3server_minimal_runscript.sh
