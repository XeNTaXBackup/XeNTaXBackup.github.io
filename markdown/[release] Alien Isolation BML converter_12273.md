## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-26T01:44:18+00:00
- Post Title: [release] Alien Isolation BML converter

alien isolation uses a binary xml format for some engine tweakers. the game itself seems to read a mix of plaintext xml, a text format, and the bml files. all the spacing is preserved, but comments are not. strings are stored alphabetically.

here is a 010 binary template for the nodes - there are flags which i have lost interest in understanding that are needed to reconstruct the xml:

moved to: [https://gist.github.com/x1nixmzeng/ffeab42c5d0d3549f945](https://gist.github.com/x1nixmzeng/ffeab42c5d0d3549f945)


update
i've written and attached a tool to convert between bml and xml (and xml to bml)    

source: [https://github.com/x1nixmzeng/AlienBML](https://github.com/x1nixmzeng/AlienBML)

update 2
fixed bml exporting

download [from this post](http://forum.xentax.com/viewtopic.php?p=101478#p101478)
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-26T01:59:23+00:00
- Post Title: [release] Alien Isolation BML converter

cool, i was just telling a friend last night I was curious about the BML files, now this.
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-26T02:15:38+00:00
- Post Title: [release] Alien Isolation BML converter

Good work!
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-26T02:26:54+00:00
- Post Title: [release] Alien Isolation BML converter

so instead of reconstructing the whole xml file, you should be able to edit the nodes with attributes.

there is also inner node text for flags 3 and 7 in the l1 instance:

```
    <ID>3</ID>
    <Name>VIEWCONESET_SLEEPING</Name>
    <Filename>ViewconeSets\VIEWCONESET_SLEEPING</Filename>
  </ViewconeSet>

```



i'd be interested to know if this has any effect in-game
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-02T02:07:01+00:00
- Post Title: [release] Alien Isolation BML converter

update

i discovered how the flag bits work, so i can now convert from bml -> xml   

it doesn't change the parser, but:

```
    Info : 3,
    Children : 21;

```


if anyone is actually looking to mod this game i'll write something up. leave a reply
## Post #6
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-02T03:51:36+00:00
- Post Title: [release] Alien Isolation BML converter

yes, I'm interested in teh BML format. any further info you find would be appreciated.
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-02T04:37:50+00:00
- Post Title: [release] Alien Isolation BML converter

Same
## Post #8
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-02T06:35:20+00:00
- Post Title: [release] Alien Isolation BML converter

very cool. make this editable and we can properly mod that shit game
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-03T22:29:51+00:00
- Post Title: [release] Alien Isolation BML converter

bump.

i've written a tool and attached it in the main thread.

for some reason i chose c#, so you may need .net 4.5 or something like that.

it's untested as i don't own the game. let me know if it works
## Post #10
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-04T02:33:07+00:00
- Post Title: [release] Alien Isolation BML converter

very nice, works well.   But i did notice if I specify a target filename, it just prints the instructions, instead of processing. 

 Example: AlienBML  ADRIANA.BML out.xml

But if i only specify an input, it works.

Example: AlienBML  ADRIANA.BML
## Post #11
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-04T07:37:12+00:00
- Post Title: [release] Alien Isolation BML converter

that is so nice. i'm writing up a modded file immediately for the weapon settings. alien ai programming next.

edit: seems the game crashes with a modified file. guess it's not read yet
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-04T17:37:18+00:00
- Post Title: [release] Alien Isolation BML converter

thanks volfin, i submitted a fix for that

> Reply from odrin
>
> seems the game crashes with a modified file. guess it's not read yet

i'm all ears:

which file did you edit
what edits did you make (upload the files would be better)
## Post #13
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-05T01:39:54+00:00
- Post Title: [release] Alien Isolation BML converter

Well I did a simple test. I dropped a BML your converter so it changes to XML. Then i dropped that XML on your converter so it converts back to a BML.  Doing a diff of the two files, they should be identical, but they aren't. In fact were many, many differences. Even the file length changed. (original was longer) Nodes seem to change order, etc. I think that test would work with any BML, but for example I tried with FONT_CONFIG.BML
## Post #14
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-05T05:54:01+00:00
- Post Title: [release] Alien Isolation BML converter

the file i edited was "GBL_ITEM.BML"

i changed some settings like the amount of ammunition available for each fuel cell. default 25, i changed to 250, for example.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-05T15:26:38+00:00
- Post Title: [release] Alien Isolation BML converter

@WRS: GBL_item.BML -> XML, ok
Then gbl_item_noconflict.xml -> BML, smaller than original BML

That the BML filesizes differ should not be a problem (from my experiences with another game's binary/XML conversion)

I logged br.BaseStream.Position ('Start' from your code) when trying to convert the smaller BML to XML again:

```
  10096  176  10068  10096  10124  192
```

10184 Possible large number of attributes -> 239 (node=AlienBML.AlienString+Ref)
 142050 eof met, program break

(maybe it helps improving your tool)

Keep up this good stuff. (don't owe the game so far, so can't make more use of it)
## Post #16
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-05T19:58:56+00:00
- Post Title: Re: [release] Alien Isolation BML converter

my tool strips a lot of whitespace from the bml files. that's the only reason why the files are smaller.

whitespace isn't normally kept by xml parsers, so my tools makes some guesses.

diffing the binary bml data will never be identical. however, the xml will be perfect (hide whitespace and line ending differences in your diff tool).

i'll buy this game when it goes on sale to see how it's crashing.
## Post #17
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-05T23:03:27+00:00
- Post Title: Re: [release] Alien Isolation BML converter

so much for moddability of modern games...
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-06T04:37:31+00:00
- Post Title: Re: [release] Alien Isolation BML converter

I like how this is done in C#, I'll contribute more once volfin and I figure out the mesh stuff
## Post #19
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-08T01:08:52+00:00
- Post Title: Re: [release] Alien Isolation BML converter

fixed the main issue with bml exporting.

please test this version  
[AlienBML.zip](https://xentaxbackup.github.io/file/8215_AlienBML.zip)
## Post #20
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-09T03:48:21+00:00
- Post Title: Re: [release] Alien Isolation BML converter

great work. the crashing is gone. but the game is bypassing the changes i've made. goddamn developers...
## Post #21
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-09T17:37:59+00:00
- Post Title: Re: [release] Alien Isolation BML converter

> Reply from odrin
>
> great work. the crashing is gone. but the game is bypassing the changes i've made. goddamn developers...

thanks for the feedback.

try deleting the xml files with the same filename as the exported bml (i'm not sure if the xml or bml takes precedence)
## Post #22
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-12-10T02:30:48+00:00
- Post Title: Re: [release] Alien Isolation BML converter

nah, xml doesn't make a difference. thought it does seem like maybe something else is controlling whether these files are being read or not. because if both xml and bml files aren't being read, what's really being read?
## Post #23
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-02-13T02:19:10+00:00
- Post Title: Re: [release] Alien Isolation BML converter

> Reply from MyPwIsWAZAAA
>
> NO, the converter isn't working right !
i think there's something wrong when coverting xml back to bml,so all your modding won't be applyed in the game

hmm. the only difference is the whitespace storage - which should have no affect on any sensible binary xml format   

i'll take another look at my tool
