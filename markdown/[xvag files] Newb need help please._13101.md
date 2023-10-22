## Post #1
- Username: Neogamer789
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 25, 2015 6:37 am
- Post datetime: 2015-07-24T22:49:04+00:00
- Post Title: [xvag files] Newb need help please.

Hello everyone    I tried to extract sound files of the last of us and I did it   And now I have .xvag and I tried to deinterlave the files but I can't.   

I tried with this topic : [viewtopic.php?f=17&t=5014](http://forum.xentax.com/viewtopic.php?f=17&t=5014) (I don't understand anything with blocksize)
And here the files (just a sample) if you need: [https://mega.co.nz/#!xMsw0BSb!d_yaUWqJg ... pCGel7fnrg](https://mega.co.nz/#!xMsw0BSb!d_yaUWqJggHmHo6xvZzlTfSPm9ohQO18GpCGel7fnrg)


It would be realy nice if you help me (I will give you a free hug  )
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-24T23:33:08+00:00
- Post Title: [xvag files] Newb need help please.

The sample file you provided is just a stereo file that vgmstream can playback just fine 

You will only need to deinterleave the XVAG if it has more than two channels.

You can also tell if you need to deinterleave an XVAG file when you try to listen to it and it sounds disjointed and doesn't playback smoothly.
## Post #3
- Username: Neogamer789
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 25, 2015 6:37 am
- Post datetime: 2015-07-24T23:52:58+00:00
- Post Title: [xvag files] Newb need help please.

Thank you a lot   Just Winamp was missing    (I need to read readme carfully me)

You're just so cool guys   
And I've just one more question. It's possible to extract xvag files ?

And it's normal that some sounds are stuttering like this one [https://mega.co.nz/#!8Nd0QRwL!LivtTt9k0 ... 1GKI54E8f0](https://mega.co.nz/#!8Nd0QRwL!LivtTt9k0Wy3OL9xLL8Yl4BUJHDYBzZwv1GKI54E8f0)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-25T00:26:57+00:00
- Post Title: [xvag files] Newb need help please.

Extract? no as they are just audio files.

Deinterleave, yes 

If it stutters during playback, that means it's most likely more than two channels.

The file you provided is 4 channels, and also in the filename it says "quad" as well 

Header size is 0x134 which can be found at the offset 0x06
Number of channels is 4 which can be found at the offset 0x2B
INTSIZE is 0x3000

Any questions?
## Post #5
- Username: Neogamer789
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 25, 2015 6:37 am
- Post datetime: 2015-07-25T08:38:05+00:00
- Post Title: [xvag files] Newb need help please.

Yes   How do you find INTSIZE ?
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-25T13:45:30+00:00
- Post Title: [xvag files] Newb need help please.

Okay, I'll use the file you provided before, the stuttering file "amb-bed-tommys-dam-ext-quad.xvag"

INTSIZE can be found by going to the very end of the file using a hex editor.

There will be a whole section of "00"s

What you need to do is this: From the end of the file, you need to highlight all of the data starting from the very last 00 and scroll up the file until you encounter another section of "00"s just like there is at the end of the file. At the end of this new section of "00"s the first two bytes will be "FF FB" which is known as the MPEG flag.

Your highlighted selection should start on the "FF FB" immediately after that section of "00"s and go all the way to the very last byte of the file.

Copy and paste that highlighted part into a new file in your hex editor and the offset given at the end of this section you copied is the INTSIZE of a single interleave block

For this file, "amb-bed-tommys-dam-ext-quad" the INTSIZE is 0x3000
## Post #7
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-18T02:10:16+00:00
- Post Title: [xvag files] Newb need help please.

I converted the XVAG files from Resistance 2 with VGMStream, but the quality is iffy. What to do then?
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-19T15:48:25+00:00
- Post Title: [xvag files] Newb need help please.

Post the original XVAG file
## Post #9
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-19T16:48:21+00:00
- Post Title: [xvag files] Newb need help please.

[https://mega.nz/#F!s580xR4Y!G1-dlg0GCJ8uT8Ydpq9Ong](https://mega.nz/#F!s580xR4Y!G1-dlg0GCJ8uT8Ydpq9Ong)

The first 3 are VAG, FYI.
## Post #10
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-20T03:46:19+00:00
- Post Title: [xvag files] Newb need help please.

The XVAG files you posted playback just fine on vgmstream without any deinterleaving as they are just stereo files.

You only need to deinterleave the file if there is more than two channels.
## Post #11
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-09-20T16:55:30+00:00
- Post Title: [xvag files] Newb need help please.

> Reply from brendan19
>
> You only need to deinterleave the file if there is more than two channels.
But how can you deinterleave the file if there is more than two channels? The quickBMS script that deinterleaves the file didn't work for me, and I'm not talking about the one Researchman edited for XVAG for more than 2 channels or something since it uses an old revision.
## Post #12
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-20T17:48:57+00:00
- Post Title: [xvag files] Newb need help please.

But do you notice the quality? I'm pretty sure it's supposed to sound clearer than that.
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-21T15:15:47+00:00
- Post Title: [xvag files] Newb need help please.

> Reply from AnonBaiter
>
> But how can you deinterleave the file if there is more than two channels? The quickBMS script that deinterleaves the file didn't work for me, and I'm not talking about the one Researchman edited for XVAG for more than 2 channels or something since it uses an old revision.

Give me a file and I'll walk you through it 


> Reply from Cameron007
>
> But do you notice the quality? I'm pretty sure it's supposed to sound clearer than that.
The XVAGs playback just fine and they're 48kHz so I do not think so unless some post processing is applied to the audio tracks by the game.

The VAG files, maybe since they're mono and quite a low frequency. The only thing that comes to mind is if those tracks are coming through an old radio or something in the game which would explain using that fidelity and that's why they are that quality.
## Post #14
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-21T18:36:14+00:00
- Post Title: [xvag files] Newb need help please.

> Reply from brendan19
>
> AnonBaiter wrote:But how can you deinterleave the file if there is more than two channels? The quickBMS script that deinterleaves the file didn't work for me, and I'm not talking about the one Researchman edited for XVAG for more than 2 channels or something since it uses an old revision.

Give me a file and I'll walk you through it 

Cameron007 wrote:But do you notice the quality? I'm pretty sure it's supposed to sound clearer than that.
The XVAGs playback just fine and they're 48kHz so I do not think so unless some post processing is applied to the audio tracks by the game.

The VAG files, maybe since they're mono and quite a low frequency. The only thing that comes to mind is if those tracks are coming through an old radio or something in the game which would explain using that fidelity and that's why they are that quality.

Funny, some of the XVAG are only 32000 Hz. Maybe those are the ones that sound crappy.
## Post #15
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-09-21T22:18:59+00:00
- Post Title: [xvag files] Newb need help please.

> Reply from brendan19
>
> AnonBaiter wrote:But how can you deinterleave the file if there is more than two channels? The quickBMS script that deinterleaves the file didn't work for me, and I'm not talking about the one Researchman edited for XVAG for more than 2 channels or something since it uses an old revision.

Give me a file and I'll walk you through it
[Here you go.](https://www.sendspace.com/file/xf3b7g)
## Post #16
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-22T08:17:28+00:00
- Post Title: Re: [xvag files] Newb need help please.

This should do it for you 

```
set PRESERVE 1
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x1390 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 2
set SKIP 0 # area at start of each block to skip
```
## Post #17
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-09-22T13:44:21+00:00
- Post Title: Re: [xvag files] Newb need help please.

Does that work with the 2016-05-16 version of the script, though? Because I might be out of luck here...
[file_deinterleaver.rar](https://xentaxbackup.github.io/file/11725_file_deinterleaver.rar)
## Post #18
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-22T13:57:59+00:00
- Post Title: Re: [xvag files] Newb need help please.

Here's the 2012 script which does work with those parameters.

I did try with the latest version but I'd need to experiment with the script more to work it out.
[file_deinterleave.zip](https://xentaxbackup.github.io/file/11726_file_deinterleave.zip)
## Post #19
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-09-22T14:02:22+00:00
- Post Title: Re: [xvag files] Newb need help please.

Now that works.
However I have one question: what steps should I take when deinterleaving a .xvag with the script you gave me, especially when dealing with a .xvag file that has a different header like this one?

```
00000010  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000020  66 6D 61 74 00 00 00 24 00 00 00 08 00 00 00 08  fmat...$........
00000030  00 2B F2 00 00 2B F2 00 00 00 00 08 00 00 BB 80  .+ò..+ò.......»€
00000040  00 58 08 00 00 00 00 01 00 00 00 04 63 70 61 6E  .X..........cpan
00000050  00 00 00 90 00 00 00 08 00 00 00 00 00 00 00 3F  ...............?
00000060  00 00 00 00 80 00 00 01 00 00 00 00 00 00 00 00  ....€...........
00000070  00 00 00 00 80 00 00 02 00 00 00 00 00 00 00 00  ....€...........
00000080  00 00 00 00 80 00 00 01 00 00 00 00 00 00 00 00  ....€...........
00000090  00 00 00 00 80 00 00 02 00 00 00 00 00 00 00 00  ....€...........
000000A0  00 00 00 00 80 00 00 01 00 00 00 00 00 00 00 00  ....€...........
000000B0  00 00 00 00 80 00 00 02 00 00 00 00 00 00 00 00  ....€...........
000000C0  00 00 00 00 80 00 00 01 00 00 00 00 00 00 00 00  ....€...........
000000D0  00 00 00 00 80 00 00 02 00 00 00 00 00 00 00 00  ....€...........
000000E0  00 00 00 00 6D 70 69 6E 00 00 00 80 00 00 00 01  ....mpin...€....
000000F0  00 00 00 03 00 00 00 C0 00 00 BB 80 00 00 00 01  .......À..»€....
00000100  00 00 00 02 00 00 00 02 00 00 02 40 00 00 04 B1  ...........@...±
00000110  00 2B F2 00 00 00 02 1C 00 00 00 02 00 00 00 80  .+ò............€
00000120  00 57 F6 00 00 00 00 00 00 00 00 00 00 00 00 00  .Wö.............
00000130  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000140  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000150  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00000160  00 00 00 00 00 00 00 00 00 00 00 00 30 30 30 30  ............0000
00000170  00 00 00 00 FF FB B4 40 00 00 03 2D 13 4F C9 E9  ....ÿû´@...-.OÉé
```
But also to avoid this:

```
- open script E:\quickbms_scripts\file_deinterleave.bms
- set output folder E:\Journey_Collectors_Edition_PS3-ZRY\_BCUS98377-[Journey Collectors Edition]\PS3_EXTRA\D002\DATA000\NPUA70218\USRDIR\Data\Sounds\Streams\mus

  offset   filesize   filename
--------------------------------------
- SCRIPT's MESSAGE:
  Error: file size minus header isn't dividable by blocksize! Aborting...
```
I mean, sure, I might be avoiding these problems by myself sometime but I still need some tips.
## Post #20
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-22T15:09:40+00:00
- Post Title: Re: [xvag files] Newb need help please.

Is there no way to set output frequency in VGMStream?
## Post #21
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-23T06:49:59+00:00
- Post Title: Re: [xvag files] Newb need help please.

> Reply from Cameron007
>
> Is there no way to set output frequency in VGMStream?
You'd need to change the frequency in the file header. vgmstream reads the header information and then plays it at that. Changing the output frequency won't increase the fidelity but instead make it playback faster or slower.

> Reply from AnonBaiter
>
> Now that works. However I have one question: what steps should I take when deinterleaving a .xvag with the script you gave me, especially when dealing with a .xvag file that has a different header like this one? I mean, sure, I might be avoiding these problems by myself sometime but I still need some tips.

You need to adjust the script as needed for the xvag files.


Header size can be found at offset 0x06

If you look at the code you just posted, "01 74" is the header size so you'd put 
set HEADER 0x174

And if you look, at offset 0x175 we see the first "FF FB" which is the MPEG frame flag. So that also confirms that is the correct size of the file header.


The number of layers can be found at offset 0x2B. However this number needs to be divided by two.

So if you see "08" at 0x2B you put 
set LAYERS 4

If you see "06" at 0x2B you put
set LAYERS 3

etc


To work out the size of a single interleave block, 

1. Go to the very end of the file in your hex editor. It should be a block of 00s

2. Select and highlight all of the data from the last 00 in the file all the way up until you reach another block of 00s (Your highlighted data should start with FFFB and end with the last 00 of the file)

3. Copy and paste this into a new file in your hex editor.

4. Scroll to the bottom of the newly created file. The final offset number will represent a single interleave block for that file.

This will give you the INTSIZE so the script can successfully deinterleave the file.
## Post #22
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2016-09-23T13:59:51+00:00
- Post Title: Re: [xvag files] Newb need help please.

I guess I'll need a hex editor for that?
## Post #23
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-09-23T17:54:40+00:00
- Post Title: Re: [xvag files] Newb need help please.

Yes you will
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-17T07:41:23+00:00
- Post Title: Re: [xvag files] Newb need help please.

XVAG splitter:

[viewtopic.php?f=17&t=15612](http://forum.xentax.com/viewtopic.php?f=17&t=15612)
## Post #25
- Username: Hereisme
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 15, 2017 3:55 am
- Post datetime: 2017-01-14T19:59:08+00:00
- Post Title: Re: [xvag files] Newb need help please.

How do i convert mp3 or wav or any other sound format to xvag?
