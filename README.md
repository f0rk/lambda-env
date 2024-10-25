lambda-env
==========

Read environment variables from an in-AWS lambda function and execute a command
with those variables exported. Think of it like the `env` command, but it
retrieves variable definitions from lambda. Helpful for debugging a lambda
locally.

Use like:

```!sh
$ echo "$TZ"

$ lambda-env my_test_app sh -c 'echo "$TZ"'
America/New_York
```

Works well with [swaj](https://github.com/f0rk/swaj) or [eruza](https://github.com/f0rk/eruza):
```!sh
$ swaj --profile dev exec lambda-env my_test_app sh -c 'echo "$ENVIRONMENT"'
dev
$ swaj --profile production exec lambda-env my_test_app sh -c 'echo "$ENVIRONMENT"'
production
```

See also [docker-run-env](https://github.com/f0rk/docker-run-env) for other possibilities.

Install
=======

```!sh
curl https://raw.githubusercontent.com/f0rk/lambda-env/master/lambda-env > ~/bin/lambda-env
chmod +x ~/bin/lambda-env
```
