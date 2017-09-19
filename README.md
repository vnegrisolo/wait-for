# wait-for

`wait-for` is a shell script that wait for multiple host:port.

If you want to control startup order for your `docker` containers you should use this script.

This is a nice [Docker documentation](https://docs.docker.com/compose/startup-order/) about the startup-order problem.

This is script was heavily inspired [on this one](https://github.com/vishnubob/wait-for-it) :+1:.

## Usage

Using default timeout of **15 seconds**:

```shell
./wait-for pg.dev:5432
```

Setting a **timeout**:

```shell
./wait-for --timeout=60 pg.dev:5432
./wait-for -t=5 pg.dev:5432
```

Wait for multiple host:port:

```shell
./wait-for pg.dev:5432 api.dev:3000
```

Setting different timeouts for each host:port:

```shell
./wait-for -t=5 pg.dev:5432 -t=10 api.dev:3000
```

## Main features

- `timeout` => in **seconds**
- `multiple` => host:port tuples
- `parallel` => wait for better metrics
- `log` => some nice log
- `shell` => doesn't require anything special
