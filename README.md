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

Run docker-compose
- `docker-compose up`


## Production

Clone this repository
- `git clone https://github.com/scholarslab/alumna.git`

Run docker-compose
- `docker-compose up -d`
