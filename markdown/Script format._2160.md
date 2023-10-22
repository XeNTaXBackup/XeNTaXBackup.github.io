## Post #1
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2006-10-17T17:06:05+00:00
- Post Title: Script format.

First, you're going to have to make some assumptions for me.   

1. Assume that I've been working on a game extractor since May, and it's starting to come together.
2. Assume I've released game extractors before and thus know how to code, and - 
3. Assume I'm posting this here only because this seems to the best game archive community around, and not because I want to ride on anyone's coat-tails or take advantage of these forums (or Mr. Mouse, whom I very much respect for the things he does)

OK.

Now, this game extractor I'm working on supports scripting, but it does it differently to Mex.  It has the advantage of being (IMO) easier to read, but the disadvantage of being less powerful in the things it can do.

A few samples:
```

file name = "*.stuff" {
	packed simple

	unsigned32 fileCount

	FileEntry [fileCount] (
		unsigned32 size
		unsigned32 nameSize		
		string name
	)
}

file name = "*.txt" {
	text
}

file name = "*.ogg" {
	sound OGG
}

file name = "*.dds" {
	image DDS
}
```


```

file name = "*.pak" {
	packed simple

	unsigned32 fileCount

	FileEntry[fileCount] (
		FixedString name 100
		unsigned32 offset_from_end_of_header
		offset: (fileCount * 108) + 4 + offset_from_end_of_header
		unsigned32 size
	)
}
```
 
```
	packed simple

	FileEntry[filePos < dataStart] (
		FixedString name 12
		unsigned32 offset
	)
}

file name = "title.raw" { #title image is special
	data unknown 4
	image VGA (
		width: 640
		height: 480
	)
}
```


You can use any variable anywhere in a script, so you can do things like:

```
    unsigned16 fileCount;

    FileEntry[fileCount + 2](
        unsigned32 size
        name: "Dunno" + size
        someFlag = true
    )
}

file (someFlag) = 1 OR (name = "Something") {
    image RAW24 (
        width: 24
        height: size / ( width * 3)
    )
}
```


And things like LZSS and XOR encryption will be included as standard things you can 'wrap around' other bits of data.

Some of the things you might ask for that work already:

- Archives with no names.  You can:

```
    u8 fileCount
    packedName: name #store the packed file's name

    FileEntry[fileCount] (
        u32 size
        u32 offset
        name: filenames["name"]
    )
}

table filenames(
    -packedName- name
    "foo.pak"        booPakFiles["name"]
    "bar.pak"        barPakFiles["name"]
)

table booPakFiles (
    -fileNum-    name
    0               "blah.bmp"
    ..etc..
)
```


- Files with only an offset/size listed - automatically handled by the "simple" archive reader, although you can define the "size" and "offset" variables if the archive isn't a header followed by file data

- Data types: u8, s8, u16, s16, u32, s32, string (a null-terminated string), fixedString (a string of fixed size, with or without null terminator), ansiString (a u8 of size followed by data), and dirtyString (a u8 of size, followed by string data, padded out to a certain length with no null ternimator); u64/s64 and floats might come later if it's required.

- Hex viewer: still very crap, but it works.

- Modding: not yet, however it's definately planned.  Given that the program reads a file in given the structure, it should be possible to reverse the process quite easily (in some cases).

Now, the reason I'm posting this is the following: this thing's fairly far into development, and I can see that the way I chose it implement it does, in fact, work (against my better judgement ) So, now that I can see results and things work, I can start to massage in things that people want.  What would you like to see in something like this?  What would you like the scripts to look like?  What would you find easiest to read?  Would you prefer variables to be written as "var name: 'Something' + size" to set them apart from data in a file more?  Once again, I emphasise that I'm trying to write something that people will find a use for, not to blow my own trumpet or prove anything.

Cheers guys.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-19T07:55:30+00:00
- Post Title: Script format.

I like the idea, but I haven't had time to really consider your work yet, to see potential pitfalls or advantages other than those you mention. 

