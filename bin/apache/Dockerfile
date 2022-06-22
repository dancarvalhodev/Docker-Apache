FROM httpd:2.4-bullseye

RUN apt update && apt dist-upgrade -y
RUN apt update && apt install -y nano

CMD  [ "httpd", "-D", "FOREGROUND"]