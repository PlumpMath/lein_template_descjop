# lein-template-descjop

A Leiningen template for Web based desktop application with atom-shell and others.
(now atom-shell based only. will build nw.js based later...)

## Requirements

* leiningen 2.x +
* node v0.12.x +

## Usage

```
$ lein new lein-template-descjop YOUR_APP_NAME
```

see your app dir. looks like

```
.
├── README.md
├── app
│   ├── index.html
│   ├── js
│   │   ├── cljsbuild-main.js
│   │   ├── externs.js
│   │   ├── main-original.js
│   │   └── main.js
│   └── package.json
├── package.json
├── project.clj
└── src
    └── NAMESPACE
        └── core.cljs
```

## Build your atom app

### step 1

run npm command below.

```
$ npm install -g grunt-cli
$ npm install
$ grunt download-atom-shell

Running "download-atom-shell" task

Done, without errors.
```

and run extern commands,

```
$ lein externs > app/js/externs.js
```

run cljsbuild.

```
$ lein cljsbuild once

Compiling ClojureScript.
Compiling "app/js/cljsbuild-main.js" from ["src"]...
Successfully compiled "app/js/cljsbuild-main.js" in 10.812 seconds.
```

so you can run atom-shell app.

On Windows:

```
$ .\atom-shell\atom.exe app
```

On Linux:

```
$ ./atom-shell/atom app
```

On OS X:

```
$ ./atom-shell/Atom.app/Contents/MacOS/Atom app
```

## License

Copyright ©  Kazuhiro Hara (Greative LLC http://greative.jp/)
{:mail kazuhiroh@gmail.com
 :twitter https://twitter.com/kara_d}

Distributed under the MIT License http://opensource.org/licenses/MIT .