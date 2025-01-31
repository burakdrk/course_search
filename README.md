# Course Searcher

### This is a PhP web app for searching courses offered in UoG by prerequisites.
### Completed as part of a group project in Soft Eng class.

## How to run this server locally (Windows or MacOS)

1. [Install Docker Desktop.](https://www.docker.com/products/docker-desktop/)
2. Downloading/pull the contents of the repository to your own local project directory.
3. While in the project directory (the directory where docker-compose.yml file is), run `docker-compose up -d` (Make sure it's not already running).
4. The server/container will be running in the background and accessible on localhost.
5. If you want to access the MySQL instance that's on the VM, on a separate terminal window, run: `ssh -o StrictHostKeyChecking=no -L 3307:localhost:3306 socs@groupurl` (Make sure you're connected to the vpn).
6. Leave the terminal window running to stay connected.
7. Once you're done developing, you can stop the container using Docker's GUI Dashboard and exit the terminal/ssh.

### Rebuilding the server locally

In the case that NGINX configuration has been changed or there are unknown issues with the container, rebuilding may be an option.

1. Ensure the container is stopped/shut down first
2. Rebuild the container: `docker-compose build`
3. Start up the rebuilt container: `docker-compose up -d`

## Deploying on the VM

### Using Linux scp

1. SSH to the VM first and delete everything in the /var/www/html/ directory, you can quit the teriminal after this.
2. While in this project directory, run: `scp -r ./src/* socs@groupurl:/var/www/html/`
3. SSH to the VM.
4. Go to the page to confirm it loads successfully.

