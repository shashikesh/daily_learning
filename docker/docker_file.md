### 📦 Dockerfile Instructions Cheat Sheet

Below is a list of common Dockerfile instructions used to build Docker images.

``` Dockerfile
# Base image
FROM ubuntu:20.04

# Maintainer info (Deprecated - use LABEL instead)
# MAINTAINER Your Name <your@email.com>

# Metadata
LABEL maintainer="Your Name <your@email.com>"

# Build-time variable
ARG APP_VERSION=1.0

# Environment variable
ENV NODE_ENV=production

# Set working directory
WORKDIR /usr/src/app

# Copy files
COPY . .

# Add files (can also handle remote URLs and archives)
ADD https://example.com/app.tar.gz /tmp/

# Run shell commands
RUN apt-get update && apt-get install -y curl

# Create a mountable volume
VOLUME ["/data"]

# Expose port
EXPOSE 3000

# Define the user to run as
USER node

# Default command
CMD ["node", "server.js"]

# Entrypoint (can be combined with CMD)
ENTRYPOINT ["docker-entrypoint.sh"]

# Health check
HEALTHCHECK --interval=30s CMD curl -f http://localhost:3000 || exit 1

# Change default shell (for RUN, CMD, etc.)
SHELL ["/bin/bash", "-c"]

# ONBUILD triggers for base images
ONBUILD RUN echo "This runs when used as a base image"
