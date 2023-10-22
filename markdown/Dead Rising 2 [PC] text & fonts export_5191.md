## Post #1
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-12T22:55:20+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

Does anyone know how i can export texts from the game??? I want to translate it to my language but everytime i try to edit "str_en.bcs" the game crashes 
file:
```
http://www.megaupload.com/?d=TKFE3ACO
```
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-12T23:53:58+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

```

for i = 0 < ITEMS
  get ITEMID long # assumed; if so, this doesn't need editing
next i

for i = 0 < ITEMS
  get ITEMSTRPTR long # string pointer
next i

for i = 0 < ITEMS
  get ITEMSTR string # null-terminated string
next i

# then padded, unsure of importance

```


any strings you change will affect the ITEMSTRPTR values following it IF the length changes - which is very likely..
not sure if the game could support different encoding, or how it treats such characters.

hope you can work with this.
## Post #3
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-13T00:17:16+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

sorry i am new here  where i must copy this script?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-13T09:55:20+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

> Reply from prudislav
>
> sorry i am new here  where i must copy this script?

its for [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip). just save the script as a text file and select it when you run quickbms.
it doesn't dump anything though - its just the structure of the format.
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-13T12:32:00+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

I created a simple BCS <-> TXT converter util. I hope that works.
 Usage:
BCS_TXT.exe <file.BCS>
       or:
BCS_TXT.exe <file.TXT>
Example:
BCS_TXT str_en.bcs  ----> this will decode the str_en.bcs file to str_en.txt.
BCS_TXT str_en.txt  ----> this will encode the str_en.txt file to str_en.bcs.
Warning! The existing files will be overwritten without asking!

PROGRAM UPDATE: Now the text file saved in UTF-8 format! Maybe this will be better, than the old, Ansi format was.

[Attached file deleted. See my latest comment for the most recent version of the program.]
## Post #6
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-13T15:01:48+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

thank you very much
EDIT: but game doesn't support centraleuropean charset (letters like "ěščřž")
## Post #7
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-10-13T17:25:04+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

thanks bacter, nice job

but unfortunately it doesn't decode Russian version, looks like can't support Unicode or like thing, or may be character encoding isn't known
## Post #8
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-14T17:36:14+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

does anyone knows where is fonts and how can i edit them to Central Europena charset(ěščřžýáíéúů)?
## Post #9
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-14T22:57:53+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

I think that fonts are hidden in these files : 
```
http://www.megaupload.com/?d=QF24XDAT
```
## Post #10
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-10-16T09:56:59+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

Thank you, bacter, good job.
How can we export the fonts?
## Post #11
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2010-10-18T03:44:49+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

> Reply from Gocha
>
> thanks bacter, nice job

but unfortunately it doesn't decode Russian version, looks like can't support Unicode or like thing, or may be character encoding isn't known

Your're correct , the strings are encoded in UTF-8. Just add UTF-8 translation to the script and you're done.
## Post #12
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-10-19T10:08:50+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

> Reply from dogkarl
>
> Gocha wrote:thanks bacter, nice job

but unfortunately it doesn't decode Russian version, looks like can't support Unicode or like thing, or may be character encoding isn't known

Your're correct , the strings are encoded in UTF-8. Just add UTF-8 translation to the script and you're done.

How can I do that?
Sorry, I'm new in this job.
## Post #13
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-10-20T04:58:05+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

> Reply from qabRieL
>
> dogkarl wrote:Gocha wrote:thanks bacter, nice job

but unfortunately it doesn't decode Russian version, looks like can't support Unicode or like thing, or may be character encoding isn't known

Your're correct , the strings are encoded in UTF-8. Just add UTF-8 translation to the script and you're done.

How can I do that?
Sorry, I'm new in this job.
+1 
Can you make program for Russian text? 
Here is a file from Russian version - [http://www.multiupload.com/T3YD5E6CUX](http://www.multiupload.com/T3YD5E6CUX)
## Post #14
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2010-10-20T09:00:28+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

i start translating to my language but when i try to ply with edited text game donts save progress
## Post #15
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-11-05T06:28:22+00:00
- Post Title: Dead Rising 2 [PC] text & fonts export

bacter,
I think it still have problem with Russian ecnoding, but i'm not sure of it.

You better make converter with support of ASCII table chars, and there codes for Russian chars are from 192 to 255
## Post #16
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-02-02T11:56:33+00:00
- Post Title: Re: Dead Rising 2 [PC] text & fonts export

Here's the source code (in Delphi) of my util.
(Requested by qabRieL)
## Post #17
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-02-02T13:02:05+00:00
- Post Title: Re: Dead Rising 2 [PC] text & fonts export

Thank you.
## Post #18
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2012-12-13T19:42:16+00:00
- Post Title: Re: Dead Rising 2 [PC] text & fonts export

> Reply from bacter
>
> I created a simple BCS <-> TXT converter util. I hope that works.
 Usage:
BCS_TXT.exe <file.BCS>
       or:
BCS_TXT.exe <file.TXT>
Example:
BCS_TXT str_en.bcs  ----> this will decode the str_en.bcs file to str_en.txt.
BCS_TXT str_en.txt  ----> this will encode the str_en.txt file to str_en.bcs.
Warning! The existing files will be overwritten without asking!

PROGRAM UPDATE: Now the text file saved in UTF-8 format! Maybe this will be better, than the old, Ansi format was.

[Attached file deleted. See my latest comment for the most recent version of the program.]
any chance to reupload this file???
## Post #19
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2018-12-25T03:42:47+00:00
- Post Title: Re: Dead Rising 2 [PC] text & fonts export

> Reply from qabRieL
>
> Thank you, bacter, good job.
How can we export the fonts?
yes how can we export and import [pack & unpack] .bcf font files??
for DR2 & DR3 & DR4..??
thanks
