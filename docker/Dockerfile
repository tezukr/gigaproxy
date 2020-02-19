FROM nginx:alpine

RUN ls -lah /

COPY ./public/index.html /usr/share/nginx/html
COPY ./docker/nginx.conf /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
