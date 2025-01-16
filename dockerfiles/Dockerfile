FROM alpine:latest
RUN mkdir /opt/biami /env && apk update && apk add openjdk8-jre expect
WORKDIR /opt/biami
ADD ./resources/20230412_biami.tar.gz .
COPY ./resources/core_run.sh /usr/local/bin
COPY ./resources/expect.exp .
RUN chmod 755 /usr/local/bin/core_run.sh ./expect.exp && expect ./expect.exp
VOLUME [ "/env", "./bin/temp" ]
RUN apk del expect && rm ./expect.exp
ENTRYPOINT [ "core_run.sh" ]
CMD [ "--context_param", "cmd=import", "--context_param", "cmd=update" ]