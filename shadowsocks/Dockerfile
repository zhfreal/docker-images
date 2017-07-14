FROM alpine:latest

MAINTAINER " IESoft Team <zhfreal@gmail.com>"

ENV AUTHORIZED_KEYS ***YOUR_AUTHORIZED_KEYS***
ENV TZ 'Asia/Shanghai'

RUN apk update && \
    apk upgrade && \
    apk add openssh pwgen bash tzdata && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    rm -rf /var/cache/apk/*

COPY entrypoint.sh .
COPY keygen.sh .
COPY pwgen.sh .

EXPOSE 22/tcp

CMD ["/entrypoint.sh"]
