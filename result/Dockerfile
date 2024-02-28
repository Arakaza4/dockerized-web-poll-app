# Use Node 12 alpine as parent image
FROM node:12-alpine

# Change the working directory on the Docker image to /app
WORKDIR /app

# Copy all app to the /app directory
COPY package.json .
COPY . .

# Install dependencies

RUN npm install

RUN npm -v
RUN npm pack 

RUN tar -xzvf result-1.0.0.tgz --strip-components=3


# Expose application port
# EXPOSE 4242
EXPOSE 80

# Start the application
CMD ["npm", "start","app.js"]
