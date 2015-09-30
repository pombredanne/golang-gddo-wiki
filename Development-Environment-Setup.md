- Install and run [the latest stable version of Redis](http://redis.io/download). The redis.conf file included in the Redis distribution is suitable for development.
- Install Go 1.5.
- Install and run the server:

        $ go get github.com/golang/gddo/gddo-server
        $ gddo-server

- Browse to [http://localhost:8080/](http://localhost:8080/)
- Enter an import path to have the server retrieve & display a package's documentation

If you want to work on a fork of the server code, clone your forked repo to $GOPATH/src/github.com/golang/gddo and work from there. Do not use 'go get' to get your fork. Internal package references and the default path for assets assume that the code is located at $GOPATH/src/github.com/golang/gddo.

To run the gddo-server binary outside of a development environment with the source in $GOPATH/src/github.com/golang/gddo, you will need a copy of the [assets directory](https://github.com/golang/gddo/tree/master/gddo-server/assets). Use the gddo-server --assets command line flag to specify the location of the directory.

Optional:

- Create the file gddo-server/config.go using the template in [gddo-server/config.go.template](https://github.com/golang/gddo/blob/master/gddo-server/config.go.template).