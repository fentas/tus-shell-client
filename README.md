# tus-shell-client
<img alt="Tus logo" src="https://github.com/fentas/tus-shell-client/blob/master/tus-shell-client.png?raw=true" width="30%" align="right" />

> A pure shell client for the tus resumable upload protocol.

## Install
```sh
wget https://raw.githubusercontent.com/fentas/tus-shell-client/bin/tus -O /usr/local/bin/tus
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
  -r                Reuploads given file from beginning.
  -h                Shows usage.

➤ https://tus.io/protocols/resumable-upload.html
➤ https://github.com/fentas/tus-shell-client

```

## Environment variables
You can following options as environmnet variables.
- `TUSD` _(Option: `-t`)_
- `TUS_HEADERS` Seperate headers with `,` _(Option: `-H`)_
```sh
export TUS_HEADERS="Authorization: token,Other-Header: value"
```
**equels:** `-H "Authorization: token" -H "Other-Header: value"`.
- `TUS_CHUNCK_SIZE` in MegaBytes _(Option: `-c`)_
- `TUS_PARALLEL` _(Option: `-p`)_

## DONE
- [x] `Creation`
- [x] Implemented `Upload-Concat` but not tested.

## TODOS `Tus-Extension`
- [ ] `Upload-Defer-Length`
- [ ] `Upload-Expires`
- [ ] `Tus-Checksum-Algorithm` and `Upload-Checksum`
- [ ] `DELETE`
- [ ] Test `Upload-Concat`.

## Referrences
- https://tus.io/blog/2015/11/16/tus.1.0
- https://github.com/tus/tus.io/issues/96
