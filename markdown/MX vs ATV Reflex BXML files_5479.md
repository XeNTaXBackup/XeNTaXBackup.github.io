## Post #1
- Username: Number18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 28, 2010 10:51 pm
- Post datetime: 2010-11-29T22:47:27+00:00
- Post Title: MX vs ATV Reflex BXML files

Hello all,

Could somebody please take a look at this BXML format from MX vs ATV Reflex for PC. They seem to be encrypted XML files, the original XML files are still there but the game doesn't read those even after removing the BXML file.

I have uploaded a  RAR package with some BXML and XML files [here](http://www.mxg-hq.com/files/reflex_bxml.rar).

It would be much appreciated by the whole MX vs ATV community.
## Post #2
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-01T06:53:17+00:00
- Post Title: MX vs ATV Reflex BXML files

Don't feel bad. I've been working on this for days. 

First I thought it was backbase.. I called the company for help.. They said they couldn't help. not anything they're familiar with.

Second I thought it was a BXML file from here. :  [http://www.cubewerx.com/bxml](http://www.cubewerx.com/bxml)
I just got out of a conversation with a guy from there.. Here was the conversation...

ME:

I'm a modder. I've been part of modding communities for video games for years. I've always loved the communities and enjoyed creating new things for the them. I'm currently workin on a project for a game called "MX VS ATV Reflex" for the PC. However, I've run into a problem. I have a "BXML File" that I can't seem to edit. I can't find any text editors that will work for it and I've tried EVERYTHING I know with Visual Studio.

I've been going off tutorials because I'm extremely new to all of this. All I want to do, is be able to view and edit the BXML file. The game I'm working on has two files for each name. One file is an XML and another File is a BXML. For example "MXRegistry.xml" and "MXRegistry.BXML" The game doesn't care about the xml files, and I believe these are only there to edit, and pack back into a BXML file. I know that I need to edit the bxmls, but I can't for the life of me, figure out how to edit them.

I've spent days trying to figure this out with no help. If you could help, or shine some light on how to edit a BXML file, I would be extremely appreciative.

HIM: 

There are a few different formats for encoding XML data in binary and
I am only familiar with one of them.  Send me a hexadecimal dump of the
first 16 bytes of the file (or the whole thing if it's short) and I'll
see if I can help you.

ME:

thank you so much! I think it would be much easier for you if I sent you the bxml files. If you can manage to edit this... I attached the file.

HIM:

Sorry, this isn't the BXML format that I'm familiar with.  I don't know
what format your file is in.


So.... To sum it up.. I think we're SOL... I really hope someone can figure this out. I've exhausted my efforts. It's apparently not backbase, nor is it from cube, so... im lost.. lol
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-01T14:04:40+00:00
- Post Title: MX vs ATV Reflex BXML files

it uses a very common compression algorithm which is easy to identify.

the bxml format contains some details on the uncompressed data, which uses a string table for the tags which can easily be reproduced in xml format.

quickbms is not the best tool to rebuild the xml file, but if i have time, i'll see how far it can get. 2 minute bms script to at least parse the file:

```
get UNKNOWN long # 0x103EA - bxmlformat/engine/game version
get STRINGS long # number of strings in uncompressed data
get P_EOSTR long # point to end of strings in uncompressed data

# room for 2 other numbers + pointers

goto 32

get ZSIZE long

comtype zlib

get NAME basename
string NAME += "_bxml.xml"

clog NAME 0x24 ZSIZE 0xfffff

```
## Post #4
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-01T17:46:05+00:00
- Post Title: MX vs ATV Reflex BXML files

well wrs I hope u can figure it out. you'd be the first. I know I'm lost. All I know is that its compressed. I don't know how to decompress it, and re-compress it back into bxml for the game to understand, so I hope you can. lol
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-01T19:14:38+00:00
- Post Title: MX vs ATV Reflex BXML files

> Reply from figuare9
>
> well wrs I hope u can figure it out. you'd be the first. I know I'm lost. All I know is that its compressed. I don't know how to decompress it, and re-compress it back into bxml for the game to understand, so I hope you can. lol

use [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip) and my script to decompress it but converting it to xml is next. just running the script you see how it matches the xml samples.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-01T21:44:46+00:00
- Post Title: MX vs ATV Reflex BXML files

i'll be honest. i didn't see myself spending 3 hours on this format    i didn't really expect quickbms to support recursion too well either - I WAS WRONG!

i've finished a work in progress which works on smaller bxml files but i've overlooked something on node order, and i haven't looked at _valuetype yet, so thats not there.

bxml files doesn't store comments. at all. so recreating them is impossible.

i also decided formatting was worth including, so indenting and one conditional tag syntax is included   

see the previous posts for a link to quickbms if you try this version out.
[bxmlscript.zip](https://xentaxbackup.github.io/file/3653_bxmlscript.zip)
## Post #7
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-01T22:38:17+00:00
- Post Title: MX vs ATV Reflex BXML files

damn that was fasssst! However, I actually don't need BXML to XML.. We need it the other way around. Let me explain.

As you can see in this picture, the game has a BXML file for every XML file. HOWEVER, the game doesn't actually use the xml files. I can run the game completely fine without any of the xml files. I can also edit the XML files and when I start the game nothing I edited works.

What does this mean? It means that the game ONLY uses the BXML files. So... We don't exactly need BXML to XML because the game already provided us with the XML files to edit.... We just need to edit the existing XML files and convert them to the BXML that the game needs to read.
## Post #8
- Username: Number18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 28, 2010 10:51 pm
- Post datetime: 2010-12-01T23:58:59+00:00
- Post Title: MX vs ATV Reflex BXML files

Wow great work! If only we can compile them back to BXML now!

@figure9: We do need the ability to convert BXML to XML because there some some files, the camera presets for example that do not have an original XML in place.
## Post #9
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-02T00:12:25+00:00
- Post Title: MX vs ATV Reflex BXML files

a lot of people that mod have very basic knowledge of anything besides photoshop and 3d modeling. If someone could develop an application that can give us "BXML to XML" and vise-versa, we would be in perfect business.I'm one of those people. I don't know C, and I don't like software im unfamiliar with. I think that goes for a lot of people. What we really need is an app that can do the bxml crap for us.
## Post #10
- Username: Number18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 28, 2010 10:51 pm
- Post datetime: 2010-12-02T00:24:27+00:00
- Post Title: MX vs ATV Reflex BXML files

> Reply from figuare9
>
> a lot of people that mod have very basic knowledge of anything besides photoshop and 3d modeling. If someone could develop an application that can give us "BXML to XML" and vise-versa, we would be in perfect business.I'm one of those people. I don't know C, and I don't like software im unfamiliar with. I think that goes for a lot of people. What we really need is an app that can do the bxml crap for us.

Well we're halfway there now. Editing the XML is very easy with just notepad, though I use Dreamweaver myself.
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-02T01:09:01+00:00
- Post Title: MX vs ATV Reflex BXML files

it should be easy to convert back if anyone had the time do write it in a slightly more powerful language.

i just came back to post a spec i just wrote up with the corrections to how the node levels are stored in the last section of the uncompressed data.

```
-----------

Signature (4 bytes, ASCII "BXML")
Version
StringCount
PoolPointer
PoolSize
AttributeCount
NodeCount
Unknown (0)
CmpSize

Followed by data (with a length of CmpSize) compressed with zlib:

UNCOMPRESSED DATA FORMAT
------------------------

String table (variable size):

Null-terminated strings


Pool (size of PoolSize):

Mixture of integer, boolean and floating point values


Attribute table (12 bytes):

ANameIndex
AValueIndex
AOther


Node table (32 bytes):

NNameIndex
NInnerTextIndex
NUsesPool
NValueType
NLevelId
NChildCount
NAttribIndex
NAttribCount

NODE TABLE INFO
---------------

All nodes on the same level are stored together

Level0
Level1
Level2
.. etc

There must only be 1 top level node at level 0 (named after the filename).

Property info:

NInnerTextIndex will have a value of -1 if there is no inner text.
NUsesPool is a boolean, if 1, the inner text is from the Pool.
NValueType with a value greater than 0 adds a "_valuetype" attribute:

(NOTE: NOT ALL VALUETYPES HAVE BEEN FOUND)

1: "string" (does not seem to use the pool)
3: "int"
5: "float"

11: "bool (either "T", "F" or "true" or "false")

There is also a vector3 type (MXRegistry.bxml)


NLevelID is the sum of the previous levels' NLevelID + NChildCount

NAttribCount is each attribute starting from NAttribIndex


```


The string table is just a list of all the unique strings in the XML document, which are referenced by the various name indexes.

This format was fun, thanks
## Post #12
- Username: Number18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 28, 2010 10:51 pm
- Post datetime: 2010-12-02T02:53:27+00:00
- Post Title: MX vs ATV Reflex BXML files

> Reply from WRS
>
> This format was fun, thanks

And thank you, this is a great step in the right direction! Not long before our community can continue modding the MvA series.
## Post #13
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-03T01:16:47+00:00
- Post Title: MX vs ATV Reflex BXML files

WRS, I don't suppose you can make a tool to allow us to convert XML to BXML?
## Post #14
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-05T06:17:56+00:00
- Post Title: MX vs ATV Reflex BXML files

> Reply from figuare9
>
> WRS, I don't suppose you can make a tool to allow us to convert XML to BXML?

i have spent a little longer on this format as the recursion thing was itching at me... and i finished a bxml to xml converter - but even that's missing some value types which aren't in the samples. 

to repack i need to figure out how to read the xml tree recursively into the bxml table..  with all those indexes too 

for now, see if you run into any trouble converting larger bxml files to xml - my pascal was a little rusty! source is included.
[bxml.zip](https://xentaxbackup.github.io/file/3662_bxml.zip)
## Post #15
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-05T18:09:22+00:00
- Post Title: MX vs ATV Reflex BXML files

That's great! You'd definitely be the first to figure this one out. If you can get this done maybe I'll donate some cash your way for your efforts. I know there would be a lot of people that are gunna love you for this! haha
## Post #16
- Username: Number18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 28, 2010 10:51 pm
- Post datetime: 2010-12-06T03:43:11+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

> Reply from WRS
>
> figuare9 wrote:WRS, I don't suppose you can make a tool to allow us to convert XML to BXML?

i have spent a little longer on this format as the recursion thing was itching at me... and i finished a bxml to xml converter - but even that's missing some value types which aren't in the samples. 

to repack i need to figure out how to read the xml tree recursively into the bxml table..  with all those indexes too 

for now, see if you run into any trouble converting larger bxml files to xml - my pascal was a little rusty! source is included.

It's good to see you are giving it another try. I've tested the BXML to XML converter and it works great except with the larger files.

[Here](http://www.findatrack.com/temp/xml_and_bxml.rar) is a package with all BMXL and XML files I could find so you have some more files to test with.
## Post #17
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-09T03:29:39+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

> Reply from Number18
>
> I've tested the BXML to XML converter and it works great except with the larger files.

thanks for the samples. the attribute indexes have different types, and anything not a string uses the pool too - i'm not sure why i didn't see that before!

anyway, just look out for nodes which have both children and innertext: to fix an issue with animationsets where the innertext was just a comment which snuck in, i dont bother printing innertext for nodes which have children anymore.

this weekend maybe i'll get a chance to take another look at converting back to bxml  
[BXML.zip](https://xentaxbackup.github.io/file/3676_BXML.zip)
## Post #18
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-09T20:35:35+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

> Reply from WRS
>
> Number18 wrote:I've tested the BXML to XML converter and it works great except with the larger files.

thanks for the samples. the attribute indexes have different types, and anything not a string uses the pool too - i'm not sure why i didn't see that before!

anyway, just look out for nodes which have both children and innertext: to fix an issue with animationsets where the innertext was just a comment which snuck in, i dont bother printing innertext for nodes which have children anymore.

this weekend maybe i'll get a chance to take another look at converting back to bxml

very nice! I can't wait. I'm glad you're helping us out! Do you currently have the game that we're trying to work on? The reason I ask is because you can check for yourself to see if it all works when its put back together in bxml
## Post #19
- Username: Number18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 28, 2010 10:51 pm
- Post datetime: 2010-12-14T14:49:42+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

Hey WRS,

Any news on the converter yet?
## Post #20
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2010-12-19T17:47:49+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

TtT
## Post #21
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-19T19:19:17+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

my interest is in the format - which is almost complete - and i have no reason to continue working on this game at all - i don't own, play or care about it!

as it happens, another thread on the .package files was started which uses the bxml format too, so i've been actively working on finishing the bxml to xml converter. WHY? you might ask. well, in order to convert BACK to bxml i need to first understand as much of it as i can? make sense?
## Post #22
- Username: Scawn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 11, 2010 1:47 pm
- Post datetime: 2010-12-22T01:27:10+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

Just so you know, all of your work is greatly appreciated WRS. Thank you for continuing to figure this out.
## Post #23
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2011-03-16T06:04:08+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

bumping, as I'm still trying to figure this out. lol
## Post #24
- Username: madcat117
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 31, 2015 1:49 am
- Post datetime: 2017-07-25T01:28:09+00:00
- Post Title: Re: MX vs ATV Reflex BXML files

Why did WRS not make xml back to bxml for game to read properly!

bxml to xml only is worthless as the game cannot read regular xml files

WRS make the conversion tool please!
