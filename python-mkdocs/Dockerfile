FROM python:latest

RUN mkdir /mnt/mkdocs-page && \
    pip install mkdocs && \
    pip install mkdocs-material

EXPOSE 8000/tcp

CMD mkdocs serve
