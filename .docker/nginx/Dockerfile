FROM nginx:1.12-alpine

ARG JH_SERVER_NAME
ARG JH_PUBLIC_DIR

COPY .docker/nginx/default.conf /etc/nginx/conf.d/default.conf
RUN sed -i -e "s,___JH_SERVER_NAME___,$JH_SERVER_NAME,g" /etc/nginx/conf.d/default.conf
RUN sed -i -e "s,___JH_PUBLIC_DIR___,$JH_PUBLIC_DIR,g" /etc/nginx/conf.d/default.conf

RUN cat /etc/nginx/conf.d/default.conf

VOLUME /etc/nginx/conf.d

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]