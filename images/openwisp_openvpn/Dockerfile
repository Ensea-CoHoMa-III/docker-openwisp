# hadolint ignore=DL3007
FROM kylemanna/openvpn:dev

RUN apk add --no-cache \
            curl~=7.79.1-r1 \
            tzdata~=2022a-r0 \
            supervisor~=4.2.0-r0 && \
    rm -rf /var/cache/apk/* /tmp/*
CMD ["sh", "init_command.sh"]
EXPOSE 1194

ENV MODULE_NAME=openvpn \
    DASHBOARD_APP_SERVICE=dashboard \
    DASHBOARD_INTERNAL=dashboard.internal \
    API_INTERNAL=api.internal \
    DB_NAME=openwisp_db \
    TZ=UTC \
    DB_USER=admin \
    DB_PASS=admin \
    DB_HOST=postgres \
    DB_PORT=5432 \
    DB_SSLMODE=disable \
    DB_SSLKEY=None \
    DB_SSLCERT=None \
    DB_SSLROOTCERT=None \
    DB_OPTIONS={} \
    TOPLOGY_UPDATE_INTERVAL=3

# hadolint ignore=DL3045
COPY ./common/init_command.sh \
    ./common/utils.sh \
    ./openwisp_openvpn/ ./
