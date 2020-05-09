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
RUN npm install -g ionic

# Copy app source
COPY . .

# Run ionic
RUN ionic build

# Bind the port that the image will run on
EXPOSE 8100

# Define the Docker image's behavior at runtime
ENTRYPOINT ["ionic"]
CMD ["serve", "8100", "--address", "0.0.0.0"]
