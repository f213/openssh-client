# openssh-client

[![Build status](https://github.com/f213/openssh-client/actions/workflows/ci.yml/badge.svg)](https://github.com/f213/openssh-client/actions/workflows/ci.yml)

> Docker Image with alpine linux and openssh-client

Supported tags and respective Dockerfile links

- latest ([Dockerfile](https://github.com/f213/openssh-client/blob/master/Dockerfile))


## Usage

For SSH tunneling

```yaml
tunnel:
   image: ghcr.io/f213/openssh-client:0.0.4
   command: ssh -v -o StrictHostKeyChecking=no -N -L 0.0.0.0:5432:localhost:5432 tunnel-user@your-postgres-server
   secrets:
     - source: private_key
       target: /root/.ssh/id_rsa
       mode: 0600

secrets:
  private_key:
   external: true
```
