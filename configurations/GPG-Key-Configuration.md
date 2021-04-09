# GPG Key Configuration

## Install GPG software

#### Windows:

* Download from [official site](https://www.gnupg.org/download/index.html) (GnuPG binary releases / windows)

* Install using GUI

## Config GPG for git

* Get GPG key ID

  `gpg --list-secret-keys --keyid-format LONG`

  ```
  sec   <Algorithm Name>/<16 DIGIT GPG KEY ID(!USE THIS!)> <Create Time> [SC] [expires: <Expire Time>]
        <40 DIGIT GPG KEY>
  uid                 [ultimate] <Username> <Email>
  ssb   <Algorithm Name>/<16 DIGIT> 2021-04-09 [E] [expires: <Expire Time>]
  ```

  Use the 16 digit GPG key ID here

* Set key

  `git config --global user.signingkey <Key ID>`

* Enable default sign

  `git config --global commit.gpgsign true`

* (Optional / Windows) Set GPG program path

  ` git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"`

  (Directory may vary due to installation options)

* Check configuration validity

  * Make any commit: `git commit`

  * View log with signature: `git log --show-signature`

## Config GPG for github

* Get GPG Public key

  export to file: `gpg --export -armor -o <File Name> `

* Upload to github

  * open website [github.com/settings/keys](https://github.com/settings/keys)
  * New GPG key
  * Paste Public key into textbox

