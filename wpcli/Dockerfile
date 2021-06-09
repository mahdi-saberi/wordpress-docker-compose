FROM dockerhub.ir/wordpress:cli

# Install make tool
USER root

RUN echo http://mirror.yandex.ru/mirrors/alpine/v3.6/main > /etc/apk/repositories; \
    echo http://mirror.yandex.ru/mirrors/alpine/v3.6/community >> /etc/apk/repositories; \
    echo http://mirror.yandex.ru/mirrors/alpine/v3.13/main >> /etc/apk/repositories; \
    echo http://mirror.yandex.ru/mirrors/alpine/v3.13/community >> /etc/apk/repositories; 
RUN apk add --no-cache make wget

# Make docker-compose wait for container dependencies be ready
	# Add the wait script to the image
ENV WAIT_VERSION 2.7.3
#RUN wget -e use_proxy=yes -e http_proxy=http://user:pass@ip:port https://github.com/ufoscout/docker-compose-wait/releases/download/2.7.3/wait  -O /wait
RUN chmod +x /wait

# Add Makefile to scripts dir
ADD Makefile entrypoint.sh /scripts/
RUN chmod +x /scripts/entrypoint.sh

ENTRYPOINT [ "/scripts/entrypoint.sh" ]
USER 33:33
CMD ["wp", "shell"]
