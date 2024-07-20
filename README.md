# Saraudon

A command to Visualize result of `git log --stat`


## Install

(not yet supported)

```bash
$ composer install smeghead/phel-saraudon
```

## Execute

```bash
$ git log --stat -n 20 | vendor/bin/phel run src/main.phel -- src > output.html
```

## Development

### docker

```bash
$ docker compose build 
$ docker compose run --rm php_cli bash
# composer install
```



