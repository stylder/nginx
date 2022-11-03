# Nginx with Let’s Encrypt on docker-compose

`init-letsencrypt.sh` fetches and ensures the renewal of a Let’s
Encrypt certificate for one or multiple domains in a docker-compose
setup with nginx.
This is useful when you need to set up nginx as a reverse proxy for an
application.

## Installation
1. [Install docker-compose](https://docs.docker.com/compose/install/#install-compose).

2. [Install Curl](https://curl.se/download.html).

3. Clone this repository: `git clone https://github.com/stylder/nginx.git `

4. Modify configuration:
- cp init-letsencrypt.template.sh init-letsencrypt.sh
- mv ./data/nginx/template.conf ./data/nginx/app.conf
- Add domains and email addresses to init-letsencrypt.sh and app.conf
- Replace all occurrences of example.org with primary domain (the first one you added to init-letsencrypt.sh) in data/nginx/app.conf

5. Run the init script:

        ./init-letsencrypt.sh

6. Run the server:

        docker-compose up

## License
All code in this repository is licensed under the terms of the `MIT License`. For further information please refer to the `LICENSE` file.
