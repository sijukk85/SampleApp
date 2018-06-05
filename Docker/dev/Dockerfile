FROM jyothis/todobackend-base:latest

RUN yum -y install python-devel

RUN . /appenv/bin/activate &&\
    pip install wheel --upgrade

ENV WHEELHOUSE=/wheelhouse PIP_WHEEL_DIR=/wheelhouse PIP_FIND_LINKS=/wheelhouse XDG_CACHE_HOME=/cache

VOLUME /wheelhouse

VOLUME /reports

COPY script/test.sh /usr/local/bin/test.sh
RUN chmod +x /usr/lcoal/bin/test.sh

ENTRYPOINT ["test.sh"]
RUN ["python", "manage.py", "test", "--noinput"]

COPY src /application
WORKDIR /application



