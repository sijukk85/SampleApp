FROM centos

ENV TERM=xterm-256color

yum install -y \
	python python-virtualenv

RUN virtualenv /appenv && \
	. /appenv/bin/activate && \
	pip install pip --upgrade

ADD scripts/entrypoint.sh /usr/lcoal/bin/entrypoint.sh
RUN chmod +x /usr/lcoal/bin/entrypoint.sh

ENTRYPOINT ["entrypoint.sh"]


