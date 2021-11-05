# Deploy pgAdmin on Render

This is a [pgAdmin](https://www.pgadmin.org/) template that can be forked and deployed on [Render](https://render.com). (Or any other service that builds and deploys from a Dockerfile.)

It uses pgAdmins's [pre-built Docker image](https://hub.docker.com/r/dpage/pgadmin4/) as base.

## Deployment

See the guide at https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html.

## Environment and Settings on Render

The container needs the following environment variables at startup:
- PGADMIN_DEFAULT_EMAIL
    - This is the email address used when setting up the initial administrator account
- PGADMIN_DEFAULT_PASSWORD
    - This is the password used when setting up the initial administrator account
- PGADMIN_LISTEN_ADDRESS
    - Set the local address that the servers listens on to 0.0.0.0
- PGADMIN_LISTEN_PORT
    - Optional: Set the port that the server listens to 
- PORT
    - Set the port to serve traffic from to the same value as PGADMIN_LISTEN_PORT, which is 80 by default

In addition, set the Health Check Path to "/login".
