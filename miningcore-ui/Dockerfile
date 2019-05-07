FROM nginx:stable

RUN apt update && apt install -y git

RUN rm -rf /usr/share/nginx/html
RUN git clone https://gitlab.com/calvintam236/miningcore-ui.git /usr/share/nginx/html
RUN sed -i 's/localhost:4000/web.habs.no/' /usr/share/nginx/html/assets/js/miningcore-ui.js

