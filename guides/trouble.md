# Common Errors and Troubleshooting

## `pipenv` error `'module' object is not callable`

If you're running `pipenv` and you get an error that ends like this:

```
"/usr/local/Cellar/pipenv/2018.7.1/libexec/lib/python3.7/site-packages/pipenv/vendor/requirementslib/models/requirements.py", line 704, in from_line
line, extras = _strip_extras(line)
TypeError: 'module' object is not callable
```

it might be time to upgrade `pipenv`. Make sure that `pipenv --version` is
outputting at least `2018.10.13`.

## `./manage.py` error `from exc`

If you get this:

```
    ) from exc
         ^
SyntaxError: invalid syntax
```

it usually means Python 2.x is running instead of Python 3. This, in turn,
usually means you've forgotten to `pipenv shell` into your virtual environment.

Run `python --version` and make sure it says `3.`-something.

## `./manage.py dbshell` not launching

_Chief. Windows_

Make sure you have your SQLite3 package installed and in your path.

## VS Code not recognizing Django imports properly

Enable Django linting by adding the following to your VS Code workplace
settings:

```
"python.linting.pylingArgs":["--load-plugins","pylint_django"]
```