# SMTP to SendGrid Gateway


[![Build Status](https://img.shields.io/circleci/project/github/Paradiced/smtp-to-sendgrid-gateway.svg)](https://circleci.com/gh/Paradiced/smtp-to-sendgrid-gateway/) [![Deps](	https://img.shields.io/david/Paradiced/smtp-to-sendgrid-gateway.svg)](https://david-dm.org/Paradiced/smtp-to-sendgrid-gateway) [![Docker Automated build](https://img.shields.io/docker/automated/deorum/smtp-to-sendgrid-gateway.svg)](https://hub.docker.com/r/deorum/smtp-to-sendgrid-gateway) [![Docker Pulls](https://img.shields.io/docker/pulls/deorum/smtp-to-sendgrid-gateway.svg)](https://hub.docker.com/r/deorum/smtp-to-sendgrid-gateway) [![Docker Stars](https://img.shields.io/docker/stars/deorum/smtp-to-sendgrid-gateway.svg)](https://hub.docker.com/r/deorum/smtp-to-sendgrid-gateway)

Forward emails from SMTP requests to the Sendgrid API. Useful when the cloud provider does not allow outbound connections on ports 25, 465, 587.

## Run

Since this server should run as *a sidekick of the main application* (thus on the same machine or [the same pod](https://kubernetes.io/docs/concepts/workloads/pods/pod-overview/#understanding-pods)) authorization was not required.

```shell
docker run -it -p 25:25 -e SENDGRID_API=XXXXXXX deorum/smtp-to-sendgrid-gateway
```

### Configuration - environment variables

- `SENDGRID_API` (required): sendgrid API token
- `SMTP_PORT` (optional) Port to listen (default: 25)


## Credits

- [SMTP server](https://nodemailer.com/extras/smtp-server/)
- [mailparser](https://nodemailer.com/extras/mailparser/)
- [@sendgrid/mail](https://www.npmjs.com/package/@sendgrid/mail)
