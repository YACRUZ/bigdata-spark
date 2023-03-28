#os
FROM debian:bullseye

#run apt-get
RUN apt-get update

# Install some utilities needed by node, npm.
RUN apt-get install -y curl make g++

# Install Node.js and npm.
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs

# Add package .json
ADD package.json /package.json
RUN npm install

WORKDIR /src

EXPOSE 8080

# Run startup command.
CMD ["node", "/src/server.js"]
