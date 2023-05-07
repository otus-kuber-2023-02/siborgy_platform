FROM nginx:1.23.4-alpine-slim

ARG USER=www
ARG UID=1001
ARG GID=1001

RUN adduser -D -u ${UID} ${USER}
RUN mkdir -p /var/run/nginx && chown -R "${UID}:${GID}" /var/run/nginx

COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /app
COPY --chown=${UID}:${GID} ./app /app

EXPOSE 8000

CMD ["nginx", "-g", "daemon off;"]