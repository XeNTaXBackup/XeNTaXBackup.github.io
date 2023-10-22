## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-29T13:07:40+00:00
- Post Title: Using highlights to help figure out formats

Recently I was looking at some references and noticed that someone wrote it using an 010 editor template.
I don't use templates very often, but it would be pretty nice if you could write up a template and apply it to multiple open documents at the same time. In 010 editor at least, the template highlights stuff based on the definitions you write.

I haven't used too many different hex editors out there (HxD, hexworkshop, and some other pretty simple ones), but 010 editor is pretty nice.

Basically, all you have to do is while writing up structs, you can check that the format matches different files.
You can quickly identify where the issues are and possibly pick up patterns that you otherwise wouldn't be able to without the visual aid.

The syntax looks pretty easy as well, so this might be something to consider.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-08-29T15:09:41+00:00
- Post Title: Using highlights to help figure out formats

I've heard a lot about 010 Editor, but the $50 price tag has ensured I probably won't be able to do much with it for a while now; the free trial only lasts 30 days.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-29T20:19:05+00:00
- Post Title: Using highlights to help figure out formats

i use 010 daily but it took a while to convince myself to buy it (esp. with a fully functioning trial).

the scripting and templates are not just ideal but practical to map out a file format. the structures you create can be used in your c/c++ sources (+ vise-versa) and there are tons of little features like copying hex as c-code which saves so much time.

as a special bonus for me it works well on linux with wine - it can read large files much faster than other native hex editors like bless - which is otherwise ok
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-29T22:02:11+00:00
- Post Title: Using highlights to help figure out formats

Hmm interesting...  I could and should make my own hex editor too. Anyone interested in an open source community hex editor?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-29T22:57:45+00:00
- Post Title: Using highlights to help figure out formats

I've seen a couple open source hex editors, though I never actually tried them.

I like 010 cause it does a lot of calculations for me in a side panel, which is probably the main reason I use it cause I don't look at hex very much anyways.

The other ones that are suggested quite often are things like HxD or hex workshop or some other really light-weight (meaning, you can only read/write files in hex, nothing else lol) don't have all of those cool things cluttering the screen.

HOWEVER, I would like a hex editor that will perform binary operations in real-time, so if I didn't have any techniques to figure out some simple encryption like XOR, maybe I'll just type in random numbers for maybe 200-300 bytes and see what I get o.O
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-30T14:44:30+00:00
- Post Title: Using highlights to help figure out formats

> Reply from finale00
>
> HOWEVER, I would like a hex editor that will perform binary operations in real-time, so if I didn't have any techniques to figure out some simple encryption like XOR, maybe I'll just type in random numbers for maybe 200-300 bytes and see what I get o.O

that's where scripting comes in!

```
ubyte test_area[ TESTNUM ]
local int i; local ubyte j;
for(j=0;j<256;j++)
{
  Printf("XOR %02X - ", j);
  for(i=0;i<TESTNUM;i++) Printf("%02X ", test_area[i] ^ j);
  Printf("\n");
}

```
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-30T15:09:22+00:00
- Post Title: Using highlights to help figure out formats

Oh, you can do that sort of thing in 010 as well.
Pretty cool.
