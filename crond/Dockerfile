FROM alpine

COPY crontabs/root /var/spool/cron/crontabs/root

VOLUME ["/var/www"]

CMD ["crond"]
