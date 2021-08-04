FROM docker.io/python:latest

RUN mkdir /mnt/mkdocs-page && \
    pip install mkdocs && \
    pip install mkdocs-material

WORKDIR /mnt/mkdocs-page

EXPOSE 8000/tcp

CMD ["mkdocs", "serve", "-a", "0.0.0.0:8000"]
