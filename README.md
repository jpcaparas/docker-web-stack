# Docker Web Stack


# What's inside

A `docker-compose`-powered stack to get your PHP project running in no time.

- PHP-FPM 7.1
- nginx
- MariaDB
- Node w/ Yarn


# Requirements

- `Docker` v17.03.1-ce or higher
- `docker-compose` v1.11.2 or higher


# How-to (simple)

To start the stack, run:

        docker-compose up -d --build --remove-orphans

- The `-d` flag daemonises the stack.
- The `--build` builds services (e.g. `php-fpm`, `nginx`) that comprise the stack.
- The `--remove-orphans` stack ensures that services that aren't being used are deleted (to save disk space).

---

To stop the stack, run:

        docker-compose stop

---

To install composer dependencies, run:

        docker-compose run --rm composer install

- The `--rm` flag ensures that that intermediate (temporary) containers are deleted once you install packages (to save disk space).


# How-to (advanced)

## Re-building a service

If you want to extend the functionality of a service (e.g. php-fpm), you have to re-build it.

To accomplish this, modify the Dockerfile, then run:

        docker-compose build --no-cache --force-rm [name-of-service]

... followed by a `docker-compose up [arguments...]`


# Warranties

- This stack was built on `macOS Sierra` v10.12.5. Experience may vary on other operating systems.
