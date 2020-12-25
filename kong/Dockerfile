FROM kong:2.2.1-alpine

MAINTAINER linjiancheng (sys.linjc@gmail.com)

# KONG_DATABASE: off|postgres
ENV KONG_DATABASE='off' \
KONG_PG_HOST='postgres' \
KONG_PG_PORT='1921' \
KONG_PG_USER='postgres' \
KONG_PG_PASSWORD='postgres' \
KONG_DECLARATIVE_CONFIG='/usr/local/kong/declarative/kong.yml' \
KONG_CASSANDRA_CONTACT_POINTS='postgres' \
KONG_PROXY_ACCESS_LOG='/dev/stdout' \
KONG_ADMIN_ACCESS_LOG='/dev/stdout' \
KONG_PROXY_ERROR_LOG='/dev/stderr' \
KONG_ADMIN_ERROR_LOG='/dev/stderr' \
KONG_ADMIN_LISTEN='0.0.0.0:8001, 0.0.0.0:8444 ssl' 

COPY ./conf/kong.yml /usr/local/kong/declarative/
COPY ./conf/custom_nginx.template /usr/local/kong/
COPY ./conf/bin/ /opt/docker/bin/

CMD [ "/bin/sh", "/opt/docker/bin/entrypoint.sh" ]