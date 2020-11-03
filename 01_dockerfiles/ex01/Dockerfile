FROM debian:9.3

RUN apt-get update -y && apt-get upgrade -y && apt -y install wget && apt-get -y install bzip2

# télécharger la dernière version disponible
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2
# Extraction de l'archive
RUN tar -xvf teamspeak3-server_linux_amd64-3.6.1.tar.bz2

ENV TS3SERVER_LICENSE=accept

EXPOSE 9987/udp 10011 30033 41144
# 9987 default voice
# 10011 server query
# 30033 file transport

CMD /teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start

# docker build -t teamspeeeaaak .
# docker run -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -p 41144:41144 -d teamspeeeaaak