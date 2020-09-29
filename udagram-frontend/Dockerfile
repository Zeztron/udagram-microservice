# Build
FROM beevelop/ionic as build

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm ci

COPY . .

RUN ionic build

# Serve
FROM nginx:alpine

COPY --from=build /usr/src/app/www /usr/share/nginx/html

