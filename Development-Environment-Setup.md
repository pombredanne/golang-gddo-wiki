1. Install and run [the latest stable version of Redis](http://redis.io/download). The redis.conf file included in the Redis distribution is suitable for development.

1. Download and install Go at https://golang.org/dl/

1. Download and install Cloud SDK at https://cloud.google.com/sdk/docs/

1. (Optionally) Generate a new GitHub personal access token with `public_repo` scope.

1. Get the source code:

        $ git clone https://go.googlesource.com/gddo $GOPATH/src/github.com/golang/gddo

1. Start Redis:

        $ redis-server

1. Run the server:

        $ cd $GOPATH/src/github.com/golang/gddo/gddo-server && \
              go build && \
              GITHUB_TOKEN=<redacted> ./gddo-server

    (Replace `<redacted>` with the personal access token from step 4.)

1. Browse to http://localhost:8080/github.com/golang/gddo/gddo-server

If you want to work on a fork of the server code, clone your forked repo to $GOPATH/src/github.com/golang/gddo and work from there. Do not use 'go get' to get your fork. Internal package references and the default path for assets assume that the code is located at $GOPATH/src/github.com/golang/gddo.

To run the gddo-server binary outside of a development environment with the source in $GOPATH/src/github.com/golang/gddo, you will need a copy of the [assets directory](https://github.com/golang/gddo/tree/master/gddo-server/assets). Use the gddo-server --assets command line flag to specify the location of the directory.