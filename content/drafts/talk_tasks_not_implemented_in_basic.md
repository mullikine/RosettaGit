+++
title = "Talk:Tasks not implemented in BASIC"
description = ""
date = 2009-05-15T22:11:37Z
aliases = []
[extra]
id = 4104
[taxonomies]
categories = []
tags = []
+++

We have a problem when there are no omitted tasks shown on this page. --[[User:Mwn3d|Mwn3d]] 18:42, 28 April 2009 (UTC)
: Is there a task with the omit template used for BASIC?  Has ImplSearchBot had a chance to run since the template was added to that particular task page?  The bot runs every four hours.  Check back at about 12:05AM UTC; The bot should be finished with its next cycle by then. --[[User:Short Circuit|Short Circuit]] 22:17, 28 April 2009 (UTC)
::Not that. The "End of List" paragraph shows up as part of a column instead of all across the bottom. --[[User:Mwn3d|Mwn3d]] 00:12, 29 April 2009 (UTC)
:::Ah, I noticed that.  I thought it looked fine; A rather pointed "this is the end of the list" statement--in the end of the list. :-)  Adding a carriage return to the beginning of the footer template should fix it, if it bothers anyone. I don't dare touch ImplSearchBot's code until I'm dead certain I'm not going to have to go into work for a while; Once I start tweaking it, I won't be able to stop. --[[User:Short Circuit|Short Circuit]] 00:47, 29 April 2009 (UTC)
:::This is not really intentional -- the columnization is done by a <nowiki><div></nowiki> in the header template which is not actually closed anywhere, so the ending point is kind of arbitrary. What we *should* do, I think, is instead of having a header and footer template, have a template for the *whole* unimp page, which we insert the contents into as a parameter. That is, "Tasks not implemented in Foo" contains <code><nowiki>{{unimp page|...unimp list generated by ImplSearchBot...|...omit list generated...}}</nowiki></code>. Then, the unimp page template would contain <code><nowiki>bla bla <div style="...columns...">{{{1}}}</div> ==unimp== bla bla {{{2}}}</nowiki></code>, and so the opening and closing tags for the columns are paired in one template page. --[[User:Kevin Reid|Kevin Reid]] 02:05, 29 April 2009 (UTC)
::::On the up side, that significantly reduces the page edit count by ImplSearchBot, which in turn means I could increase the run frequency to every two hours instead of every four; It drops to one edit per language, plus some others that aren't per-language.  If someone wants to prep a template page, I'll use it next chance I have time to spend on revising ImplSearchBot.  I'll even go so far as to have it nuke the old per-language supporting templates, to save on manual cleanup. (Though I'm seriously going to have to do something about the emails cron sends me if I run it every two hours; Every four is like a Westminster clock.  Every two would be sleep deprivation, as my phone beeps at me when I receive emails.) --[[User:Short Circuit|Short Circuit]] 03:29, 29 April 2009 (UTC)

== What if implementation same as in other language? ==

The "omit" tag means that "language is wholly inappropriate for the task".
But what if the implementation is not needed since it is the same as the implementation in some other language?

For example, I have made a [[RapidQ]] implementation only when it is different from BASIC implementation.
If the BASIC implementation works with RapidQ, I have added the "works with" tag. In this case, the implementation is not needed for RapidQ.
I think there is similar situation for example with C++.
--[[User:PauliKL|PauliKL]] 09:11, 29 April 2009 (UTC)

: I have used the following construct on some pages with very similar languages (C/Objective-C/C++, Pascal/Delphi).  --[[User:IanOsgood|IanOsgood]] 15:39, 29 April 2009 (UTC)

```txt
<nowiki>

## RapidQ

: ''See [[#Basic|Basic]]''
</nowiki>
```


:: That is one possible solution. However, then you would not know which tasks have actually been implemented with the language. It would be nice if there was a list of all "works with" links, too. Or, at least, there could be another template, similar to "omit", but with the meaning "no need for language specific implementation". --[[User:PauliKL|PauliKL]] 15:15, 15 May 2009 (UTC)
::: If the behavior is sufficiently analogous to the "implemented in X" searches, I'll rewrite ImplSearchBot to handle multiple job sets.  I also need to see how difficult it would be to move ImplSearchBot into a separate namespace where pages are generated on view (of cached constructive data), rather than posted as a normal wiki page.  The normal posting inflates the edit count and costs about eight minutes of CPU time for every ImplSearchBot run. --[[User:Short Circuit|Short Circuit]] 22:11, 15 May 2009 (UTC)