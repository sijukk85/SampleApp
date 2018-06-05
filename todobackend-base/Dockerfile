FROM centos

ENV TERM=xterm-256color

RUN yum install -y \
	python python-virtualenv

RUN virtualenv /appenv && \
	. /appenv/bin/activate && \
	pip install pip --upgrade

ADD scripts/entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

ENTRYPOINT ["entrypoint.sh"]


