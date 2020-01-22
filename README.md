# Demo of Turf-Buffer Bug

A demo of the turf-buffer bug w/ rollup

## Seeing the Bug:

1. `npm install`
2. `npm run dev`

## Using:

1. Run `npm run dev` to start a server with watching for app changes.
2. If you change `index.html` you'll need to restart your server.
3. If you want to run on a non-default port run `PORT=NEW_PORT npm run dev`
4. Any files or folders in `assets` will be copied into `public`.
5. Any files referenced by `app.scss` will be built into `public`.
6. Any files referenced by `app.js` will be build into `public`.

## Prod:

1. Run `npm run build` to copy and build all assets and hash the javascript and
  css built.

## Deploy:

Configure s3 or cloudflare to server all files with a very aggressive cache. The
content hashing will bust the caching for updated js and css files.

You'll want to serve all files with heavy caching except index.html (which
should never be cached) and any icons or images from src/assets (unless you
version these manually).

On CI server the steps to deploy will be roughly:

1. Use a recent `node` version.
2. `npm install && npm run build`.
3. Copy `public` folder to somethign like s3 or cloudflare.