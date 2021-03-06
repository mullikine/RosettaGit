+++
title = "Ursa"
description = ""
date = 2016-06-13T14:16:43Z
aliases = []
[extra]
id = 20945
[taxonomies]
categories = []
tags = []
+++

{{stub}}{{language|Ursa|exec=interpreted|site=http://cygnus-x.net/geekstuff/projects/ursa|strength=strong|gc=no}}

==About==
Ursa is a simple programming language that [[user:whinson|I've]] been working on for awhile now. Its syntax is (at times) similar to Lisp, but instead of being list-based, it is "stream-based." Most in-built statements operate on types of data called streams. Streams are are variable-length arrays of data of a certain type.

The basic premise of ursa is to function as a very high-level abstraction layer between streams and "I/O devices." I/O devices are objects that represent locations that can be read and written using data streams; namely, the console, files, and network ports. Ursa greatly simplifies the implementation of programs that transfer data between these devices.

Ursa uses reverse polish notation for math and functions are simply seperated from their arguments by space characters. This makes implentation of Standard Ursa interpreters since this syntax is easier to write a parser for.

==Example Code==

### Raw File Transfer

This Ursa code opens a port on a remote server, then outputs the specified file to the port.

```ursa

if (< (size args) 4)
	out "usage: " args<0> " [server] [port] [file]" endl console
	stop
end if

decl file f
decl port p
f.open args<3>
p.connect args<1> (int args<2>)
out (f.readall) p
f.close
p.close

```


===Single-User Echo Server===

```ursa
# declare a serverport and a port to attach new connections to
declare serverport sp
declare port p

# declare a string to contain lines of input
declare string input

# attach the serverport to port 20000
sp.attach 20000

# loop indefinitely, getting connections then echoing the data they send
while true
        set p (sp.getconn)
        out "%msg: connection from " (p.addr) endl console
        out "echo server " _version endl endl p
        while true
                set input (in string p)
                out input endl p
                if (and (= input "") (not (p.isopen 1000)))
                        break
                end if
        end while
        p.close
        out "%msg: connection closed" endl console
end while
```


==See Also==
* [http://cygnus-x.net/geekstuff/projects/ursa Ursa homepage]
