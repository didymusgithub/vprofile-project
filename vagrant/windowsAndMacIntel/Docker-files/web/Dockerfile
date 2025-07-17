FROM nginx:latest
LABEL "project"="vprofile"
LABEL "Author"="Techwithdidier"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf
