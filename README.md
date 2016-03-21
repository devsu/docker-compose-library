# Docker Compose Library

This is a collection of docker-compose files for about anything you can have running on docker.

It's a database of docker compose files that use the "best" images we've found for both development and production environments.

## Motivation

1. Avoid re-creating the same templates again and again for one project to another.
2. Create a common database of templates that apply a few "conventions" we follow for most projects.

## Usage

First, clone this repo:

`git clone https://github.com/devsu/docker-compose-library.git`

Second, to use a template, use the `cp-tpl` script. You will need the next parameters: the name of the template, the path to create the copy, and the name of the project.

`./cp-tpl platforms/symfony/2.x-php7.0-with-mysql ../my-awesome-project-path my-awesome-project`

You will get a copy of the template on the `../my-awesome-project-path` folder, with the name `my-awesome-project`

Third, modify the variables inside `../my-awesome-project-path/my-awesome-project_env`

Finally, you can use the `./use-tpl` script to run docker composer using the variables in the file. 

`./use-tpl create ../my-awesome-project-path/my-awesome-project`

The difference between using `create` or `up` is that create only creates the container while up creates it and then starts it.

## Conventions

- Set variables for [nginx-proxy](https://github.com/jwilder/nginx-proxy).
- Connect to other containers using external links.
- Links aliases are as simple as possible: e.g. **mysql** for a mysql database.
- Variables are set in a different file (.env).

## License

[GNU GPLv3](https://github.com/devsu/docker-compose-library/blob/master/LICENSE) © 2016, Devsu LLC