# tus-shell-client  [![Build Status](https://travis-ci.org/fentas/tus-shell-client.svg?branch=master)](https://travis-ci.org/fentas/tus-shell-client)

<img alt="Tus logo" src="https://github.com/fentas/tus-shell-client/blob/assets/tus-shell-client.png?raw=true" width="30%" align="right" />


> [**tus**](https://tus.io/) is a protocol based on HTTP for *resumable file uploads*. Resumable
> means that an upload can be interrupted at any moment and can be resumed without
> re-uploading the previous data again. An interruption may happen willingly, if
> the user wants to pause, or by accident in case of a network issue or server
> outage.

`tus-shell-client` is a pure shell client implementation for the tus resumable upload protocol.

## Install
```sh
wget -O /usr/local/bin/tus "https://github.com/fentas/tus-shell-client/blob/master/bin/tus?raw=true"
chmod +x /usr/local/bin/tus
```

## Usage
```sh
Usage:
  tus [options] file

Options:
  -t URI            [required] tusd endpoint.
  -o                List tusd OPTIONS.
  -c MEGABYTES      Read up to MEGABYTES bytes at a time.
                    > default: 1
  -p N              N parallel uploads.
                    > default: 1
  -H HEADER         Set additional header.
  -r                Reuploads given file from the beginning.
  -h                Shows usage.

➤ https://tus.io/protocols/resumable-upload.html
➤ https://github.com/fentas/tus-shell-client

```
---
<p align="center">
  <img alt="Tus usage" src="https://github.com/fentas/tus-shell-client/blob/assets/tus-shell-client.gif?raw=true" width="60%" />
</p>

## Environment variables
You can set options as environment variables.
- `TUSD` _(Option: `-t`)_
- `TUS_HEADERS` Separate headers with `,` _(Option: `-H`)_
```sh
export TUS_HEADERS="Authorization: token,Other-Header: value"
```
**equals:** `-H "Authorization: token" -H "Other-Header: value"`.
- `TUS_CHUNK_SIZE` in MegaBytes _(Option: `-c`)_
- `TUS_PARALLEL` _(Option: `-p`)_

## TODOS
- [ ] :rotating_light: test cases with https://github.com/sstephenson/bats ?
- [ ] :construction: kill child processes on SIGTERM
- [ ] :sparkles: `Upload-Defer-Length`
- [ ] :sparkles: `Upload-Expires`
- [ ] :sparkles: `Tus-Checksum-Algorithm` and `Upload-Checksum`
- [ ] :sparkles: `DELETE`
- [ ] :wrench: Test `Upload-Concat`.

## Referrences
- https://tus.io/protocols/resumable-upload.html
- https://github.com/tus/tus.io/issues/96
- https://github.com/sstephenson/bats

## License
This project is licensed under the MIT license, see `LICENSE`.
