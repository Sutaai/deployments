# Deployments

This repository contains the definition of my tools deployments.

Good for me so I can track how I deploy my stuff.


## Quick notes

### ENV interpolation

```sh
Direct substitution
  ${VAR} -> value of VAR
Default value
  ${VAR:-default} -> value of VAR if set and non-empty, otherwise default
  ${VAR-default} -> value of VAR if set, otherwise default
Required value
  ${VAR:?error} -> value of VAR if set and non-empty, otherwise exit with error
  ${VAR?error} -> value of VAR if set, otherwise exit with error
Alternative value
  ${VAR:+replacement} -> replacement if VAR is set and non-empty, otherwise empty
  ${VAR+replacement} -> replacement if VAR is set, otherwise empty
```

### Setting an user

All possible values:

```yml
services:
  app:
    image: python
    user: 1000:1000
    user: sutaai
    user: sutaai:web
    ...
```

> [!NOTE]
> LinuxServer's images prefers `PUID`/`PGID`. Process won't be launched as root, but container will be.

## References

- Environment variables interpolation: <https://docs.docker.com/compose/how-tos/environment-variables/variable-interpolation/>
- Compose file reference: <https://docs.docker.com/reference/compose-file/>
