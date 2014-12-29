# docker-maven - Oracle Java 8 + Maven 3.2.5

Docker image  containing Oracle Java 8 and Maven 3.2.5

## Running
The simplest way to run it is like this

```bash
docker run -ti joeygibson/maven mvn [maven options....]
```

But something like this is better. It will map the local directory to /usr/local/project, cd into it, and execute Maven on the project.

```bash
docker run --rm=true \
	-v $(pwd):/usr/local/project \
	-v $HOME/.m2/repository:/usr/local/m2-repo \
	joeygibson/maven bash -l -c "cd /usr/local/project && mvn -Dmaven.repo.local=/usr/local/m2-repo clean package"
```

