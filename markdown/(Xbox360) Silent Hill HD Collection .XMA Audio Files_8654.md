## Post #1
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2012-03-28T15:09:29+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

Is there a script or converter for the Xbox360 .XMA files? I have tried to scan it with Psound and Cube Media Player but it shows there's nothing in there. Is it encrypted?

Also would you guys like a .XMA sample to help? Also I opened it up with a hex editor and it says "RIFF WAVE fmt" in it if that means anything.

Thanks guys
## Post #2
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2012-03-28T18:41:43+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

hcs will be your guy to help on this one, i tried but i haven't used xma_parse for ages so there's no way i'm thinking in the correct frame of mind but if you want some sort of audio, here's a brief outline.

for reference, i've only explored the sound files in "\sh2_360\data\sound\adx\apart\" so can't say if this will work on the other files.

For any of the sound files (i will use "bgm_10100000.xma" for my example), open them up in a hex editor, find the very first instance of "data" then 4 bytes on from this, delete the beginning part of the file so the beginning of the file should look like the following

"7C 00 01 03 02 85 FC 01 C0"

now save the file & we use hcs's xma_parse ([http://www.hcs64.com/files/xma_parse09.zip](http://www.hcs64.com/files/xma_parse09.zip)), & do the following to deinterleave a stream (i forget the process of doing this for all the streams which is why hcs will be able to help you alot more but at least you know it's not encrypted)

xma_test bgm_10100000.xma -o 0 -b 10000 -r bgm_10100000_1.xma

you will now have an output file "bgm_10100000_1.xma"

now combine it with an xma header ([http://www.hcs64.com/files/xma_header.zip](http://www.hcs64.com/files/xma_header.zip))
(copy /b bgm_10100000_1.xma + header2 bgm_10100000_1_header.xma)

now you have the file "bgm_10100000_1_header.xma"

you can now decode this with towav  ([http://www.hcs64.com/files/towav.zip](http://www.hcs64.com/files/towav.zip))

hope that's helped & sorry for the rough guide
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-28T23:43:43+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

towav is the primary tool for decoding XMA, you should try that first as it may work without any additional trouble.

Otherwise, get xmash (at the bottom of [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html) ), it will do a lot of the conversion needed to get things in shape for towav (header generation, demuxing, rebuilding).  It doesn't work on every format, though, so if that doesn't work you may need to do some more manual work.  Uploading a sample would be a good first step.
## Post #4
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2012-03-29T00:35:07+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

Well im stuck at the first part. im using the same file as you but i opened it with a Hex editor and im confused on what im suppose to delete. =S I have always been wanting to learn how to use a hex editor so i guess ill start now. Where is the first instance of data? and i dont see where "7C 00 01 03 02 85 FC 01 C0". Sorry if im being difficult.   

I also tried using xmash and it came out with multiple xma and pos files so and I dragged the file on towav and it did nothing. Unless im supposed to do other things?
## Post #5
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2012-03-29T01:54:59+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

i knew hcs would know it, his xmash tool does it perfectly...

when it outputs loads of xma files & pos files, put towav in the same directory along with "ConvAll.bat" (which also comes with towav) then double click ConvAll.bat & it will do them 

So ignore everything i said before, just use hcs's xmash tool like you already did, making sure towav & convall are also in the same directory when double clicking convall.bat after getting all the multiple xma & pos files (pos files are not needed)
## Post #6
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2012-03-29T02:15:11+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

Okay it worked. I guess all the xma files had to bee in there. Is there anyway I can learn the manual way just in case some programs wont work?
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-29T05:07:13+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

btw, if you put those .pos files in the same dir as the .wav files, you can play/decode the .pos files with vgmstream and it will loop properly.
## Post #8
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2012-03-29T16:58:17+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

Okay thanks guys one more thing. What about .snd and sdb. I tried to open the .snd files with quicktime and WMP but it couldnt play it. thanks.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-01T03:33:39+00:00
- Post Title: (Xbox360) Silent Hill HD Collection .XMA Audio Files

Regarding XMA: Only in a few rare cases can XMA files be decoded by toWAV without manipulation.
For all other cases you'll need:
- my stream stripper that automatically deletes the header: [viewtopic.php?f=13&p=63096#p63096](http://forum.xentax.com/viewtopic.php?f=13&p=63096#p63096)
- if the stream is XMA2, HCS' xma parser: [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html) (xma_parse)
- my XMA header adder for the parsed file (or unparsed if already XMA1): [viewtopic.php?f=13&p=46731#p46731](http://forum.xentax.com/viewtopic.php?f=13&p=46731#p46731)
With these three tools I've converted all XMA files I've found so far. If something isn't working, I always update my scripts.
