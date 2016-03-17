# Docker Compose Library

This is a collection of docker-compose files for about anything you can have running on docker.

It's a database of docker compose files that use the "best" images we've found for both development and production environments.

## Motivation

1. Avoid re-creating the same templates again and again for one project to another.
2. Create a common database of templates that apply a few "conventions" we follow for most projects.

## Usage

First, clone this repo:

`git clone https://github.com/devsu/docker-compose-library.git`

Second, to use a template, use the `docker-use-tpl.sh` script. You will need to parameters: the name of the template, and the name of the project.

`./docker-use-tpl platforms/symfony/2.x-php7.0-with-mysql.yml my-awesome-project`

You will get a copy of the template on the `containers` folder, with the name `my-awesome-project`

Third, modify the variables inside `containers/my-awesome-project/my-awesome-project.env`

Finally, you can use the `./docker-create` script to run docker composer using the variables in the file. 

`./docker-create create my-awesome-project`

The difference between using `create` or `up` is that create only creates the container while up creates it and then starts it.

## Conventions

- Set variables for [nginx-proxy](https://github.com/jwilder/nginx-proxy).
- Connect to other containers using external links.
- Links aliases are as simple as possible: e.g. **mysql** for a mysql database.
- Variables are set in a different file (.env).

## License

[GNU GPLv3](https://github.com/devsu/docker-compose-library/blob/master/LICENSE) © 2016, Devsu LLC