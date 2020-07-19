FROM node:alpine

WORKDIR /usr/app

# Paths relative to docker build context
# Order makes a difference in Dockerfile
# Copying only package.json first, since this would make the dependency installation not rely on every single file
# If copying everything, and then running npm install, a source code change would force npm install to run again, even if dependencies haven't changed
COPY package.json .
RUN npm install

COPY . .

CMD [ "npm", "start" ]
