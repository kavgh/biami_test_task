FROM openjdk:8-jre-buster
WORKDIR /opt/biami
ADD ./resources/20230412_biami.tar.gz .
COPY ./resources/core_run.sh /usr/local/bin
RUN mkdir ./bin/env && chmod +x /usr/local/bin/core_run.sh
WORKDIR /opt/biami/bin/core
VOLUME [ "/opt/biami/bin/env", "/opt/biami/bin/temp" ]
CMD [ "/bin/bash" ]