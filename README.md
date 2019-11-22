*(Note: This is still a work in progress.
This project is not associated with the
[Bitwarden](https://bitwarden.com/)
project nor 8bit Solutions LLC. Please use gitter or the issue tracker for this repo if you need support. If you need to use the official Bitwarden channels make it clear that you are using a 3rd party backend server)*

## bitwarden-go

[![Build Status](https://travis-ci.org/kisom/bitwarden-go.svg?branch=master)](https://travis-ci.org/kisom/bitwarden-go)


A server compatible with the Bitwarden apps and plugins. The server has a small footprint and could be run locally on your computer, a Raspberry Pi or a small VPS. The data is stored in a local SQLite database.

** If you're using an old database you need to add kdf and kdfIterations to your accounts table **

For more information on the protocol you can read the [documentation](https://github.com/jcs/bitwarden-ruby/blob/master/API.md) provided by [jcs](https://github.com/jcs)

### Usage
#### Fetching the code
Make sure you have the ```go``` package installed.
*Note: package name may vary based on distribution*

You can then run ```go get github.com/kisom/bitwarden-go/cmd/bitwarden-go``` to fetch the latest code.

#### Build/Install
Run in your favorite terminal:
```
cd $GOPATH/src/github.com/kisom/bitwarden-go/cmd/bitwarden-go
```
followed by
```
go build
```
or
```
go install
```
The former will create a executable named ```bitwarden-go``` in the current directory, and ```go install``` will build and install the executable ```bitwarden-go``` as a system-wide application (located in ```$GOPATH/bin```).
*Note: From here on, this guide assumes you ran ```go install```*

#### Initalizing the Database
*Note: This step only has to be performed once*

Run the following to initalize the database:
```
bitwarden-go -init
```
This will create a database called ```db``` in the directory of the application. Use `-location` to set a different directory for the database.

#### Running
To run [bitwarden-go](https://github.com/kisom/bitwarden-go), run the following in the terminal:
```
bitwarden-go
```

#### Usage with Flags
To see all current flags and options with the application, run
```
bitwarden-go -h
```
