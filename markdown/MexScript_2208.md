## Post #1
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-21T04:08:06+00:00
- Post Title: MexScript

MexScript Parser and Interpreter

Major Additions to the language include new types and embeded expressions.

To be compatible with standard parsing, all places where expressions are allowable, requires the expression to be encompased by parenthesis.

Examples include

```
Set MyVar MyOtherVar
Math MyVar *= 1024

New Code:
Set MyVar (MyOtherVar * 1024)
```


Full support for embeded variables

Unlike the current mexscript, types are generally ignored interally, except when using the "GET" command to read,

```
Byte # alias for Word8
Long # alias for Int32
Int # alias for Int16
ThreeByte
String
Int8
Int16
Int32
Int64
Word8
Word16
Word32
Word64
Single
Double
```

Possibly support for SString (pascal short string) and PString (pascal Long string)

Currently this is a complete rewrite and not all commands have yet been implemented.  Mr.Mouse and I have had several discussions about maybe creating a new engine that might end up replacing everything MexScript does.  Its too early to say if it'll ever be implemented, but its an idea i've floated past him, that he seems to like. 

Please post new ideas or suggestions, with more to follow, stay in touch.
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-21T06:02:30+00:00
- Post Title: MexScript

Decide to revamp the Interpreter so that it can act better as a debugger.  A script IDE for MexScript could act as a debugger and allow steping through the script.  Nice for writters.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-21T08:32:37+00:00
- Post Title: MexScript

Just back from San Diego. Yes, Rahly has done some extensive work on rewriting a "MexScriptor", at least the core code. A new IDE should still be written, if needed. The other idea Rahly has, a new way to approach format interpreting/handling, is really rather cool. But its still very early.
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-23T01:10:28+00:00
- Post Title: MexScript

And support for old scripts? Will that be handled, and if so, how? Or will support for them just be dropped altogether?
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-23T05:34:17+00:00
- Post Title: MexScript

probably not immediately, if ever. but if it does work out, then there wouldn't be any more upgrades to the scripting at least.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-23T07:35:55+00:00
- Post Title: MexScript

Is there already a working version / interface that I can test to use with MexCom? Or do you have any idea when you'b more or less complete the MexScript core?
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-23T11:48:48+00:00
- Post Title: MexScript

Not sure what you are talking about, the thing we were talking about or MexScript?

nothing working for the first, just a rough outline

MexScript, not sure, i don't know how you work things and errors that are produced for some things. doing a little guess work, with a few things i'm working out.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-23T12:31:11+00:00
- Post Title: MexScript

Yeah, I was talking about MexScript.
## Post #9
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-24T17:00:36+00:00
- Post Title: MexScript

Command done pending complete testing for it. (aka has worked for a script but not all aspects have been tested)

```
Get <variable> <type> <expression>
For <varible> = <expression> to <expression>
Next <variable>
GetDString <variable> <expression> <expression>
IDString <expression> <raw string data>
Goto <expression> <expression>
Math <variable> <mathop> <expresion>
Log <expression> <expression> <expression> <expression> <expression> (<expression> <expression>)
CLog <expression> <expression> <expression> <expression> <expression> <expression> <expression>
SavePos <variable> <expression>
ImpType <importtype>
ComType <compressiontype>
Do
While <expression> <relationop> <expression>

// Still need to be added to the interpreter
Open <raw string> <raw string> <expression>
GetCT <variablename> <type> <raw string> <expression>
FindLoc <variablename> <type> <raw string> <expression>
String <variablename> <mathop> <expression>
If <expression> <relationop> <expression>
Else
EndIf
```


Not exactly sure what ImpType and ComType actually do, wiether it applies to the file being extracted, or the data that being read by the script.  Having Clog is allowed for backwards compatibility, but now log allows the 2 options in CLog to be optional, this makes Clog obsolete.

Not quite sure what "GetCt TempVar Long $ 0" is suppose to do.
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-26T19:01:51+00:00
- Post Title: MexScript

Am I missing any commands?
## Post #11
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-11-27T06:12:56+00:00
- Post Title: MexScript

Another question is how do you want the interface, since the code is in .NET and uses Classes and Objects, which vb doesn't have access to, i have to create a mixed code wrapper for you to call.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-27T09:30:27+00:00
- Post Title: MexScript

ImpType: Tells MexCom what kind of structure to expect in terms of resource replacement in the archive. Standard means that Resource Offsets and Sizes are all there, and there's no tail. StdSize , only sizes are saved, and StdTail (or something) notifies that there's a tail with the file info in it, and a tailpointer to match this. The tailpointer location is saved in TailOffOff. And the value there in TailOff. 

