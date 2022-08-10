# apt-key-bind
apt-key-bind is a small script to automate following steps.

1. download public key of apt repository
2. prepare file for the key in /etc/apt/keyring
3. add "singed-by" of apt repository setting

# usage
```
echo "apt_repository_segging" |  apt-key-bind pub_key_url key_name
```

# example

```
$ echo 'deb https://apt.releases.hashicorp.com jammy main' | sudo apt-key-bind https://apt.releases.hashicorp.com/gpg apt.releases.hashicorp.com
deb [signed-by=/etc/apt/keyrings/apt.releases.hashicorp.com.gpg] https://apt.releases.hashicorp.com jammy main
$ file /etc/apt/keyrings/apt.releases.hashicorp.com.gpg 
/etc/apt/keyrings/apt.releases.hashicorp.com.gpg: OpenPGP Public Key Version 4, Created Thu May  7 18:09:42 2020, RSA (Encrypt or Sign, 4096 bits); User ID; Signature; OpenPGP Certificate
```

# License
[Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)

