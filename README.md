1. Create docker-compose.yml
1. Create Dockerfile
1. Create .dockerignore
1. Create .gitignore
1. Create .env

## Environment Variables

```
HOST=$$$
PORT=$$$
APP_KEYS=$$$
API_TOKEN_SALT=$$$
ADMIN_JWT_SECRET=$$$
TRANSFER_TOKEN_SALT=$$$
JWT_SECRET=$$$

# @strapi-community/dockerize variables 
DATABASE_HOST==$$$
DATABASE_PORT=$$$
DATABASE_NAME=$$$
DATABASE_USERNAME=$$$
DATABASE_PASSWORD=$$$
NODE_ENV=$$$
DATABASE_CLIENT=$$$
# @strapi-community/dockerize end variables 
```

## Converting default database to Postgres


## Generating SSH Key and SSH into Server

We host Strapi at `bb1.hosting.bigbrave.digital`

To SSH into server, ensure your SSH public key is in the known SSH Hosts file (Ask @Caitie for access)

### Generating SSH Key
  
```bash
  ssh-keygen -t ed25519 -C "user@bigbrave.co.za"
```


### Copying SSH Key to Server

```bash
  sudo nano ~/.ssh/authorized_keys
```

1. Add the public key generated in the previous step to the last line. Save and exit.

### Connecting to the server
  
```bash
  ssh username@bb1.hosting.bigbrave.digital
```

# Docker

## Deplopyment

[https://hub.docker.com/](https://hub.docker.com/)

We are using Docker to deploy our Strapi application. We have a Dockerfile that builds the application and then we have a docker-compose.yml file that runs the application.

Server: `Hetzner Cloud`

### 1. Clone the repo onto the server

#### Authenticate Bitbucket on the Server

[Using a bitbucket app password](https://support.atlassian.com/bitbucket-cloud/docs/app-passwords/)

TODO: Write out readme on generating Bitbu


```bash
  git clone REPO_URL
```

Enter the BitBucket app password when prompted.

### 2. CD into the repo

```bash
  cd REPO_NAME
```

### 3. Copy the .env file

On the local machine:
```bash
  wormhole send .env
```

On the server:
```bash
  wormhole receive PASSPHRASE
```

### Deploy alias for easy image deployment 

`deploy`:`alias deploy="sudo docker-compose pull && sudo docker-compose up -d"`


# Portainer

https://bb1.hosting.bigbrave.digital/#!/auth


