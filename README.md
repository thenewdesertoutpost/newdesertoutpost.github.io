# New Desert Outpost
The source for the website of the Burning Man Camp: [The New Desert Outpost](http://newdesertoutpost.com/)

## Content

Content for the site is broken down into two areas: Pages and Posts. All content is written in [markdown](https://www.markdownguide.org/basic-syntax/) with [jekyll front matter](https://jekyllrb.com/docs/front-matter/) at the top.

### Posts
These are blog posts and usually specifically about a place in time. For example announcements, talking about an upcoming or past burn, etc.

Posts are added to the `_posts` directory with the file format: `<year>-<month>-<day>-<title>.md`.
For example: `2018-08-01-burn-prep.md`

### Pages
A page is content which will be relevant from year-to-year. For example: [the new camper guide](http://newdesertoutpost.com/pages/camper_guide/).

New pages are generally added to the `pages` directory and can be named whatever you want the URL to be.

The name of the file determines the url. For example, `about.md` will be accessible from `/pages/about`.

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
