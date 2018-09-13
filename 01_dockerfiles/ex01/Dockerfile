FROM debian:latest
RUN apt-get update && apt-get upgrade
RUN apt-get install curl bzip2 -y

EXPOSE 9987
EXPOSE 30033
EXPOSE 10011
EXPOSE 41144

RUN curl http://dl.4players.de/ts/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 > teamspeak-server.tar.bz2 
RUN tar -xjvf teamspeak-server.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
COPY ts3server.ini /home/t3/teamspeak3-server_linux_amd64/ts3server.ini
USER ts3
ENTRYPOINT ["sh","ts3server_minimal_runscript.sh", "inifile=ts3server.ini"]