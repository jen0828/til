## Json-server

Json-server provides a readymade Database and a HTTP Server .This npm package uses a single file db.json, treats the file as a JSON database and also exposes routes on which you can GET, POST, PUT, DELETE for that db.json file.

1.  Install json-server

    ``$ npm install -g json-server
    ``
2.  Create a db.json file with some data

    ``
    {
  "posts": [
    { "id": 1, "title": "json-server", "author": "typicode" }
  ],
  "comments": [
    { "id": 1, "body": "some comment", "postId": 1 }
  ],
  "profile": { "name": "typicode" }
}
    ``
3. Start JSON Server

    ``
    $ json-server --watch db.json
    ``

4. If you go to http://localhost:3000/posts/1, you'll get
    ``
    { "id": 1, "title": "json-server", "author": "typicode" }
    ``

***
* [Example repo](https://github.com/jen0828/blog-react) : json-server as a backend for data retrieval with React app.