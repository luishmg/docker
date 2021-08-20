# Dockerfile Repository

This repository has many Dockerfile s create with the purpose of making it easier
test different types of code without the need to modify the configuration system.

## Python environment

To create a container to do python development, just use the alias below:

```
alias pyconbuild="docker build -t python/pycon:latest https://raw.githubusercontent.com/luishmg/docker/master/python-virtual-environment/Dockerfile"
```

To run the environment you should use the command below:

```
alias pycon="docker container run --rm -it -v $PWD:/mnt/project --name pycon --entrypoint /bin/bash localhost/python/pycon:latest"
```

!!! Warning
    This command should be run inside of your project folder.
    
## mkdocs

To create a mkdocs container to test how your mkdocs page looks like you will need to make use of the aliases below:

This first alias use the [python image][pycon] above to build itself.

```
alias mkdocsbuild="docker build -t python/mkdocs:latest . -f https://raw.githubusercontent.com/luishmg/docker/master/python-mkdocs/Dockerfile"
```

This command will run your mkdocs configuration mounting the current folder were you are as the
root folder of the mkdocs page.

```
alias mkdocstest="docker container run --rm -d -p 8080:8000/tcp -v $PWD:/mnt/mkdocs-page --name mkdocs-server localhost/python/mkdocs:latest"
```

This is a troubleshooting command to get the logs from the mkdocs instance.

```
alias mkdocslogs="docker container logs -f mkdocs-server"
```

This command stops the container.

```
alias mkdocstop="docker container rm -f mkdocs-server"
```

This command generate the mkdocs base files.

```
alias mkdocsgenerate="docker container run --rm -v $PWD:/mnt/mkdocs-page --name mkdocs-gen localhost/python/mkdocs:latest pipenv install && mkdocs new ."
```

This command generate the html code and send it to the GitHub.

```
alias mkdocsgh="docker container run --rm -v $PWD:/mnt/mkdocs-page --user $(id -u):$(id -g)  --workdir=/mnt/mkdocs-page --name mkdocs-gh localhost/python/mkdocs:latest pipenv install && mkdocs gh-deploy"
```


[pycon]: ##-Python-environment
