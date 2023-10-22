## Post #1
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-04-02T09:55:04+00:00
- Post Title: Still Life 2 DAT

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-03T14:22:37+00:00
- Post Title: Still Life 2 DAT

Can you post the main program exe file to help look at the encryption or what the file is used for.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-04-03T18:02:32+00:00
- Post Title: Still Life 2 DAT

oh sorry, i did it myself i forgot about this thread xD

here's the xor key if someon is interested. The archives are pretty easy after the decryption.

```
2923BE84E16CD6AE529049F1F1BBE9EB
```
## Post #4
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-04T03:24:16+00:00
- Post Title: Still Life 2 DAT

Can you make a extractor for this game?
Vey thanks!
## Post #5
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-04-05T13:16:03+00:00
- Post Title: Still Life 2 DAT

Any one can give a file format of this file?
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-04-07T17:23:03+00:00
- Post Title: Still Life 2 DAT

LOL it's easiest than i thought.
after xored the archives the formati is this:

0x04 //"GMGB"
0x04 //Number of files

for each file {

0xX path and filename
0x01 0x00
0x04 file length
0x01 0x00
}
## Post #7
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-08T00:55:24+00:00
- Post Title: Still Life 2 DAT

Darn I'm a noob at encryption, how can we apply to xor key to the existing file to make the strings right again? Is there a tool or something? Then we'd just have to extract the files out via hex editor right, since the archives aren't compressed?
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-08T03:26:44+00:00
- Post Title: Still Life 2 DAT

> Reply from pietastesgood
>
> Darn I'm a noob at encryption, how can we apply to xor key to the existing file to make the strings right again? Is there a tool or something? Then we'd just have to extract the files out via hex editor right, since the archives aren't compressed?

you can use bugtest's  great tool.
[xor.zip](https://xentaxbackup.github.io/file/1957_xor.zip)
## Post #9
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-08T03:41:27+00:00
- Post Title: Still Life 2 DAT

Terrific, thanks man.

Edit: The tool works great, but I can't seem to find any headers in the new file. Is the file compressed or something? If so, what should I do next? (I'm a n00b)

I'm using Sl2data.dat, not the other huge dat files with the game data from the game.
## Post #10
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-08T09:12:29+00:00
- Post Title: Still Life 2 DAT

> Reply from pietastesgood
>
> Terrific, thanks man.

Edit: The tool works great, but I can't seem to find any headers in the new file. Is the file compressed or something? If so, what should I do next? (I'm a n00b)

I'm using Sl2data.dat, not the other huge dat files with the game data from the game.

You need set the xor key in binary.
So, you maybe get a incorrect file.
## Post #11
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-04-08T09:52:08+00:00
- Post Title: Still Life 2 DAT

i'll write down something today or tomorrow..
## Post #12
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-08T14:42:24+00:00
- Post Title: Still Life 2 DAT

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-08T22:13:29+00:00
- Post Title: Still Life 2 DAT

The contents of this post was deleted because of possible forum rules violation.
[key.rar](https://xentaxbackup.github.io/file/1959_key.rar)
## Post #14
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-08T23:54:18+00:00
- Post Title: Still Life 2 DAT

Awesome, it worked. Thanks steven!
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-08T23:57:39+00:00
- Post Title: Still Life 2 DAT

or directly:
xor.exe Sl2_de.dat new.dat 0x2923BE84E16CD6AE529049F1F1BBE9EB
## Post #16
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-09T01:25:59+00:00
- Post Title: Re: Still Life 2 DAT

Thanks bugtest, your method works as well.
## Post #17
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-12T09:01:23+00:00
- Post Title: Re: Still Life 2 DAT

Is there any news about still life 2 extractor?
## Post #18
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-14T04:56:27+00:00
- Post Title: Re: Still Life 2 DAT

Apparently not, however, once you apply the xor you can simply scan the files with Nova Extractor if you're too lazy to extract by hex and get the files. Unfortunately if you use Nova you can't get the file names.
## Post #19
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-04-14T09:42:25+00:00
- Post Title: Re: Still Life 2 DAT

I'm sorry but i'm very busy in these days...i'll write it as soon as i can
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-17T14:37:43+00:00
- Post Title: Re: Still Life 2 DAT

I have written and attached the script for extracting the files of still life 2 (note, you need the quickbms tool linked in the comments in the file).
example: quickbms.exe stillife2.bms c:\Sl2data.dat c:\folder
[stillife2.zip](https://xentaxbackup.github.io/file/1967_stillife2.zip)
## Post #21
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-04-17T14:51:13+00:00
- Post Title: Re: Still Life 2 DAT

> Reply from Bugtest
>
> I have written and attached the script for extracting the files of still life 2 (note, you need the quickbms tool linked in the comments in the file).
example: quickbms.exe stillife2.bms c:\Sl2data.dat c:\folder

Very thanks.
## Post #22
- Username: Energy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 19, 2010 9:05 am
- Post datetime: 2010-03-21T14:18:49+00:00
- Post Title: Re: Still Life 2 DAT

Working thanks.
## Post #23
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2011-05-29T16:50:49+00:00
- Post Title: Re: Still Life 2 DAT

Hi,

can anyone write the instructions for getting extracted files back to the .dat archive? Thank you
