+++
title = "Neko"
description = ""
date = 2018-11-01T22:49:40Z
aliases = []
[extra]
id = 12135
[taxonomies]
categories = []
tags = []
+++

{{language
|exec=bytecode
|gc=yes
|checking=dynamic
|site=http://nekovm.org/
}}

'''Neko''' is a high-level [[Dynamic_programming|dynamically typed]] programming language developed by Nicolas Cannasse at [http://motion-twin.com/ Motion-Twin] as part of a R&D effort for better languages.

'''Neko''' is also the name used for a Virtual Machine bytecode interpreter. The VM can be embedded in applications via a C language API.

The '''nekoc''' command compiles Neko source code into NekoVM bytecode.  The '''neko''' command runs NekoVM bytecode.

Another language, '''NekoML''', also compiles to NekoVM bytecode.  '''nekoml''' is a higher level functional programming language, inspired by OCaml.

Other tools that ship with Neko, include a '''nekotools boot''' wrapper to create native executables that encapsulate NekoVM bytecode, and a small web server engine with embedded Neko.  The '''nekotools server''' engine emulates the API provided by the Apache webserver plugin modules ''mod_neko'' and ''mod_tora''.

'''Neko''' is a core part of the [[Haxe]] programming language/toolkit; one of the output targets. Neko is used for system level access, command line applications, and takes a supporting role in some of the tools that make up the Haxe programming environment.

'''Neko''', introduced in 2005, may be superseded by a new virtual machine engine for Haxe development, [[HashLink]].  '''HashLink''' was introduced in 2016, designed as a successor to '''Neko'''.  Haxe 4 (in preview in late 2018), still supports compilation to Neko bytecode and the '''Haxe 4''' environment still uses Neko library functions.

* https://nekovm.org
* https://haxe.org
* https://hashlink.haxe.org
