# Ruby Certificates

These are the public certificates which I use for signing Ruby gems. You should only trust these files when they come from a git commit signed with my public key.

```bash
$ gpg2 --list-keys DEF93B63EA78DCD4B495452EA0765423A44728FB
pub   rsa4096 2017-01-18 [SC] [expires: 2027-01-16]
      DEF93B63EA78DCD4B495452EA0765423A44728FB
uid           [ultimate] Samuel Grant Dawson Williams <samuel.williams@oriontransfer.co.nz>
sub   rsa4096 2017-01-18 [E] [expires: 2027-01-16]
```

## Usage

You can trust gems that I release by downloading my certificates and running:

```
$ gem cert --add release-2021.cert
$ gem cert --add release-2022.cert
```

You can then install one of my gems using the MediumSecurity profile:

```
$ gem install falcon -P MediumSecurity
```

The `MediumSecurity` trust profile will verify signed gems, but allow the installation of unsigned dependencies. This is necessary because not all of my dependencies are signed, so we cannot use `HighSecurity`.
