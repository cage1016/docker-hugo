# docker-hugo

> hugo runtime via docker

## Running

hugo help

```sh
$ docker run --rm -ti cage1016/docker-hugo:0.17 help
hugo is the main command, used to build your Hugo site.

Hugo is a Fast and Flexible Static Site Generator
built with love by spf13 and friends in Go.

Complete documentation is available at http://gohugo.io/.

Usage:
  hugo [flags]
  hugo [command]

Available Commands:
  benchmark   Benchmark Hugo by building a site a number of times.
  check       Check content in the source directory
  config      Print the site configuration
  convert     Convert your content to different formats
  env         Print Hugo version and environment info
  gen         A collection of several useful generators.
  import      Import your site from others.
  list        Listing out various types of content
  new         Create new content for your site
  server      A high performance webserver
  undraft     Undraft changes the content's draft status from 'True' to 'False'
  version     Print the version number of Hugo

...
```

server exists hugo project

```sh
$ docker run --rm -ti -v $(pwd):$(pwd) -w $(pwd) -p 1313:1313 cage1016/docker-hugo:0.17 server -w --bind=0.0.0.0 ./
```

you can give long command as an alias name

```sh
# give an alias name
$ alias dockerhugo="docker run --rm -ti -v $(pwd):$(pwd) -w $(pwd) -p 1313:1313 cage1016/docker-hugo:0.17"

# server exists hugo proejct again
$ dockerhugo server -w --bind=0.0.0.0 ./
Started building sites ...
Built site for language en:
0 draft content
0 future content
0 expired content
13 pages created
0 non-page files copied
0 paginator pages created
1 tags created
0 categories created
total in 76 ms
Watching for changes in <your-project-path>{data,content,layouts,static,themes}
Serving pages from memory
Web Server is available at http://localhost:1313/ (bind address 0.0.0.0)
Press Ctrl+C to stop
```
