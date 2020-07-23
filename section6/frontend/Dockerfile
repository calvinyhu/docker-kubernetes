FROM node:alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
EXPOSE 80
COPY --from=0 /app/build /usr/share/nginx/html
