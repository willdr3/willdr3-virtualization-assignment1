FROM python:2.7
MAINTAINER Dan Williamson
ENV REFRESHED_AT 30/08/2016

RUN apt-get -qqy update

ADD . /flaskApp
WORKDIR /flaskApp

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

RUN uwsgi --build-plugin https://github.com/unbit/uwsgi-consul

ENTRYPOINT ["uwsgi", "--ini", "uwsgi-consul.ini", "--ini", "uwsgi-consul.ini:curlyserver"]
CMD []
