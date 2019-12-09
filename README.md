# electron-pdf

git init](http://electron.atom.io/)

## Usage

```sh
$ docker run -p 9010:3000 junaida2/electron-pdf
```


## API

### Endpoints

#### `GET /:url`

`url`: Absolute url to the webpage you want to have rendered.

```sh
$ curl "http://localhost:9010/https://en.wikipedia.org/wiki/Docker_(software)" > docker.pdf
```

<hr>

#### `POST /`

Send a html string as the request body.

```sh
$ curl -X POST --data '{"html":"<b>Hello</b> World"}' http://localhost:9010/ > hello.pdf
$ curl -X POST -H "x-pdf-orientation: landscape" --data '{"html":"<b>Hello</b> World"}' http://localhost:9010/ > hello.pdf
```


### Options

Use following request headers to control the output pdf appearance.

- `x-pdf-orientation`: `landscape` or `portrait` - Page orientation, defaults to `portrait`.
- `x-pdf-no-backgrounds`: Presence of this header prevents backgrounds from being printed.
- `x-pdf-margins`: `default`, `none` or `minimum` - Margin type, defaults to `default`.
- `x-pdf-pageSize`: `A4`, `A3`, `Legal`, `Letter` or `Tabloid` - Paper size, defaults to `A4`.
