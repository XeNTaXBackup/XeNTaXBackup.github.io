## Post #1
- Username: Cyrix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2021 12:24 pm
- Post datetime: 2021-05-16T04:59:52+00:00
- Post Title: [C#] BML.CS - compile error

Hello there,

I am using a BML-Converter written in C# (BML.CS) whats used by a programm to change entries. [See here.](https://github.com/IIWDTI/Coach/blob/master/BML/BML.cs)
The BML-Converter decompiles a BML file to a XML format that be can read easily.
But, some files, if I try to save it unchanged again, it drops me an NullReferenceException - error thats located in line 474 of th BML.CS file.
It does it not on all files, thats I wonder about it. Loading a file is not the problem but to save some of them , I dont understand why.

The files I tried to change are from the game Alien Isolation
In the BML.CS file is an adress what leads me over here.
Hope getting some help, thank you.

// Alien Isolation (Binary XML converter)
// Written by WRS (xentax.com)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-26T22:05:26+00:00
- Post Title: [C#] BML.CS - compile error

> Reply from Cyrix ↑Sun May 16, 2021 12:59 pm at Sun May 16, 2021 12:59 pm
>
> 
Hello there,
[..]
But, some files, if I try to save it unchanged again, it drops me an NullReferenceException - error thats located in line 474 of th BML.CS file.Hello - you can't seriously expect someone's able to help you WITHOUT uploading the file (sample) in question, do you? 

WRS's thread (from Nov 2014) is here:

> Reply from WRS ↑Wed Nov 26, 2014 9:44 am at Wed Nov 26, 2014 9:44 am
>
>
## Post #3
- Username: Cyrix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2021 12:24 pm
- Post datetime: 2021-05-27T08:32:00+00:00
- Post Title: [C#] BML.CS - compile error

> Reply from shakotay2 ↑Thu May 27, 2021 6:05 am at Thu May 27, 2021 6:05 am
>
> 
Hello - you can't seriously expect someone's able to help you WITHOUT uploading the file (sample) in question, do you?

I did...

> Reply from Cyrix ↑Sun May 16, 2021 12:59 pm at Sun May 16, 2021 12:59 pm
>
> 
I am using a BML-Converter written in C# (BML.CS) whats used by a programm to change entries. See here.

I resized the letter for you, you didnt seen.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-27T09:18:38+00:00
- Post Title: [C#] BML.CS - compile error

> Reply from Cyrix ↑Thu May 27, 2021 4:32 pm at Thu May 27, 2021 4:32 pm
>
> I resized the letter for you, you didnt seen.I see more than you can think of.  

I didn't speak of the code, I spoke of the file in question, that caused the error, a BML sample.
(Maybe I was not clear enough.)

(Btw, your answer came fast, that's good! welcome to the forum, btw.  )
## Post #5
- Username: Cyrix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2021 12:24 pm
- Post datetime: 2021-05-27T10:21:12+00:00
- Post Title: [C#] BML.CS - compile error

Oooh, I thought you may have over looked it.

[The file I uploaded here](https://www.file-upload.net/download-14597409/GBL_ITEM.BML.html)

Like i said, decompiling is not that problem.


PS: ...and thank you that you try to help me!
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-27T12:53:27+00:00
- Post Title: [C#] BML.CS - compile error

Thanks.
well, I see, just looking now...

now I remember (quote from the above linked thread ):

```
Parsing child at 21744
Parsing child at 21772
Parsing child at 21800
Parsing child at 9900
Parsing child at 21856
Parsing child at 10068
Parsing child at 10184
Possible large number of attributes -> 239 (node=AlienBML.AlienString+Ref)
Parsing child at 142050

Unhandled Exception: System.IO.EndOfStreamException: Unable to read beyond the e
nd of the stream.
```


- will try to stop parsing...
----------------------------

don't see a simple solution, lines in GBL_ITEM_noconflict.xml:

```
      <input>
        <item name="pipe" quantity="2" />
        <item name="gasoline" quantity="2" />
        <item name="explosive" quantity="1" />
        <item name="gel" quantity="2" />
        <item name="scrap" quantity="25" />
      </input>
      <output>
        <item name="molotov_cocktail" quantity="1" />
      </output>

```


After GBL_ITEM.BML -> GBL_ITEM_noconflict.xml I converted that xml to bml again, then reconverted to xml (GBL_ITEM_error.xml):

```
<quantity 
="item" ="name" molotov_cocktail="quantity" 1="
" input="Dð" 
="ýê" output="É)" 
="ýê" item="" name="pipe" quantity="2" 
="item" ="name" gasoline="quantity" 1="
" item="" name="explosive" quantity="2" />
</recipe><recipe name="medikit_recipe">
<input>
```

Maybe the errors are from my ugly "patch" but the first 1000 lines in GBL_ITEM_error.xml seem to be ok.
Hard to compare because of different formatting.

Since I still don't owe that game I won't put more efforts into this unless I find a simple solution, maybe.

As mentioned in WRS's thread I logged br.BaseStream.Position when converting bml to xml.
Doing this with the original bml and the errorness one and comparing the address logs one might find the offset where things go wrong in the errorness bml.

Also read here:

> Reply from WRS ↑Fri Feb 13, 2015 10:19 am at Fri Feb 13, 2015 10:19 am
>
>  but chances may be low that WRS comes back?
## Post #7
- Username: Cyrix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2021 12:24 pm
- Post datetime: 2021-05-27T17:34:34+00:00
- Post Title: [C#] BML.CS - compile error

> Reply from shakotay2 ↑Thu May 27, 2021 8:53 pm at Thu May 27, 2021 8:53 pm
>
> 
After GBL_ITEM.BML -> GBL_ITEM_noconflict.xml I converted that xml to bml again, then reconverted to xml (GBL_ITEM_error.xml):
Code: Select all</recipe><recipe name="noisemaker_device_recipe">
<quantity 
="item" ="name" molotov_cocktail="quantity" 1="
" input="Dð" 
="ýê" output="É)" 
="ýê" item="" name="pipe" quantity="2" 
="item" ="name" gasoline="quantity" 1="
" item="" name="explosive" quantity="2" />
</recipe><recipe name="medikit_recipe">
<input>
Maybe the errors are from my ugly "patch" but the first 1000 lines in GBL_ITEM_error.xml seem to be ok.
Hard to compare because of different formatting.
Yes, this doesnt look good.


> Reply from shakotay2 ↑Thu May 27, 2021 8:53 pm at Thu May 27, 2021 8:53 pm
>
> 
Since I still don't owe that game I won't put more efforts into this unless I find a simple solution, maybe.

Too bad, EPICs dropt it for free 2 weeks ago.


> Reply from shakotay2 ↑Thu May 27, 2021 8:53 pm at Thu May 27, 2021 8:53 pm
>
> 
Also read here:
WRS wrote: ↑Fri Feb 13, 2015 10:19 am but chances may be low that WRS comes back?
As far I can see he isnt gone, last activity was Sun May 16, 2021 11:25 pm.
Maybe there is a lil tiny itzi bitzi chance to get him back to this (old) project.


I really hope that we can fix this. I wrote a lil program based on WRS his source code. I didnt seen that there is an error inside the BML.
Where I did the final tests with all the BML-files, there this error poped up. First I thought I did something wrong. I tried with my skills to solve the problem, but without success.  I dont want to drop this project.. :'(
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-27T19:02:32+00:00
- Post Title: [C#] BML.CS - compile error

You could insert 
Console.Write("0x{0:X} ", br.BaseStream.Position);

after

```
            {

                bool valid = true;
```
 at the top of the class BML in BML.cs

in ReadWrapper() I replaced
Console.WriteLine("Parsing child at {0}", n.Offset);
by
Console.WriteLine("Parsing child at 0x{0:X}, {1}", n.Offset, n.Flags.Children);

Then execute a test.cmd file (with the following line contained) in the AlienBML.exe folder (bml file must reside here, too):
AlienBML.exe GBL_ITEM_error.bml > log.txt

You might get more insight checking the logged addresses, maybe:
--------------------------------------
log.txt:

Alien Isolation BML Converter v0.03
Written by WRS (xentax.com)
Reading as BML...
0x0 Parsing child at 0x44, 18
Parsing child at 0x160, 40
Parsing child at 0x980, 11
Parsing child at 0xAB4, 44
Parsing child at 0x16A4, 1
Parsing child at 0x16E4, 2
Parsing child at 0x16E4, 72
...
Parsing child at 0x2754, 3
Parsing child at 0x27C8, 47
Possible large number of attributes -> 239 (node=AlienBML.AlienString+Ref)
Possible large number of attributes -> 228 (node=AlienBML.AlienString+Ref)
Possible large number of attributes -> 226 (node=AlienBML.AlienString+Ref)
Parsing child at 0x2B74, 49
Possible large number of attributes -> 226 (node=AlienBML.AlienString+Ref)
Parsing child at 0x33E0, 1007
Possible large number of attributes -> 226 (node=AlienBML.AlienString+Ref)
Parsing child at 0x5678, 2 ################################################ extra? Error?
Parsing child at 0x5698, 5
...

So then why does it say: "Possible large number of attributes"?
(or, in other words, why is Flags.Attributes > 100 ?)

When you compare with the log of the original bml file, it looks so smooth  :

Alien Isolation BML Converter v0.03
Written by WRS (xentax.com)
Reading as BML...
0x0 Parsing child at 0x44, 18
Parsing child at 0x1A8, 40
Parsing child at 0x9C8, 11
Parsing child at 0xAFC, 44
Parsing child at 0x16EC, 1
Parsing child at 0x1730, 2
Parsing child at 0x1768, 72
...
Parsing child at 0x5D40, 3
Parsing child at 0x5DB4, 47
Parsing child at 0x6160, 49
Parsing child at 0x69CC, 1007
Parsing child at 0x13658, 5
Parsing child at 0x136EC, 151
Parsing child at 0x15D80, 20
Parsing child at 0x16410, 50
Parsing child at 0x16FC8, 11
Parsing child at 0x1730C, 20
Parsing child at 0x1749C, 4
Exporting to GBL_ITEM_noconflict.xml...

(btw: pay attention to the fact, that ReadWrapper() is called recursively.)
## Post #9
- Username: Cyrix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2021 12:24 pm
- Post datetime: 2021-05-28T07:31:02+00:00
- Post Title: [C#] BML.CS - compile error

btw, last changes WRS did on the BML-file was two month ago, other changes 21 days ago.
I am not sure if that project from him looks dead or inactive.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-28T08:16:20+00:00
- Post Title: [C#] BML.CS - compile error

Are there any code changes related to v0.02 Latest, Dec 8, 2014?
whatever.

I removed the <movie_playlists> and <map_elements> from GBL_ITEM_noconflict.xml ("noconflict" is added by the tool automacticly)
then created a bml file and converted that back to xml again ("recreation").

On a quick glance (awful formatting of the recreated xml prevents proper comparison) everything is fine then.
But have no time to check for the "Nodes seem to change order" problem, see below.

So the general conversion logic/code seems to be ok, the problem might arise from too many elements in some lists, whatever.

What causes me some belly ache is this:

> Reply from volfin ↑Fri Dec 05, 2014 9:39 am at Fri Dec 05, 2014 9:39 am
>
> 
Well I did a simple test. I dropped a BML your converter so it changes to XML. Then i dropped that XML on your converter so it converts back to a BML.  [...] Nodes seem to change order, etc. I think that test would work with any BML, but for example I tried with FONT_CONFIG.BML"Nodes seem to change order"?
Found that here, too:

> Reply from shakotay2 ↑Thu May 27, 2021 8:53 pm at Thu May 27, 2021 8:53 pm
>
>
