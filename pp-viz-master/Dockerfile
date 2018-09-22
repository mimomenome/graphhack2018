# note that order matters in terms of docker build layers. Least changed near start to most changed...
# This image will be based on the official nodejs docker image
FROM node:7.1.0

EXPOSE 80

# Commands will run in this directory
RUN mkdir /srv/theLink
WORKDIR /srv/theLink

####################
# Web Frontend Stuff

# Add key build files
#ADD ./server.js server.js

# Copy the code for the prod container.
# This seems to not cause any problems in dev when we mount a volume at this point.
COPY ./heatmap app

# Install Dependencies
RUN npm install
RUN ./node_modules/bower/bin/bower install --config.interactive=false --allow-root

# We just run the app when we start.
CMD ["npm", "start"]
