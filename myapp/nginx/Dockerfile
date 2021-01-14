FROM nginx 
COPY . /app
COPY ./myapp/nginx/default.conf /etc/nginx/conf.d/default.conf
RUN rm -rf /app/docker
