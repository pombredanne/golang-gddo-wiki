- Install and run [the latest stable version of Redis](http://redis.io/download). The redis.conf file included in the Redis distribution is suitable for development.
- Install Go 1.6.
- Download and install Cloud SDK at https://cloud.google.com/sdk/docs/
- Add any OS environment variables needed under the env_varialbles section in the included app.yaml file
- Get the source code:

        $ git clone https://go.googlesource.com/gddo $GOPATH/src/github.com/golang/gddo

- Run the server:

        $ dev_appserver.py $GOPATH/src/github.com/golang/gddo/gddo-server/app.yaml
- The dev_appserver automatically installs the newest version and run the local dev environment for access to local version of Search API, etc. It will also redeploy whenever it detects any source code change.

- Browse to http://localhost:8080/github.com/golang/gddo/gddo-server

If you want to work on a fork of the server code, clone your forked repo to $GOPATH/src/github.com/golang/gddo and work from there. Do not use 'go get' to get your fork. Internal package references and the default path for assets assume that the code is located at $GOPATH/src/github.com/golang/gddo.

To run the gddo-server binary outside of a development environment with the source in $GOPATH/src/github.com/golang/gddo, you will need a copy of the [assets directory](https://github.com/golang/gddo/tree/master/gddo-server/assets). Use the gddo-server --assets command line flag to specify the location of the directory.