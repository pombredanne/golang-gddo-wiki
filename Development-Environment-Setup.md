- Install and run [the latest stable version of Redis](http://redis.io/download). The redis.conf file included in the Redis distribution is suitable for development.
- Install Go 1.5.
- Install and run the server:

        $ go get github.com/golang/gddo/gddo-server
        $ gddo-server

- Browse to [http://localhost:8080/](http://localhost:8080/)
- Enter an import path to have the server retrieve & display a package's documentation

Optional:

- Create the file gddo-server/config.go using the template in [gddo-server/config.go.template](https://github.com/golang/gddo/blob/master/gddo-server/config.go.template).

- If working on any of the templates you will want to provides the path to you assets folder. Passing the -assets flag to gddo-server with the path to your assets folder will allow you to view your changes
