# Set a light linux distro with node pre-installed as a starting point.
FROM node:16.14.0-alpine3.15

# Change working directory to your app final destination on image file structure.
WORKDIR /nuxt3

# Copy dependencies instructions from local to image.
COPY package.json .

# Install dependencies
RUN npm install

# Copy all local project files to image.
COPY . .

# Designated to tell Nuxt to resolve a host address (Nuxt3 Docs)
ENV HOST 0.0.0.0 
# Override Chokidar pooling settings. It is important to make HMR work in WSL environment,
ENV CHOKIDAR_USEPOLLING=true
# Expose port 3000. Exposing a port in Dockerfile usually works a type of documentation between image and container authors. This port is actually published in the container settings described on docker-compose.yml.
EXPOSE 3000

# Run Nuxt3 in development mode.
CMD npm run dev 