## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-07T02:27:28+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

I was running through the main BIN file cutting it down as I went into several AFS files stacked over each other then I came to this file with a header called LZR. I've tried extracting and converting the TIM2's but apparently the LZR indicates that they are LZR compressed. Here's a link to the cut down file:

[LINK HERE](https://www.yousendit.com/download/Q01HRm8xSWh6RTlFQlE9PQ)

Also don't worry about the WHOLE BIN, it had no header or anything special to it of it's own, just a bunch of files in it starting from the beginning. There MAY be more LZR archives after it. If anybody can crack this, THANKS.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-07T02:43:54+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Here's also an extract from that large BIN (But not as big as it was with the AFS files XD;;
[LZREXTRACT.rar](https://xentaxbackup.github.io/file/1604_LZREXTRACT.rar)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-07T06:04:55+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

ALSO, here is another ripped LZR file, it contains a TIM2 file as you can see which I tried ripping VIA Jaeder Naub and then using TIM2TGA and various other tools to convert them. All failed miserably. So obviously something is up with the TIM2s.
[LZREXTRACT2.rar](https://xentaxbackup.github.io/file/1605_LZREXTRACT2.rar)
## Post #4
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-08-07T18:58:02+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

i have the game back from when i was experimenting with the sfdmux thingie
video club's owner on vacation and we get to keep what we have free of charge until he comes back
i will take a look later...
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-07T21:11:01+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Hey, thanks! My automatic assumption is that LZR says it is using the LZR compression algorithm or a variation thereof. The LZR header being a way of telling that this chunk is using that algorithm. Other than that I have had no success decompressing the data.

Edit: The ELF file is around 10MBs which means it contains something. I'll check it out.

Yep, it is as I thought. The ELF file has ALL the info built in especially the indexing and LZR info. Also there seems to be just common TIMs in there, not just TM2s. There seems to be a decode string for LZR in the ELF... hm...
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-17T11:36:52+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Sorry to bump but has there been any leads on decompressing the TM2 files? Either they are a compressed/encryption method or the TM2's are modified or something making it hard to convert. Still, is it possible to correct this little situation? Like something to mass decompress/decrypt the files?
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-29T13:14:39+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Sorry to bump again but is there any news? Strangely this LZR format prevents me from converting the TIM2s... are the TIM2's really compressed? Or is it an encryption? Whatever it is, it has made them unreadable.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-02T12:40:52+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Additionally! This same compression is uused in the Atelier Iris titles,

Here's an example from Atelier Iris - Eternal Mana. It may hold the same style.

I really wonder if this can be decompressed... it seems like a variant of LZSS, however tools I have tried for LZR compression/decompression have given incorrect results...
[TIM2.tm2.rar](https://xentaxbackup.github.io/file/1626_TIM2.tm2.rar)
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-08T13:07:29+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Hm, looked a bit more into it. Apparently LZR is as it says. But I'm uncertain if it IS LZR specifically or a LZR derived compression... I've tried some decomp tools for LZSS and LZR tools but got little results.

Closest thing I had to a breakthrough was a non-obtainable plugin for Total Commander that supported some LZR compression.

edit: Tried that plugin, it did not decompress the files. Not sure what to do. All I know is that the LZR is said to be the basis for ZIPs but it doesn't look at all like a ZIP... it seems like a purely LZR compressed file and not an archive of any sort.

Hm... LZ77 variant? Dang this is bothersome... can't seem to find sufficient data on this.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-10T21:55:18+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

I think I found a rather difficult workaround for the compression using PCSX2 by making a data dump but this is of course timely and apparently I can't use Jaeder Naub to find them automatically (doesn't detect the correct length). So far I've only managed to use a hex editor to extract the title screen. It is off a bit mind you, I'm not completely accurate on the hex extractions but it proved that, if uncompressed, are just average TIM2s and any TIM2 program can process them.
[dump.tm2.png](https://xentaxbackup.github.io/file/1638_dump.tm2.png)
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-10T22:05:34+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Here's how the image looks after fixing it up some.

Edit: It'd still be nice to decompress the LZR files though. This method is rather limited and bears some odd results. (like the multiple image TIM2s that are currently nonconvertible)
[dump.tm2perfect.png](https://xentaxbackup.github.io/file/1639_dump.tm2perfect.png)
## Post #12
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2008-09-12T17:26:30+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Nice!
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-12T20:10:30+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Yeah, sadly there is a second form of TIM2 that doesn't convert properly.
## Post #14
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2008-12-20T06:49:22+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

Hello,

Please can anyone help me how to decompress the file RPK.bin which was compress by LZR in atelier iris games?

I really need your help.
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-01-02T00:08:56+00:00
- Post Title: Mana Khemia (PS2) LZR Compression? Certainly compressed!

It would be beneficial to be able to decompress these files as VRAM seems to splice several TIM2s into one instance.
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-06-09T09:25:33+00:00
- Post Title: Re: Mana Khemia (PS2) LZR Compression

Bumping this with some LZR files taken from RPK.BIN. The compression is a familiar routine but I just can't seem to get anything to work with it.

These are from Atelier Iris, a directly related game.

Perhaps the libLZR source would be useful here: [http://www.psp-programming.com/benhur/](http://www.psp-programming.com/benhur/)
[LZRFiles.rar](https://xentaxbackup.github.io/file/2091_LZRFiles.rar)
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T10:37:07+00:00
- Post Title: Re: Mana Khemia (PS2) LZR Compression

no, doesn't seem LZR.
I have spent various time using LZRDecompress on various blocks at the beginning without success.
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-06-09T19:52:27+00:00
- Post Title: Re: Mana Khemia (PS2) LZR Compression

Hm... then what is this compression that is used?
## Post #19
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-06-21T09:10:05+00:00
- Post Title: Re: Mana Khemia (PS2) LZR Compression

The LZR format has already been cracked.

[viewtopic.php?f=18&t=2933](http://forum.xentax.com/viewtopic.php?f=18&t=2933)

I'll attach the file here that contains the working UNLZR program from the website.
[exar2.zip](https://xentaxbackup.github.io/file/2147_exar2.zip)
