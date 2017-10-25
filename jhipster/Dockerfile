FROM jboss/keycloak:3.3.0.CR1

ENV KEYCLOAK_USER=admin \
    KEYCLOAK_PASSWORD=admin

COPY ./realm-config /opt/jboss/keycloak/realm-config

EXPOSE 9080 9443 10990

CMD ["-b", "0.0.0.0", "-Dkeycloak.migration.action=import", "-Dkeycloak.migration.provider=dir", "-Dkeycloak.migration.dir=/opt/jboss/keycloak/realm-config", "-Dkeycloak.migration.strategy=OVERWRITE_EXISTING", "-Djboss.socket.binding.port-offset=1000"]