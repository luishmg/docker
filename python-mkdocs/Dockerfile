FROM docker.io/python:latest

COPY ./requirements.txt /tmp/

RUN mkdir /mnt/mkdocs-page && \
    pip install -r /tmp/requirements.txt

WORKDIR /mnt/mkdocs-page

EXPOSE 8000/tcp

CMD ["mkdocs", "serve", "-a", "0.0.0.0:8000"]
