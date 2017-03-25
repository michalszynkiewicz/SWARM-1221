FROM fedora:25

RUN dnf install -y java-1.8.0-openjdk git maven mc vim unzip \
&& cd /tmp && git clone https://github.com/michalszynkiewicz/SWARM-1221.git test \
&& git clone https://github.com/wildfly-swarm/wildfly-swarm.git swarm

WORKDIR /tmp/test

ENTRYPOINT pushd /tmp/swarm && mvn clean install -DskipTests \ 
&& popd && pushd /tmp/test && mvn clean install && /bin/bash
