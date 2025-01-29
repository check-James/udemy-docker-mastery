# Use Node.js 6.x Alpine image as the base
FROM node:6-alpine

# Expose port 80 inside the container
EXPOSE 80

# Install tini for process management
RUN apk add --no-cache tini

# Set the working directory for the app
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package.json /usr/src/app
RUN npm install && npm cache clean --force

# Copy all app files into the image
COPY . /usr/src/app

# Use tini as the init system and start the app
CMD ["/sbin/tini", "--", "node", "./bin/www"]
# NOTE: The instructions are now in the README.md file in this directory.
