#we use debian as our base distro for this container
FROM debian:bullseye

#refrehs apt-get
RUN apt-get update

# Install some utilities needed by node, npm
RUN apt-get install -y curl make g++

#install node.js and npm
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs

# Install required npm packages
ADD package.json /package.json
RUN npm install

# Set /src as the working directory for this container
WORKDIR /src

# Open up external access to port 80xx

EXPOSE 8080

CMD ["node", "/src/server.js"]
