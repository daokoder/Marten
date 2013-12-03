# Project Mission

Project mission is to provide easy to use, powerful, embeddable web server.

# Overview

Marten is a fork of Mongoose, forked from the last revision that was still
released under the MIT license. It will stick to the C programming language
and the MIT license.

Marten keeps the balance between functionality and
simplicity by carefully selected list of features:

- Liberal, commercial-friendly
  [MIT license](http://en.wikipedia.org/wiki/MIT_License)
- Works on Windows, Mac, UNIX, iPhone, Android, and many other platforms
- Scripting and database support (Lua Server Pages + Sqlite, see
  [page.lp](https://github.com/daokoder/marten/blob/master/test/page.lp) ),
  which provides ready to go, powerful web development platform in
  one single-click executable with **no dependencies**: forget LAMP!
- Support for CGI, SSL, SSI, Digest (MD5) authorization, Websocket, WEbDAV
- Resumed download, URL rewrite, file blacklist, IP-based ACL, Windows service
- Download speed limit based on client subnet or URI pattern
- Simple and clean embedding API,
  [mongoose.h](https://github.com/daokoder/marten/blob/master/mongoose.h).
  The source is in single
  [mongoose.c](https://github.com/daokoder/marten/blob/master/mongoose.c) file
  to make things easy. Embedding examples:
  [hello.c](https://github.com/daokoder/marten/blob/master/examples/hello.c),
  [post.c](https://github.com/daokoder/marten/blob/master/examples/post.c),
  [upload.c](https://github.com/daokoder/marten/blob/master/examples/upload.c),
  [websocket.c](https://github.com/daokoder/marten/blob/master/examples/websocket.c)
- HTTP client capable of sending arbitrary HTTP/HTTPS requests
- [User Manual](https://github.com/daokoder/marten/blob/master/UserManual.md)

Note that Windows and MacOS binaries have following 3rd party software
compiled in:
  <a href="http://wolfssl.com">WolfSSL lightweight SSL library</a>,
  <a href="http://sqlite.org">SQLite embedded database</a>,
  <a href="http://lua.org">Lua embedded scripting engine</a>.

# Author

The original author is Sergey Lyubka, who developed the original Mongoose.

