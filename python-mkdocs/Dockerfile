FROM localhost/python/pycon:latest

RUN mkdir /mnt/mkdocs-page

WORKDIR /mnt/mkdocs-page

EXPOSE 8000/tcp

CMD ["bash", "-c", "pipenv install && pipenv run mkdocs serve -a 0.0.0.0:8000"]
