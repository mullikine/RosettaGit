+++
title = "MAPPER"
description = ""
date = 2019-09-28T04:06:55Z
aliases = []
[extra]
id = 11151
[taxonomies]
categories = []
tags = []
+++

{{language|MAPPER
|site=http://www.unisys.com/unisys/product/productdetail.jsp?id=1120000160000010000&pid=1120000970018210161&sid=2800008
|parampass=both
|strength=weak
|safety=weak
|gc=no
|checking=dynamic
|LCT=no
|exec=interpreted}}


MAPPER (also more recently known as BIS) was originally a product of the Sperry Corporation and was a mainframe product implemented on the Sperry 1100 systems. It was designed by Louis Schlueter in 1968. It was the first spread sheet with 150 user functions to process data. The run script language was created in the early 70's as the first Macros. In the 80's it was called a 4GL and was also the first major programming language that was easy to learn. Many of the manual function users became Run Designers and developed their own applications. This eliminates the need for the Data Processing (Programmers) Department.

After the merger of Sperry and Burroughs to create the Unisys Corporation, MAPPER was implemented on additional platforms, and is today available on

#Unisys 2200 mainframe
#[[Windows]] Server
#[[Sun]] [[Solaris]]
#[[Linux]]

At various times MAPPER has been available on a number of Unix implementations, including [[IBM]] AIX, and on the Unisys A-Series mainframes.

MAPPER was initially created for the Sperry engineers' internal use.
The first commercial customer was the Aitcheson, Topeka and Santa Fe Railroad Company.

During the early 90s, Windows MAPPER was given an optional web-enablement layer, called CoolICE (where ICE means ''I''nternet ''C''ommerce ''E''nabler),
today generally just abbreviated to ICE.

'''See Also:'''
*http://www.unisys.com/unisys/product/productdetail.jsp?id=1120000160000010000&pid=1120000970018210161&sid=2800008

MAPPER is a 4GL based on a "filing cabinet" paradigm.  Data is organised into a series of numbered "cabinets", each of which contains up to 8 "drawers" (B to I), each of which may contain up to 5,000 "reports".  Drawer "A" is special- it is a shared area, conceptually present in all cabinets simultaneously.  Cabinets are referenced in pairs, e.g. cabinet 0 and cabinet 1 are the same dataset, but if referenced as the "odd" cabinet, the view of the data is read-only.

A report is a column-oriented grid of fixed-length fields, similar in some ways to a spreadsheet, in that there are columns and rows and a set of headers.

Many operations on reports create a result, which is a non-permanent report with the same structure as a report.  In manual functions, there is only one result possible, but runs (scripts) can support up to 17 results, which are referenced the same way as reports but with a negative report-ID.  The result created by an operation is "-0", but these can be saved to -1 to -16 inclusive by the "rename" (@rnm) function.  This allows runs to perform powerful match, blend and reformat instructions.

The MAPPER language is an interpreted scripting language, and is held within the MAPPER database, in reports.  An application in MAPPER is commonly held in reports, within drawers, within a cabinet, or within a series of consecutive cabinets.

While an interpreted language, MAPPER is reasonably quick as the atoms themselves are quite powerful- sort, search, match, count etc are all atoms of the language (which are written in C++ or MASM, depending on platform).

The typing in MAPPER script is very simple: the types are primitive (integer, real, string) and no constructs or similar complex classes are supported.  One-dimensional arrays are supported, arrays of higher dimension would have to simulated in code.

Complex data structures would need to be held in reports or results.

As an alternative, MAPPER may be scripted using JavaScript, and the environment contains its own embedded JavaScript interpreter, with some extensions to reference reports etc as recordset objects, and methods which map onto the atoms of the native scripting language.
