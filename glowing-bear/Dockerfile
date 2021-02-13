FROM node:lts-alpine as build
RUN apk update && apk upgrade && apk add git
RUN git clone https://github.com/glowing-bear/glowing-bear.git
WORKDIR /glowing-bear
RUN npm install
RUN npm run build

FROM nginx:stable-alpine
COPY --from=build /glowing-bear/build /usr/share/nginx/html
COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
ENTRYPOINT ["nginx", "-g", "daemon off;"]