# nextcloud-docker

This project sets up a Nextcloud instance using MariaDB as Database and Caddy as a webserver.

## Preperations

Clone the repo and cd into it:
```
git clone git@github.com:craisp/nextcloud-docker.git
cd nextcloud-docker
```

Create a directory for the MySQL secrets and create two files containing passwords for users `root` and `nextcloud`:

```
mkdir secrets
echo 'my_very_secure_root_password' > secrets/mysql_root_password.txt
echo 'my_secure_user_password' > secrets/mysql_password.txt
```

Enter your domain in `caddy/Caddyfile` and in `docker_compose.yml` (`authorized hosts`)

## Run the app

To start the app, run
```
docker-compose up
```

Navigate to `yourdomain.tld` and you should see the Nextcloud config page. Choose a username and password for the nextcloud admin account.
Choose MariaDB / MySQL as a Database and enter the credentials:
- MySQL User: nextcloud
- Password: <your_password>
- MySQL Database: Nextcloud
- MySQL Host: db

`db` is the name of the MariaDB container (`docker-compose.yml`).

That's it, have fun.
