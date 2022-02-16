# docker-examples

This is a collection of Docker containers I've made to make life easier for myself and others.

Also included is a folder called `scripts` that perform many useful functions that I use frequently: starting/stopping/building containers, etc.


## Environment

Each container folder contains a `.envrc` with parameters that can be modified to change the build.

This file can be modified and sourced manually with `source .envrc`. You can also use `[direnv](https://direnv.net/)` to load these parameters automatically whenever the terminal enters a folder containing a `.envrc` file.


This repo is MIT licensed. Use it however you want to.
