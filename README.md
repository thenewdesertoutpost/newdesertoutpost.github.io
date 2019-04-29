# New Desert Outpost
The source for the website of the Burning Man Camp: [The New Desert Outpost](http://newdesertoutpost.com/)

## Development

You'll need [Docker](https://www.docker.com/) to build the site locally.

Build the docker image:

```sh
touch Gemfile.lock
chmod a+w Gemfile.lock
docker build -t ndo "$PWD"
docker run -d -p 4000:4000 --name ndo -v "$PWD":/srv/jekyll ndo
```

Start a new docker container with this image:

```sh
docker start ndo
```

View the site at: [http://localhost:4000/](http://localhost:4000/);

You can stop the server with:

```sh
docker stop ndo
```

You can also restart the server (to load changes to `_config.yml`) with:

```sh
docker restart ndo
```

[More info](https://github.com/daattali/beautiful-jekyll#readme)
