FROM python:3
ENV PYTHONUNBUFFERED 1
RUN mkdir /code && chmod 777 /code
ADD requirements.txt /tmp/
RUN pip3 install -r /tmp/requirements.txt
RUN useradd --uid=1000 djangouser
USER djangouser
WORKDIR /code
