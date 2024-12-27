# Use the official Node.js image as a base image
FROM node:18

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Set the React app to run on port 7070
ENV PORT=7070

# Start the React development server
CMD ["npm", "start"]

# Expose the port React will run on
EXPOSE 7070
