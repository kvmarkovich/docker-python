FROM alpine:3.6
MAINTAINER markos
EXPOSE 3031
VOLUME /app
WORKDIR ./app
RUN apk add --no-cache \
        uwsgi \
        uwsgi-python3 \
        python3
COPY . .
#RUN rm -rf public/*
RUN pwd
RUN ls -al
RUN pip3 install --no-cache-dir -r requirements.txt
CMD [ "uwsgi", "--plugins", "python3", \
               "--protocol", "uwsgi", \
               "--py-autoreload", "1", \
                "--ini", "uwsgi.ini"]
