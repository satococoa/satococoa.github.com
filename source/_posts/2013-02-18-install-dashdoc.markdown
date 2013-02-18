---
layout: post
title: "DashDoc を入れてみた"
date: 2013-02-18 15:53
comments: true
categories: sublimetext
---
Dash を Sublime Text からワンタッチで引くことができる DashDoc というプラグインを入れてみた。

インストールはいつも通り Package Control からで OK。

デフォルトで ctrl+h が割り当てられてしまっていたので、変更した。
Preferences > Package Settings > DashDoc > Key Bindings - User

```
[
  { "keys": ["ctrl+h"], "command": "left_delete"},
  { "keys": ["shift+command+h"], "command": "dash_doc"},
  { "keys": ["ctrl+command+h"], "command": "dash_doc",
                            "args": { "syntax_sensitive": "true" } }
]
```

---

あと、RubyMotion のドキュメントを直で引きたかったので追加した。
Preferences > Package Settings > DashDoc > Settings - User

```
{
  "syntax_sensitive": false,
  "syntax_docset_map":
  {
    "ActionScript": "actionscript",
    "C"           : "c",
    "C++"         : "cpp",
    "Clojure"     : "clojure",
    "CSS"         : "css",
    "Erlang"      : "erlang",
    "Groovy"      : "groovy",
    "Haskell"     : "haskell",
    "HTML"        : "html",
    "Java"        : "java7",
    "JavaScript"  : "javascript",
    "Lisp"        : "lisp",
    "Lua"         : "lua",
    "Perl"        : "perl",
    "PHP"         : "php",
    "Python"      : "python2",
    "Rails"       : "rails",
    "Ruby"        : "ruby",
    "Scala"       : "scala",
    "ShellScript" : "manpages",
    "SQL"         : "psql",
    "TCL"         : "tcl",
    "RubyMotion"  : "rubymotion"
  }
}
```

しばらく使ってみよう。