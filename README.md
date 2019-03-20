# Alumna

This is a straight copy of the site from the SDSV servers. Two docker
containers are used to replicate the site, one for MySQL and the other to serve
the PHP with Apache.

## File Structure

```
  ├── .env                # environment file to keep MySQL passwords secure
  ├── Dockerfile          # required to add mysqli and mod_rewrite to the PHP/Apache container
  ├── README.md           # this file
  ├── current/            # folder containing the static and PHP files for the site, this is attached to the PHP/Apache container
  ├── docker-compose.yml  # docker-compose file to tie together the containers
  └── initial_sql/        # folder containing an sql file with the contents of the database, this is imported into the MySQL container
```


## Development

Requirements:
- Traefik (see here: [https://github.com/scholarslab/traefik ](https://github.com/scholarslab/traefik))
- Docker compose

Clone this repository
- `git clone https://github.com/scholarslab/alumna.git`

Create a `.env` file with the following:

```
  MYSQL_ROOT_PASSWORD=replace_me_with_something
  MYSQL_DATABASE=alumna_production
  MYSQL_USER=replace_me_with_a_user_name
  MYSQL_PASSWORD=replace_me_with_a_password

```

Create a `current/config/database.ini` file using the `current/config/database.ini.changeme` file as a template.
- use `alumna_db` or the current container name for the MySQL container as the 'host' value.
- use the 'MYSQL_USER' value from the `.env` file for the 'username' field
- use the 'MYSQL_PASSWORD' value from the `.env` file for the 'password' field
- use the 'MYSQL_DATABASE' value from the `.env` file for the 'name' field
- leave the 'prefix' field empty
- leave the 'charset' and 'port' values as the default

Run docker-compose
- `docker-compose up`


## Production

Clone this repository
- `git clone https://github.com/scholarslab/alumna.git`

Create a `.env` file with the following:

```
  MYSQL_ROOT_PASSWORD=replace_me_with_something
  MYSQL_DATABASE=alumna_production
  MYSQL_USER=replace_me_with_a_user_name
  MYSQL_PASSWORD=replace_me_with_a_password

```

Create a `current/config/database.ini` file using the `current/config/database.ini.changeme` file as a template.
- use `alumna_db` or the current container name for the MySQL container as the 'host' value.
- use the 'MYSQL_USER' value from the `.env` file for the 'username' field
- use the 'MYSQL_PASSWORD' value from the `.env` file for the 'password' field
- use the 'MYSQL_DATABASE' value from the `.env` file for the 'name' field
- leave the 'prefix' field empty
- leave the 'charset' and 'port' values as the default

Run docker-compose
- `docker-compose up -d`
