## What's this?

It should be noted: 🚨 **OpenSSL 1.0 is no longer supported and no longer receives updates.** 🚨 Ideally, you wouldn't use this version of OpenSSL at all!  However, this is not an ideal world, and sometimes you have the need to install legacy software that depends on OpenSSL 1.0.  

I was personally motivated by wanting to install old versions of Ruby.  On macOS, attempts to install old versions of Ruby would result in messages like:

```
...
configuring openssl
Failed to configure openssl. It will not be installed.
...
The Ruby openssl extension was not compiled.
ERROR: Ruby install aborted due to missing extensions
Configure options used:
  --prefix=/Users/hynkle/.asdf/installs/ruby/2.1.8
  --with-openssl-dir=/usr/local/opt/openssl@1.1
  --with-readline-dir=/usr/local/opt/readline
  CC=clang
  LDFLAGS=-L/Users/hynkle/.asdf/installs/ruby/2.1.8/lib
  CPPFLAGS=-I/Users/hynkle/.asdf/installs/ruby/2.1.8/include
```

## How do I install it?

`brew install hynkle/homebrew-legacy-openssl/openssl@1.0`

Or `brew tap hynkle/homebrew-legacy-openssl` and then `brew install openssl@1.0`.

Or install via URL (which will not receive updates):

```
brew install https://raw.githubusercontent.com/hynkle/homebrew-legacy-openssl/master/Formula/openssl@1.0.rb
```

## How do I make Ruby compilation use this openssl?

Something like this:

```
RUBY_CONFIGURE_OPTS="--with-openssl-dir=$(brew --prefix)" asdf install ruby 2.1.8
```

## Documentation

`brew help`, `man brew` or check [Homebrew's documentation](https://docs.brew.sh).

## Thank you!

This is basically identical to a formula provided by [kensoh](https://github.com/kelaberetiv/TagUI/issues/635#issuecomment-564516108), just renamed from "openssl" to "openssl@1.0" and put into a tap.
