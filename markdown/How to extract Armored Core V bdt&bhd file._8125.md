## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-01-25T21:04:03+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Hi.
Could you guys help me in unpacking bdt&bhd files?
Here's a sample of the dvdbnd.bdt and dvdbnd5.bhd.
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-26T07:37:10+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

The bdt&bhd for Armored Core V is very similar to Dark Souls.
Did you try [viewtopic.php?f=10&t=7852&start=0](http://forum.xentax.com/viewtopic.php?f=10&t=7852&start=0)
May be sib file is container for model. tpf is texture?

```
N:\ACV\data\model\map\m0600\model_sib\m0005.sib
```
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-01-26T09:54:21+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Ok, i did it.
But, an error occurred while unpacking.

And dvdbnd.bdt have a different header from Dark Souls's bdt.

```
BDF311I12W39
```
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-27T05:32:44+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Try this.

```
offzip -a dvdbnd.bdt extract 0x0
```

Unfortunately, this batch script did not complete,
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-01-27T06:44:54+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Thanks dj082502.

Here is a little bigger bdt file and bnd(have  BND3JP100 header) file

I need to get help from somebody.
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-01-27T17:38:00+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

I'm also looking for a way to unpack bdt files.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-03-25T15:28:44+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Just use my script. func_getTYPE.bms can be found here: [viewtopic.php?f=13&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577). Just save it in the same directory as the below script.

```
# supported games: Armored Core V (Xbox 360)
#
# (c) 2012-03-25 by AlphaTwentyThree of XeNTaX

include "func_getTYPE.bms"
open FDDE bhd 0
open FDDE bdt 1

endian big
idstring "BHD5" 0
get ZERO long 0
get UNK long 0
get FSIZE long 0
get GROUPS long 0 # file groups?
get UNK long 0
set FNUMB 0
for i = 1 <= GROUPS
	get FILES long 0 # number of files of same group
	get INFO long 0
	savepos MYOFF 0
	goto INFO 0
	for j = 1 <= FILES
		get NAME_CRC long 0
		get SIZE long 0
		get ZERO long 0
		get OFFSET long 0
		get NAME basename 0
		callfunction constructname 1
		endian little
		callfunction getTYPE 1
		endian big
		string NAME += EXT
		log NAME OFFSET SIZE 1
	next j
	goto MYOFF 0
next i

startfunction constructname
	math FNUMB += 1
	string NAME += "_"
	string NAME += i
	string NAME += "~"
	string NAME += FNUMB
	string NAME += "_0x"
	string NAME_CRC p= "%08x" NAME_CRC
	string NAME += NAME_CRC
endfunction
```
## Post #8
- Username: donkepunch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 23, 2012 7:42 am
- Post datetime: 2012-03-27T10:05:02+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Please tell me what I'm doing wrong. 

1) I copied the script above and paste it in Notepad and named it Armored Core V with .bms extension. Saved in directory with dvdbnd.bdt

2) I copied func_getTYPE.bms from viewtopic.php?f=13&p=69577#p69577 and paste it in Notepad and named file func_getTYPE with .bms extension. Saved in directory with dvdbnd.bdt

3)Created a folder named Extractedbnd in directory. Opened Quickbms GUI, selected Armored Core V.bms (script), selected dvdbnd.bdt (archive), selected folder Extractedbdt as output directory

4) error in src\file.h line 178: myfopen <>
    Error no such file or directory
## Post #9
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-27T12:38:09+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

> Reply from donkepunch
>
> Please tell me what I'm doing wrong. 

1) I copied the script above and paste it in Notepad and named it Armored Core V with .bms extension. Saved in directory with dvdbnd.bdt

2) I copied func_getTYPE.bms from viewtopic.php?f=13&p=69577#p69577 and paste it in Notepad and named file func_getTYPE with .bms extension. Saved in directory with dvdbnd.bdt

3)Created a folder named Extractedbnd in directory. Opened Quickbms GUI, selected Armored Core V.bms (script), selected dvdbnd.bdt (archive), selected folder Extractedbdt as output directory

4) error in src\file.h line 178: myfopen <>
    Error no such file or directory
You should update your QuickBMS.
[QuickBMS generic files extractor and reimporter 0.5.9b (quickbms)](http://aluigi.org/papers/quickbms.zip)
## Post #10
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-27T14:15:25+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

Many thanks for script. It's a big surprise.
## Post #11
- Username: donkepunch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 23, 2012 7:42 am
- Post datetime: 2012-03-27T15:42:12+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

> Reply from dj082502
>
> donkepunch wrote:Please tell me what I'm doing wrong. 

1) I copied the script above and paste it in Notepad and named it Armored Core V with .bms extension. Saved in directory with dvdbnd.bdt

2) I copied func_getTYPE.bms from viewtopic.php?f=13&p=69577#p69577 and paste it in Notepad and named file func_getTYPE with .bms extension. Saved in directory with dvdbnd.bdt

3)Created a folder named Extractedbnd in directory. Opened Quickbms GUI, selected Armored Core V.bms (script), selected dvdbnd.bdt (archive), selected folder Extractedbdt as output directory

4) error in src\file.h line 178: myfopen <>
    Error no such file or directory
You should update your QuickBMS.
QuickBMS generic files extractor and reimporter 0.5.9b (quickbms)

I have latest version...Regardless, I overwrote my current files with the latest and still the same problem  Thanks for your efforts. Can anyone help?
## Post #12
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-28T01:54:06+00:00
- Post Title: How to extract Armored Core V bdt&bhd file.

I can't find model container file I'm looking for.
Does anyone know how to extract the BND311G21U40 files
Mr. donkepunch
Maybe, these are only for Xbox360.
