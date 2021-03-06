# docker-test-dovecot

Docker container with Dovecot that generates random mails in different accounts for testing purposes

## Usage

Start the container using the included `docker-compose` file.

The following users are created who get a newly generated mail if their *\Recent* mails are empty:

* a
* b
* c
* d

The following users are created but get *no* mails automatically:

* rxa
* rxb
* rxc
* rxd

The password of each user is `pass`. You can login using IMAP(S) or POP3(S).

**Important:** Don't bind mount your normal `/home` directory into this container because the Maildirs are wiped clean on startup. Use a dedicated volume for `/home` instead, like in the included docker-compose file.

## Why?

I needed a reference to test [mettmail](https://github.com/spezifisch/mettmail/) against.

## Development

This project uses [pre-commit](https://pre-commit.com/). You need working Docker to run the [hadolint-docker](https://github.com/hadolint/hadolint) hook.

```shell
# install it if needed
pip install pre-commit
# install git hook so checks are run before any commit
pre-commit install
# run manually if you want to
pre-commit run --all-files
```
