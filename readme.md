# Prerequisities

install dependencies of jekyll : 

Ruby version 2.5.0 or higher

RubyGems

GCC and Make

# Phase Dev


## Jekyll Installation

    gem install jekyll bundler

## Jekyll project

    jekyll new online-cv-bassem
    cd online-cv-bassem
    bundle exec jekyll serve --livereload

I passed the --livereload option to serve to automatically refresh the page with each change I make to the source files.

I used an open-source Jekyll CV template and customised it with my personal information which is located on :

"online-cv-bassem\_data\data.yml

# BUILD and RUN Phase

For the build and run phase, I used the Docker-Compose technology, here is the content of "docker-compose.yml" :

```yaml
version: "3.8"
services:
  jekyll:
      image: jekyll/jekyll:3.8 #The Jekyll Image which have all the necessary runtime components
      command: jekyll serve --livereload --force_polling # The command which will Build and Run the Website
      ports:
          - 4000:4000 #The port which will be listening on
      volumes:
          - .:/srv/jekyll #The Volume which will mount my Code Source to "/srv/jekyll"
```

This file uses the Jekyll image that contains all necessary runtime components, runs the command to build and run the website, maps port 4000, and mounts the code source to "/srv/jekyll"
