# YourUoY

A command-line tool for obtaining auth tokens for the API behind the
University of York's mobile app.

To install: copy or symlink the `youruoy` executable into somewhere on
your \$PATH (e.g. `~/.local/bin/`).

There are currently two ways to use YourUoY:

- install the desktop file (e.g. into `~/.local/share/applications/`),
  and have `x-terminal-emulator` be a reasonable terminal emulator that
  supports `-e` (if you're using Debian or a Debian derivative, this is
  probably already the case)
- open devtools and grab the URL that Shibboleth redirects you to, then
  pass it to `youruoy auth --url URL`

In either case, run `youruoy auth` to get started. Note: you will need
to pass a valid OAuth client ID (with `--client-id`) to all uses of
`youruoy auth`. Obtaining such a client ID is left as an exercise for
the reader.

At the time of writing, issued tokens are valid for one hour. Refresh
tokens can be used by passing `--refresh TOKEN`, though you **must not**
do this on a machine shared by other people, since it will expose your
refresh token to anyone who can see the list of running processes.
