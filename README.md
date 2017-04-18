This is a fork of
[reflex-todomvc](https://github.com/reflex-frp/reflex-todomvc).

Updated stack settings following
[stack official guide](https://github.com/commercialhaskell/stack/blob/7e300287bdeaaa4adb6c4f53233ba60ec0ef44d1/doc/ghcjs.md).

## Build

To build the project, just clone and `stack setup` and `stack build`.

```sh
$ clone https://github.com/kayhide/reflex-todomvc
$ cd reflex-todomvc
$ stack setup
$ stack build
```

Setup will take very long, possibly an hour or more.
So let's relax and have :coffee: or :tea: or :beer: or :beers: or :sake: or maybe :hotsprings:.

And when build is successfylly done, you can open the generated html with your browser.

```sh
$ open .stack-work/dist/x86_64-osx/Cabal-1.24.0.0_ghcjs/build/reflex-todomvc/reflex-todomvc.jsexe/index.html
```

### Error?

If this error happens

```
    Configuring haskell-src-exts-1.17.1...
    setup-Simple-Cabal-1.24.0.0-ghcjs-0.2.0.9006021_ghc-7.10.3: The program
    'happy' version >=1.19 is required but it could not be found.
```

It means that a valid `happy` executable is not found in PATH.

To solve this, install `happy` as a global project package.

```sh
$ cd                    # outside of any stack project
$ stack install happy
```

And put `$HOME/.local/bin` to PATH.

```sh
$ happy --version
Happy Version 1.19.5 Copyright (c) 1993-1996 Andy Gill, Simon Marlow (c) 1997-2005 Simon Marlow
```

cf) https://github.com/haskell-suite/haskell-src-exts/issues/14

### Another error?

If this error happens

```
    setup: The program 'ghc' is required but it could not be found
```

It means some package is requiring `ghc` executable to build.

Giving the path to the executable will make it work.

```sh
$ PATH=$PATH:~/.stack/programs/x86_64-osx/ghc-7.10.3/bin stack build
```
 
## Reflex

- https://github.com/reflex-frp/reflex