However, it seems you might want to check out [http://hachoir.org/](http://hachoir.org/) as this is a tool that is similar to your idea and far in development I believe. I am really intrigued by Hachoir.
[hachoir_urwid_040.png](https://xentaxbackup.github.io/file/936_hachoir_urwid_040.png)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-18T16:21:33+00:00
- Post Title: Script format.

The goal for a good tool is to support complicated and extensive computations, like some encryption algorithms and compression techniques require.
A good way would be a scripting language like LUA I think. It's an easy language (cause similar to C), easy to implement and quite powerful.
## Post #4
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2007-01-19T03:44:50+00:00
- Post Title: Script format.

LUA is problematic, as it doesn't support (natively) integers or bitwise operations.  If there's a version out there that does, please let know, but for now I'm more inclined towards Python as it supports both of the above.
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-19T12:17:06+00:00
- Post Title: Script format.

You can get a library for bitwise operations [here](http://luaforge.net/projects/bitlib)
## Post #6
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-20T00:20:02+00:00
- Post Title: Script format.

And i'm trying to get Mr. Mouse to move from script, silly boys
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-20T11:41:13+00:00
- Post Title: Script format.

It depends on which scripting language is used. The one Mex Commander uses is indeed improper cause it is complicated and restricted. If you have a struct like in C 
```
int a;
byte b[64];
int c;
}
```

you can directly read out the structure of the file and every C programmer understands it.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-20T13:53:35+00:00
- Post Title: Script format.

MexScript was not intented to recreate C or other such low-level languages. 

It was intended for people with little knowledge of programming that wish to support new formats themselves, with many important underlying functions being performed by MultiEx. Thus, it is very high-level, and therefore highly restricted. But that's a choice.  

There is not much point in creating a script like C, you can just as well program a plugin in actual C then (or other language for that matter). 

You will find that if you start doing it in a C like manner, that you will need more and more statements, functions and commands to support all formats. Again, you might as well start coding in C right from the beginning; it's got all you need.  

Rahly is in the process of creating an interpreter of MexScript that will handle old scripts, but also improves much of the MexScript. He still has another idea for this type of thing, but without using a script. Hold your breath for that one.
## Post #9
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-20T15:04:26+00:00
- Post Title: Script format.

If you are going to do this, i'd suggest you write up a grammar for that syntax.  They are helpful in planning out the language and make it 1000x easier to write out the parser for it.  A lot of times, you'll find pitfalls and figure a way around it, or easier to start over without writing code that'll become convoluted, and harder to add new features later.
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-20T18:02:55+00:00
- Post Title: Script format.

> Reply from Mr.Mouse
>
> 
It was intended for people with little knowledge of programming that wish to support new formats themselves
Yeah, but I doubt that such people are able to figure out a file format.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-20T18:43:38+00:00
- Post Title: Script format.

> Reply from Rheini
>
> Mr.Mouse wrote:
It was intended for people with little knowledge of programming that wish to support new formats themselves
Yeah, but I doubt that such people are able to figure out a file format.

That's why I invited Watto to join me in writing this tutorial at the time, eh.  

[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
## Post #12
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-20T19:08:59+00:00
- Post Title: Script format.

And also why we have this support forum. And there's always the [list of unsupported formats](http://wiki.xentax.com/index.php/Category:BMS_None) on the WIKI...
## Post #13
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-20T23:00:10+00:00
- Post Title: Script format.

C* like languages are rather ugly
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-21T13:44:16+00:00
- Post Title: Script format.

That's a matter of taste. ^^
I hate Pascal-like languages.
## Post #15
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-23T03:44:00+00:00
- Post Title: Script format.

it doesn't really have anything to do with tastes, it has to do with semantics.  Pascal is a very readable, except for a couple key words, but I think they were more lazy, like c* coders.

Except for single command, you can do a 1-to-1 from C and Pascal, since they use the same constructs.
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-28T16:02:21+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> And also why we have this support forum. And there's always the list of unsupported formats on the WIKI...
Yeah, I wonder how many scripts have been written by someone else than Mr.Mouse or Watto.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-28T19:05:16+00:00
- Post Title: 

Look, I think you made it clear by now that you have an aversion for the script, and that's okay.
## Post #18
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-28T19:12:23+00:00
- Post Title: 

Yes, but I'd really like to know if there are some scripts by other users, has nothing to do with my aversion,  I'm just curious.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-28T20:17:55+00:00
- Post Title: 

At our forum I know that PXR has created quite a few and Xennex is also writing scripts. Meanwhile, Mike Melanson has been busy with it and pointed the script out to Janusz Dziemidowicz, who recreated the script for Linux [http://fusepak.sourceforge.net/bms.php](http://fusepak.sourceforge.net/bms.php) . But you could have known this from our Team page: [http://www.xentax.com/?page_id=106](http://www.xentax.com/?page_id=106)

Then I know of people who never come here, but simply use it when they feel like it. In the end, it's much easier to come here and wait for someone to write a script, than do it yourself, especially if you're not really up to the task of figuring stuff out. 

Like I said, it's okay to dislike the script, it's not okay to troll about it.
## Post #20
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2007-01-29T00:52:32+00:00
- Post Title: 

I'm still of the opinion that 90% of the time, you don't need to script.  The way that file formats are described on the Wiki, i.e. just the layout of the file is in most cases readable and usable (with a bit of modification) by an interpreter.  I've still got some issues with games that require data embedded in the exe (although that's getting there), but I've managed to port over a large number of games that I wrote stuff for in c++, with a reasonably small custom language:

[http://www.szevvy.net/wombat_2_formats.php](http://www.szevvy.net/wombat_2_formats.php)

It's still a bit rough round the edges, but as far as proving to myself that it works and is worth building an app around - I think the experiment's been fairly successful.

Obviously, however, something like BMS is more powerful in the long run for unpacking game archives - there are some formats that you simply *have* to script for (encryption and compression notwithstanding) - there are formats for which you need to arbitarily seek and that can't be expressed as a 'layout'.
## Post #21
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-29T21:37:03+00:00
- Post Title: 

There's at least one major problem to using the descriptions off of the wiki, though. The work that would be required to design an interpreter that could use the file descriptions off the wiki and successfully extract files from described archives even 90% of the time would require extremely robust code, for the purpose of being able to identify at least most of the possible variants for field names, as well as error-catching/correcting as it goes. Besides being able to deal with errors in the description itself, though, the interpreter would have to be able to handle spamming of pages, when content often gets destroyed, as well as those pages which don't follow the standard layout. In the end, it's far easier and less labor-intensive and time-consuming to leave the file descriptions as reference tools for humans, and keep the existing BMS language.

As for the question of non-mr.Mouse BMS authors, have a look at this category on the WIKI: [Category:BMS Authors](http://wiki.xentax.com/index.php/Category:BMS_Authors) (yes, I know, there aren't many scripts listed there, it's a work in progress, just as the whole category system is).
