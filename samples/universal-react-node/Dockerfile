ROM node:carbon-alpine

# ENV Variables
ENV DIR /usr/src/app
# ENV NODE_ENV=production

# Create App Dir
RUN mkdir -p $DIR

# Set Working Dir
WORKDIR $DIR

# Copy App Codebase
COPY . $DIR

# Install APP Dependencies
RUN npm install

# Cleanup
RUN rm -f .npmrc

# Build process
RUN npm run build
RUN $DIR/node_modules/.bin/clap mps

# Run APP
CMD npm run prod

EXPOSE 3000
