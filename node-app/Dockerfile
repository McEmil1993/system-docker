# Use Node.js 20.14.0 as base image
FROM node:20.14.0

# Set the working directory for the main server
WORKDIR /usr/src/main-server

# Copy package.json and package-lock.json for main server
COPY ./main-server/package*.json ./

# Install dependencies for main server
RUN npm install

# Copy the remaining application code for main server
COPY . .

# Set the working directory for the additional module
WORKDIR /usr/src/lib

# Copy package.json and package-lock.json for additional module
COPY ./lib/package*.json ./

# Install dependencies for additional module
RUN npm install

# Change back to the working directory for main server
WORKDIR /usr/src/main-server

COPY ./main-server/package*.json ./

RUN npm install


# Command to start the app using 'npm run dev' for main server
CMD ["npm", "run", "dev"]