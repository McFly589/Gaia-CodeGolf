## Gaia-CodeGolf

This is my solution to the contest [Employee Programming Challenge #1] (https://openexchange.intersystems.com/contest/47).

The script has only one line of code (ObjectScript)
It's not very efficient but it has only 350 characters, good for the Code Golf nomination :-)

## Prerequisites

Make sure you have [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Docker desktop](https://www.docker.com/products/docker-desktop) installed.

# Build

Clone the repository

```bash
cd myfolder
git clone https://github.com/McFly589/Gaia-CodeGolf.git .
```

Start up the Docker container:

```bash
docker-compose up --build -d
```

## Run the solution

Build the project in Docker container and run the following in IRIS terminal:

```
$ docker-compose exec iris iris session iris
USER>do ^RunScript
```
