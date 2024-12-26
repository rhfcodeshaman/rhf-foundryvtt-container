# This container is currently set up using Alpine
# It is my intention to try several other Linux distros
# to increase performance. Distros to try:
# Ubuntu
# Drauger
# Mint
FROM node:23-alpine

# Need to open path to the internet so that this set of commands can work
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
RUN source .bashrc
RUN nvm install --lts

# Get the latest foundryvtt build
ADD latest /foundryvtt

# Set datapath for node.js
ENTRYPOINT ["node", "/foundryvtt/resources/app/main.js", "--dataPath=/data"]