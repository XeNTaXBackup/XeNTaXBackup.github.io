## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-14T19:43:46+00:00
- Post Title: Levels of support?

Hey Mr.Mouse (and any other general extraction tool authors), I've been doing some work on the wiki as of late, and currently, I have plans for expanding on the "Program support" information for formats. After giving it some thought, I've come up with the following list of support levels that *should* cover most, if not all, situations involving archive formats (if anyone would like to expand the list into other format types, or if you see something I missed, feel free to mention it):
Read archive
Open archive (is there actually any difference between this and reading?)
Extract file
Replace file
Delete file
Add file
Decompress file
Unencrypt file
Compress file
Encrypt file
Create archive
I'm needing to know what levels of support MexScript is capable of, and if there's any at-a-glance methods to identify the level of support. If you could throw in some information on the plugin systems, that'd be great too.

Obviously, MexScript is not natively capable of supporting compression or encryption beyond ZLib (unless you want to get into experimenting with some really ugly math and variable manipulations, or unless I'm missing something big) so you don't need to worry about those.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-16T16:25:39+00:00
- Post Title: Levels of support?

Well, after chatting with Mr.Mouse yesterday, I learned a few things about MexScript:
First, a MexScript doesn't "provide" support for a given format, it "enables" support. While this may sound like splitting hairs, there's actually a pretty significant difference. In order to provide support, the MexScript itself would have to be responsible for reading, extracting, etc., whereas enabling support can basically be interpreted as the MexScript being a set of rules defining the format layout. Ultimately, the level of support is determined by the program calling Multiex.dll.
This also means that a MexScript cannot do anything involving compression or encryption, other than passing the (un)compressed size to the calling program, if the archive provides it. Along the same vein, Mr.Mouse answered a long-standing question of mine regarding MexScripts, when he stated that a script is not capable of calling a plugin.

Later, I broke out my (probably outdated) copy of Game Extractor for the first time in a long time, and while poking around in it, got around to looking at the plugins. Lucky, lucky me, it seems Watto took the time to document just what each individual plugin allows, so the only real problem at this point will be ripping the information from the documentation... Also, I've only got the full version of GE, so I'll need to download and have a look at the demo/free version to see if it does the same thing.

On to Game File Explorer, if I really have to, I can take support information from the website, but it doesn't really provide the in-depth information I'm looking for.

Last, it's been far too long since I looked at the Dragon UnPACKer program or website, so I have no idea what type of information I can glean from them... I'll have to have a look at some point.

If anyone has comments on any of this stuff, feel free to post!
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-18T07:40:03+00:00
- Post Title: Levels of support?

Okay, well, you want to know all this to gain insight into the level of programsupport for each format on the wiki, am I correct? 

In MexCom you can view the level of support (extracting versus editing) in the Help menu (allows importation (=replacing), versus just extraction). With the exeption of plugins that can have additional levels of support, like adding, creating new, and deleting (view Tools->View Plugins). 

TIP: You'll get a nice suplist.txt file in the data folder of MultiEx Commander if you choose the option Help->Supported games (allowing import). In this tab-delimited text file all supported formats are listed, with a flag (Yes/No) for "Edit", meaning replacing is allowed.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-18T16:12:08+00:00
- Post Title: Levels of support?

All right, that should help me!  

I thought that you were able to create new archives in a few rare instances where the format was supported by a MexScript though... or am I imagining things?

Also, how would this work out for Jaeder Naub? It's not a file extractor so much as a file ripper, is it?
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-18T23:08:00+00:00
- Post Title: Levels of support?

JN's a file ripper. When it finds something, it'll rip it, regardless of format. JN doesn't do formats.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-19T14:25:45+00:00
- Post Title: Levels of support?

All right, just like I thought. Thanks for clarifying/confirming for me.
