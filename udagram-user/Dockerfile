# Use NodeJS base image
FROM node:13

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

ARG POSTGRES_USERNAME=$POSTGRES_USERNAME
ARG POSTGRES_PASSWORD=$POSTGRES_PASSWORD
ARG POSTGRES_HOST=$POSTGRES_HOST
ARG POSTGRES_DB=$POSTGRES_DB
ARG AWS_BUCKET=$AWS_BUCKET
ARG AWS_REGION=$AWS_REGION
ARG AWS_PROFILE=$AWS_PROFILE
ARG JWT_SECRET=$JWT_SECRET
ARG URL=$URL

RUN export POSTGRES_USERNAME=$POSTGRES_USERNAME
RUN export POSTGRES_PASSWORD=$POSTGRES_PASSWORD
RUN export POSTGRES_HOST=$POSTGRES_HOST
RUN export POSTGRES_DB=$POSTGRES_DB
RUN export AWS_BUCKET=$AWS_BUCKET
RUN export AWS_REGION=$AWS_REGION
RUN export AWS_PROFILE=$AWS_PROFILE
RUN export JWT_SECRET=$JWT_SECRET
RUN export URL=$URL

# Copy app source
COPY . .

# RUN npm run build

# Bind the port that the image will run on
EXPOSE 8100

# Define the Docker image's behavior at runtime
CMD ["npm", "run" ,"dev"]