## Avoiding 404 errors during apt-get

I was getting lots of 404 errors when building Dockerfiles.
This seems very relevant:
https://stackoverflow.com/questions/37706635/in-docker-apt-get-install-fails-with-failed-to-fetch-http-archive-ubuntu-com/37727984

In particular the answer by `jwodder`:


You have stated that your Dockerfile contains `RUN apt-get -y update` as its own RUN instruction. However, due to build caching, if all changes to the Dockerfile occur later in the file, when docker build is run, Docker will reuse the intermediate image created the last time `RUN apt-get -y update` executed instead of running the command again, and so any recently-added or -edited apt-get install lines will be using old data, leading to the errors you've observed.

There are two ways to fix this:

1. Pass the `--no-cache` option to docker build, forcing every statement in the Dockerfile to be run every time the image is built.

1. Rewrite the Dockerfile to combine the `apt-get` commands in a single `RUN` instruction: `RUN apt-get update && apt-get install foo bar ....` This way, whenever the list of packages to install is edited, docker build will be forced to re-execute the entire RUN instruction and thus rerun `apt-get` update before installing.

The Dockerfile best practices page actually has an entire section on apt-get commands in Dockerfiles. I suggest you read it.

