FROM python:3

RUN apt update

RUN useradd -m -d /app backend
USER backend

COPY ./requirements.txt /app/requirements.txt
WORKDIR /app
RUN pip3 install -r requirements.txt
COPY . /app
RUN sh start.sh

CMD [ "/app/.local/bin/gunicorn", "wsgi:app", "-b", "0.0.0.0:8000" ]
