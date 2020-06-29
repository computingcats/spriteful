~~Modernized to work with [golang/dep](https://github.com/golang/dep)~~

Modernized to work with Go Modules.

Spriteful
=========

Spriteful is an API that provides server boot configuration for pixiecore.

See [pixiecore](https://github.com/danderson/pixiecore).

# Build or Install Spriteful
## Install Dependencies
~~As mentioned previously, this project has been forked to update the dependencies management now that gb is pretty much [dead](https://github.com/constabulary/gb/issues/736). golang/dep is now being used and dependencies can be installed by running the following:~~

~~You will need dep, Install instructions [here](https://golang.github.io/dep/docs/installation.html).~~

Now using Go's in-built module dependency manager, ```go mod```. If you'd like to download the dependencies to the vendor folder run

```shell
go mod vendor 
```
Why didn't you commit the vendor directory like other Golang projects using dep i've seen?

Honestly, preference. For more information, see [here](https://github.com/golang/dep/blob/master/docs/FAQ.md#should-i-commit-my-vendor-directory).

## Installing

```shell
go install $GOPATH/src/github.com/engineerang/spriteful
```
Binary can be found in `bin/` directory.

If your $GOBIN is configured you should now be able to run:
```shell
spriteful --help
```

## Building
```shell
go build $GOPATH/src/github.com/engineerang/spriteful
```

# Running

To run spriteful, use the following command:

```shell
spriteful -config /path/to/config/file
```

a sample config file is provided [here](config.json.example).

## pixiecore integration

To integrate with `pixiecore`, point the `-api` argument to this api:

```
$ pixiecore api http://{bindHost}:{bindPort}/api
```
