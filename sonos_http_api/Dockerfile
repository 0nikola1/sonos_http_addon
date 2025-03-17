ARG BUILD_FROM
FROM $BUILD_FROM


# Install necessary packages
RUN apk add --no-cache git nodejs npm

# Clone the Sonos HTTP API repository
RUN git clone https://github.com/jishi/node-sonos-http-api.git /app

# Install dependencies
RUN cd /app && npm install --production

COPY rootfs/ / 

WORKDIR /app
# Expose the default port
EXPOSE 5005

# Start the service using s6-overlay
CMD [ "/init" ]
