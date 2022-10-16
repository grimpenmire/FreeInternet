FROM neilpang/acme.sh

RUN apk add --no-cache docker-cli
ADD start.sh /start.sh

EXPOSE 80/tcp

ENTRYPOINT ["/start.sh"]
CMD ["daemon"]
