FROM python:latest

RUN mkdir /mnt/mkdocs-page && \
    pip install mkdocs && \
    pip install mkdocs-material

WORKDIR /mnt/mkdocs-page

EXPOSE 8000/tcp

CMD cd /mnt/mkdocs-page; mkdocs serve
