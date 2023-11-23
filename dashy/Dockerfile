ARG BUILD_FROM=lissy93/dashy:latest
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

VOLUME ["/app"]

# Finally, run start command to serve up the built application
CMD [ "yarn", "start" ]

# Expose the port
EXPOSE ${PORT}

# Run simple healthchecks every 5 mins, to check that everythings still great
HEALTHCHECK --interval=5m --timeout=5s --start-period=30s CMD yarn health-check

# Labels
LABEL \
  io.hass.name="${BUILD_NAME}" \
  io.hass.description="${BUILD_DESCRIPTION}" \
  io.hass.arch="${BUILD_ARCH}" \
  io.hass.type="addon" \
  io.hass.version=${BUILD_VERSION} \
  maintainer="Benoit Anastay <benoit@anastay.dev>" \
  org.opencontainers.image.title="${BUILD_NAME}" \
  org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
  org.opencontainers.image.vendor="Home Assistant Community Add-ons" \
  org.opencontainers.image.authors="Benoit Anastay <benoit@anastay.dev>" \
  org.opencontainers.image.licenses="MIT" \
  org.opencontainers.image.url="https://anastay.dev" \
  org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
  org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
  org.opencontainers.image.created=${BUILD_DATE} \
  org.opencontainers.image.revision=${BUILD_REF} \
  org.opencontainers.image.version=${BUILD_VERSION}