ComType: How resources are compressed, only one type per script allowed. ZLib1 (zlib files) and BK2 (bk2 files). ZIP files are not there, as they are processed by MexCom regardless of script.

```
GetCt TempVar Long $ 0
```


Get character-terminated TempVar (a long variable) from file 0. The long is terminated with a $. Mostly used of course with strings that are not null-terminated but terminated with some other character.
## Post #13
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-24T16:32:36+00:00
- Post Title: MexScript

simple test ide interface for rad development.
## Post #14
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-25T17:39:40+00:00
- Post Title: MexScript

Just a thought, perhaps number each line of code in the editor? I noticed that your debugger showed a line number, but in a lengthy script, it could be a hassle counting manually to the problematic line...
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-25T19:33:06+00:00
- Post Title: MexScript

> Reply from Dinoguy1000
>
> Just a thought, perhaps number each line of code in the editor? I noticed that your debugger showed a line number, but in a lengthy script, it could be a hassle counting manually to the problematic line...

You mean, MY scriptor did. These are pics from Rahly's scriptor. I think it might be an idea in the future, that's up to Rahly though.
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-26T16:05:48+00:00
- Post Title: 

please note i said TEST ide, this is by no means a product, but a visual of how the debugger and scriptor works.
## Post #17
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-26T17:27:30+00:00
- Post Title: 

Eh? I knew that... I was referring to the last image, where it says
"4: Unknown Command: x
Test Compile Completed"
## Post #18
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-05-30T02:14:16+00:00
- Post Title: 

New stuff, different look, also added breakpoints.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-05-30T06:37:09+00:00
- Post Title: 

I long for the day I can get rid of my MexScriptor!  This is looking good!
## Post #20
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-05-31T22:28:41+00:00
- Post Title: 

Nice!  I was wondering where you'd disappeared to...
## Post #21
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-07-04T15:05:57+00:00
- Post Title: 

For Get Command

Removed Types

```
Int
ThreeByte
Byte
```


All Types as Followed

```
LInt16
LInt32
LInt24
LInt64
LUInt8
LUInt16
LUInt24
LUInt32
LUInt64
BInt8
BInt16
BInt24
BInt32
BInt64
BUInt8
BUInt16
BUInt24
BUInt32
BUInt64
String
ShortString
LongString
Single
Double
```


Created Alias for backwards compatibility

```
Int -> LInt16
Byte -> LUint8
ThreeByte -> LInt24
```


Alias's take an extra lookup time, so in theory they are slower but not noticably

Types on Debate

```
LongWideString
```
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-04T17:37:58+00:00
- Post Title: 

Really NICE!
## Post #23
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-07-05T02:51:37+00:00
- Post Title: 

some changes

removed types (changed to Alias')

```
BInt8
LUInt8
BUInt8
```


added types

```
UInt8
```


Mainly because 8bit doesn't have endianess
## Post #24
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-07-05T03:34:19+00:00
- Post Title: 

removed types (changed to alias')

```
Double
```


added types

```
LDouble
BSingle
BDouble
```
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-05T05:26:03+00:00
- Post Title: 

> Reply from Rahly
>
> 
Mainly because 8bit doesn't have endianess

LOL.
## Post #26
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-07-07T15:34:48+00:00
- Post Title: 

Yet Another Reason (YAR!) why endianness still mystifies me...
## Post #27
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-11-24T16:50:18+00:00
- Post Title: 

Internal types and their conversion in expressions

```
string + int    = int
string + long   = long
string + uint   = uint
string + ulong  = ulong
string + float  = float

int    + string = int
int    + int    = int
int    + long   = long
int    + uint   = long
int    + ulong  = ulong
int    + float  = float
 
long   + string = long
long   + int    = long
long   + long   = long
long   + uint   = long
long   + ulong  = ulong
long   + float  = float

uint   + string = uint
uint   + int    = long
uint   + long   = long
uint   + uint   = uint
uint   + ulong  = ulong
uint   + float  = float

ulong  + string = ulong
ulong  + int    = long
ulong  + long   = ulong
ulong  + uint   = ulong
ulong  + ulong  = ulong
ulong  + float  = float

float  + string = float
float  + int    = float
float  + long   = float
float  + uint   = float
float  + ulong  = float
float  + float  = float
```


if undesirable, new command added

```
CONVERT VariableName Type
```

This command allows the promotion of a variable to a specific type

P.S. Forgot to mention that strings will be converted to an integer, unlike most string->int converters in languages, this acts more like in scripting languages (perl/php) where "103 hello" is actually 103 integer instead of an error or 0
