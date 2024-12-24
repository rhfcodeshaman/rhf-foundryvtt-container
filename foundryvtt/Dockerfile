# This container is currently set up using Alpine
# It is my intention to try several other Linux distros
# to increase performance. Distros to try:
# Ubuntu
# Drauger
# Mint
FROM node:16-alpine

#Environment variables for User and Group IDs
ENV UID=1000
ENV GID=1000

# Removing node user and its home dir,
# Adding Group and User
RUN deluser --remove-home node
RUN addgroup -g $GID foundry 
RUN adduser $UID -G foundry -D foundry

# Making neccessary directories
RUN mkdir -p /home/foundry/data
RUN mkdir -p /home/foundry/app

# Setting the working directory for Foundry
# and then copying the parent directory to the
# working directory
WORKDIR /home/foundry/app
COPY . .

# Exposing the appropriate port
EXPOSE 30000

# Setting the dataPath and running main.js in headless mode
CMD ["node", "./resources/app/main.js," "--headless", "--dataPath=/home/foundry/data"]