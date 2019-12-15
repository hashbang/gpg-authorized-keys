# GPG Authorized Keys

GPG keyrings can be used as a source of trust in terms of who should be allowed
to SSH into a server.

This repository contains a script that may be used as an sshd
`AuthorizedKeysCommand`.

## Usage

You will need to create a user specifically to run `gpg-authorized-keys`.  It's
recommended to use `systemd-sysusers` to create this user, or alternatively you
could run:

```
useradd gpg-authorized-keys
```

In your `sshd_config` add:

```
AuthorizedKeysCommand=/path/to/gpg-authorized-keys
AuthorizedKeysCommandUser=gpg-authorized-keys
```

