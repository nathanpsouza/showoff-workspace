# Showoff Workspace

There is a demo application hosted on [https://pacific-citadel-66008.herokuapp.com/](https://pacific-citadel-66008.herokuapp.com/).

## Running application

To run this project, you must have [docker](https://www.docker.com/) and [docker-compose](https://docs.docker.com/compose/) installed on your computer.

### Get the repositories

First of all, to clone the necessary repositories run in your terminal:
```
git clone git@github.com:nathanpsouza/showoff-workspace.git && \
cd showoff-workspace && \
git clone git@github.com:nathanpsouza/showoff.git
```

In this repository there is only docker configurations, the actual code is hosted on [https://github.com/nathanpsouza/showoff](https://github.com/nathanpsouza/showoff).

### Build docker image

To run application, you will need to build docker image, inside `showoff-workspace` directory run:

```
docker-compose build app
```

### Install dependencies and prepare database

```
docker-compose run app bash -c 'yarn && rails db:create db:migrate'
```

### Run RSpec tests

```
docker-compose run app bash -c 'rspec spec'
```

### Start application
```
docker-compose up app
```

After this the application will be accessable through [http://localhost:3000](http://localhost:3000)

## Setup application environment variables

In the file `env`, inside showoff-workspace you can setup showoff api address, client-secret and client id. Just open the file with one text editor and tune as needed.