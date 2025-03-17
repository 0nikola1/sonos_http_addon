ARG BUILD_FROM
FROM $BUILD_FROM

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Install necessary packages
RUN apk add --no-cache nodejs npm

# Clone the Sonos HTTP API repository
RUN git clone https://github.com/jishi/node-sonos-http-api.git /app

# Install dependencies
RUN cd /app && npm install --production

# Expose the default port
EXPOSE 5005

# Start the service
CMD ["node", "/app/server.js"]
