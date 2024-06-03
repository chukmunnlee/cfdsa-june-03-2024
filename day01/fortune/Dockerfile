ARG NODE_VERSION=22-bullseye
# Set the runtime
FROM node:${NODE_VERSION}

## Build the application

# Create and CD into directory
WORKDIR /app
# Inside /app directory

# Copy all sources into the image
COPY package.json .
COPY package-lock.json .
COPY main.js .
COPY public public
COPY views views

# Install the dependencies
RUN npm ci

## Run the application

# Environment variable used by the application
ENV APP_PORT=3000 

# Ports the application bind to
EXPOSE ${APP_PORT}

# Run the application
ENTRYPOINT node main.js