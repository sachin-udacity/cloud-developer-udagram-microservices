# Use NodeJS base image
FROM node:13

# Create app directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Run audit
RUN npm audit fix

# Copy app source
COPY . .


# TypeScript
RUN npm run tsc

# Bind the port that the image will run on
EXPOSE 8080

# Define the Docker image's behavior at runtime
CMD ["npm", "run", "dev"]
