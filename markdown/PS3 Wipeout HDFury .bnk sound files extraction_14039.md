## Post #1
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-03-01T20:39:11+00:00
- Post Title: PS3 Wipeout HD/Fury .bnk sound files extraction

Hi mates,

I've been trying to deal with the wipeout fury/hd audio banks (.bnk) for 2 weeks and I didn't get any result, I tried quickbms, wwxmbank, bnkfileeditor, bnkextr and i always get the unrecognised file format.

So i tried to open it with hexedit and in the file header you can read klBS instead of KNAB or BKHD, so I supposed that they are encrypted or something, so i'm asking if there is some way to decrypt or extract those bank files. I will attach you 2 bnk files so you can try them because I lost all the fate on them.

Google Drive link: [https://drive.google.com/file/d/0B9dy0w ... sp=sharing](https://drive.google.com/file/d/0B9dy0wb-EfqPbnNhbkZDTXExbHM/view?usp=sharing)

Ty to all of u.

First Bytes shiphd.bnk

```
 Ÿô  g¦°klBSTÎÖ@0P@g¦°g¦°* –Lxÿÿÿødd `d(`d
```


Last bytes shiphd.bnk

```
Ï‹ä
```
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-02T18:11:43+00:00
- Post Title: PS3 Wipeout HD/Fury .bnk sound files extraction

> Reply from josema0890
>
> I supposed that they are encrypted or something

No. Not encrypted. These are just some other bank format.

You can decode audio without knowing the format though. Use vgmtoolbox, and it's famous feature to decode PS ADPCM.
## Post #3
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-03-02T22:36:05+00:00
- Post Title: PS3 Wipeout HD/Fury .bnk sound files extraction

> Reply from daemon1
>
> josema0890 wrote:I supposed that they are encrypted or something

No. Not encrypted. These are just some other bank format.

You can decode audio without knowing the format though. Use vgmtoolbox, and it's famous feature to decode PS ADPCM.

Wow daemon   , thank you very much, you are amazing, I downloaded vgmtoolbox, extracted them on .bin and droped them on ADPCM Player 1.44h, i played with the values a little and i found the perfect ones, Freq. to 50K Channels to 1 and interleave to 40 and boom, magic done, i owe you a big one.

EDIT 03/03: While I can grab some files, the program sometimes doesn't export the sounds from a bank, but anyways, something is more than nothing, so far i get 253 sounds, ty again
## Post #4
- Username: xengi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 25, 2017 1:58 am
- Post datetime: 2017-07-24T23:56:53+00:00
- Post Title: PS3 Wipeout HD/Fury .bnk sound files extraction

I'm currently on the hunt for these files. I need the weapon pickup sounds. I've copied all the files from the Wipeout HD disc but couldn't extract the psarc files. I tried getting the bnk files from the playstation harddrive but I can't mount it.

How did you get the bnk files?
Which tools did you use?
If you have the files with the weapon pickup sounds can you upload it somewhere or tell me how I can get them? Would be nice to know how it works ether way.
