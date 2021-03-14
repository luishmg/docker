FROM python:latest

RUN mkdir /mnt/files && \
    pip install simple-http-server

WORKDIR /mnt/files

EXPOSE 80/tcp

ENTRYPOINT python -m http.server -d "/mnt/files" 80
