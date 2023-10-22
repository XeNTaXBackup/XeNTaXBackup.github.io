## Post #1
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-05-13T14:28:15+00:00
- Post Title: WWise RIFF Vorbis format?

Hi,

(Recently?) CCP changed all their music into a custom ".ogg" format which turns out to be Vorbis inside a custom RIFF container identified as "WAVE" and has nothing to do with Ogg.

A sample file is here: [http://dl.getdropbox.com/u/773354/1.riffvorb](http://dl.getdropbox.com/u/773354/1.riffvorb)

Here's what I know so far:

There are 3 blocks in the RIFF file, "fmt ", "vorb" and "data". "fmt " seems to be the same as in a WAVE file and has valid data but the format is set to 0xFFFF.

Update: "fmt " turned out to be quite a bit larger, there's some extra data there.

"vorb" is 44 bytes, not sure what it is yet. Probably needed to play the file.

"data" seems to be a (raw?) Vorbis stream, you can find the three first Vorbis headers by looking for:

0x01"vorbis" (the identification header)
0x03"vorbis" (the comments header)
0x05"vorbis" (the "codebooks" header)

8 bytes before each header there's a 32-bit int that says how large the header is. The problem I have is that I don't know where each Vorbis audio packet begins and ends.

I've written a small program in C (with very messy code) that extracts the 3 first Vorbis headers and puts them in a proper Ogg file. It's identified as a valid music file but with 0 length as I don't know how to put the Vorbis packets in Ogg pages. You can download it here: [http://dl.getdropbox.com/u/773354/extract.zip](http://dl.getdropbox.com/u/773354/extract.zip)

Updated:

The format turns out to be "audiokinetics wwise", they use their own container for Vorbis etc. I downloaded their SDK but it doesn't seem possible to play the files without the original project. But at least it helps quite a bit...
## Post #2
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-05-13T14:51:54+00:00
- Post Title: WWise RIFF Vorbis format?

I uploaded the program I wrote to extract the ogg but it's very ugly code. It was written on Linux and it's used like: make && ./ro music.riffvorbis and creates "anders.ogg". Needs libogg installed.

[http://dl.getdropbox.com/u/773354/extract.zip](http://dl.getdropbox.com/u/773354/extract.zip)
## Post #3
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-05-13T20:32:03+00:00
- Post Title: WWise RIFF Vorbis format?

(the download links are fixed now)
## Post #4
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-05-13T21:01:31+00:00
- Post Title: WWise RIFF Vorbis format?

Use MEGAUPLOAD.COM, NETLOAD.IN, 4SHARED.COM.
They don't make any problems and are very frendly for nonpaying downloading users.
## Post #5
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-05-13T21:10:25+00:00
- Post Title: WWise RIFF Vorbis format?

> Reply from asmxtx
>
> Use MEGAUPLOAD.COM, NETLOAD.IN, 4SHARED.COM.
They don't make any problems and are very frendly for nonpaying downloading users.
[http://dl.getdropbox.com/u/773354/extract.zip](http://dl.getdropbox.com/u/773354/extract.zip) for my C source code (very ugly)

[http://dl.getdropbox.com/u/773354/1.riffvorb](http://dl.getdropbox.com/u/773354/1.riffvorb) for the example file

These work now.
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-06-14T21:06:41+00:00
- Post Title: WWise RIFF Vorbis format?

Thanks for make this unpacker/conversor i tried under Slamd64 and GCC 4.2.3, when i compile i get:

```
vorbis.c:170: warning: format '%d' expects type 'int', but argument 2 has type 'ogg_int64_t'

```

and then if i analyze the ogg

```
Vorbis headers parsed for stream 1, information follows...
Version: 0                                                
Vendor: AO; aoTuV b4b [20051117] (based on Xiph.Org's libVorbis)
Channels: 2                                                     
Rate: 48000                                                     

Nominal bitrate: 48,000000 kb/s
Upper bitrate not set          
Lower bitrate not set          
Negative or zero granulepos (-1) on vorbis stream outside of headers. This file was created by a buggy encoder              
...

```

and

```
        Playback length: 0m:00.000s
        Average bitrate: inf kb/s

```
## Post #7
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-06-14T22:48:09+00:00
- Post Title: WWise RIFF Vorbis format?

> Reply from Savage
>
> Thanks for make this unpacker/conversor i tried under Slamd64 and GCC 4.2.3, when i compile i get:
Code: Select allvorbis.c:110: warning: format '%d' expects type 'int', but argument 2 has type 'size_t'
vorbis.c:170: warning: format '%d' expects type 'int', but argument 2 has type 'ogg_int64_t'

and then if i analyze the ogg
Code: Select allNew logical stream (#1, serial: deadbeef): type vorbis
Vorbis headers parsed for stream 1, information follows...
Version: 0                                                
Vendor: AO; aoTuV b4b [20051117] (based on Xiph.Org's libVorbis)
Channels: 2                                                     
Rate: 48000                                                     

Nominal bitrate: 48,000000 kb/s
Upper bitrate not set          
Lower bitrate not set          
Negative or zero granulepos (-1) on vorbis stream outside of headers. This file was created by a buggy encoder              
...

and
Code: Select allTotal data length: 103036 bytes
        Playback length: 0m:00.000s
        Average bitrate: inf kb/s
Yeah, it's broken. I don't know the audio packet boundaries so all the generated .ogg has is the 3 first headers.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-06-15T20:16:06+00:00
- Post Title: WWise RIFF Vorbis format?

Maybe here we get some clues
[http://www.hydrogenaudio.org/forums/ind ... opic=69941](http://www.hydrogenaudio.org/forums/index.php?showtopic=69941) 

PS: lol, 4 years here
## Post #9
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-06-16T00:08:13+00:00
- Post Title: WWise RIFF Vorbis format?

> Reply from Savage
>
> Maybe here we get some clues
http://www.hydrogenaudio.org/forums/ind ... opic=69941 

PS: lol, 4 years here
I will look into all this again and post everything I know so far. Haven't really touched this in a while now...
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-26T21:37:17+00:00
- Post Title: WWise RIFF Vorbis format?

Savage, thank you for sticking with all of us for 4 years
## Post #11
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-07-08T04:25:10+00:00
- Post Title: WWise RIFF Vorbis format?

I have "figured" the format out enough to convert the files to playable Ogg Vorbis. You can find the converter here:

[http://andersman.org/~anders/wwiseconv.py](http://andersman.org/~anders/wwiseconv.py)

It requires Python 2.5+ and mutagen.

This should work for other games using WWise as well, but I don't have any. Also, when I tried the latest WWise SDK and encoded some Vorbis stuff it seems they changed the format...
## Post #12
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-09-12T20:58:26+00:00
- Post Title: WWise RIFF Vorbis format?

```
import os
import sys
import struct
from uuid import UUID

input_file = '/Applications/EVE Online.app/Contents/Resources/transgaming/c_drive/Program Files/CCP/EVE/res/Audio/128526931.ogg'

def parse(stream):
    save = {}

    magic, file_size, file_type = struct.unpack('<4sL4s', stream.read(12))
    print "magic: %s file_size: %d file_type: %s" % (magic, file_size, file_type)

    while stream.tell() <= file_size:
        chunk, size = struct.unpack('<4sL', stream.read(8))
        print "  chunk: '%s' size: %d" % (chunk, size)

        if chunk == 'fmt ':
            (format, channels, samples_per_sec, avg_bytes_per_sec, blockalign,
            bits_per_sample, size, valid_bits, channel_mask, guid) = struct.unpack('<HHLLHHHHL16s', stream.read(size))

            uuid = UUID(bytes=guid)

            print "    format: %02x; channels: %d; rate: %d; avgbytes: %d" % (format, channels, samples_per_sec, avg_bytes_per_sec)
            print "    bits_per_sample: %d size: %d valid_bits: %d channel_mask: %d" % (bits_per_sample, size, valid_bits, channel_mask)
            print "    guid: {%s}" % str(uuid)

            save['rate'] = samples_per_sec

        elif chunk == 'vorb':
            data = stream.read(size)
            samples, a, b, c, d, audio_size, f, g, h, i, j = struct.unpack('<LLLLLLLLLLL', data)
            save['audio_size'] = audio_size
            song_len = samples // save['rate']
            print "    samples: %d audio_size: %d" % (samples, audio_size)
            print "    samples / %d = %0.2f secs" % (save['rate'], song_len)

        elif chunk == 'data':
            orig_pos = stream.tell()

            ident_size, unknown1 = struct.unpack('<LL', stream.read(8))
            ident = stream.read(ident_size)

            comments_size, unknown2 = struct.unpack('<LL', stream.read(8))
            comments = stream.read(comments_size)

            codebooks_size, unknown3 = struct.unpack('<LL', stream.read(8))
            codebooks = stream.read(codebooks_size)

            print "    chunk_size - audio_size = %d" % (size - save['audio_size'])

            print "    ident_size: %d comments_size: %d codebooks_size: %d" % (ident_size, comments_size, codebooks_size)
            print "    unknown1: %d unknown2: %d unknown3: %d" % (unknown1, unknown2, unknown3)

            packets = 0

            while stream.tell() < size + orig_pos:
                packet_size, granule = struct.unpack('<LL', stream.read(8))

                # need to figure out these
                if granule == 0:
                    print "        [%d] granule = %d; size = %d" % (packets, granule, packet_size)
                    print "            %s" % repr(stream.read(packet_size))
                else:
                    stream.seek(packet_size, os.SEEK_CUR)
                packets = packets + 1

            print "    found %d vorbis packets" % packets

            extra = stream.read(size - save['audio_size'])
            print len(extra)

        else:
            print "    skipping chunk"
            stream.seek(size, os.SEEK_CUR)

        print ""

if len(sys.argv) == 2:
    input_file = sys.argv[1]

print "== %s ===========" % input_file
f = open(input_file, 'rb')
parse(f)
```


Run this on an EVE .ogg file. I'm trying to figure out the format. You can find my initial documentation at: [http://bitbucket.org/anders/wwiseconv/wiki/WWise_format](http://bitbucket.org/anders/wwiseconv/wiki/WWise_format)

I need to figure out the fields in "vorb" and the 2 initial packets in the "data" chunk (after the 3 vorbis headers).
## Post #13
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-04T09:01:06+00:00
- Post Title: WWise RIFF Vorbis format?

Apparently Assassin's Creed 2 uses a later version of this format.  I made a converter that converts that to normal Ogg Vorbis.  The biggest oddity is that codebooks are stored external to the file.  Other than that, maybe you're dealing with the same kind of corner-cutting (leaving out reserved or unneeded fields) that I did, it might be helpful for reference.  I doubt it's 100% correct yet, but it pretty much works.
[http://hcs64.com/files/ww2ogg00.zip](http://hcs64.com/files/ww2ogg00.zip)
## Post #14
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-04T09:18:41+00:00
- Post Title: WWise RIFF Vorbis format?

> Reply from hcs
>
> Apparently Assassin's Creed 2 uses a later version of this format.  I made a converter that converts that to normal Ogg Vorbis.  The biggest oddity is that codebooks are stored external to the file.  Other than that, maybe you're dealing with the same kind of corner-cutting (leaving out reserved or unneeded fields) that I did, it might be helpful for reference.  I doubt it's 100% correct yet, but it pretty much works.
http://hcs64.com/files/ww2ogg00.zip
I'll have a look, but I downloaded the Wwise SDK and the codebooks are stored within the .ogg files. There is only one difference: in the Vorbis specification there is a set of "time books" (?) and these are simply not included in the Wwise Vorbis files, so you have to parse the whole codebooks then rewrite them but with the times also. That's only 6 bits or so.

Codebooks are different for every encoder and also encoded file, usually, so that you could just embed some other codebooks is quite interesting...

Reading the code at the moment and just saw that you figured out the vorb header!!! Great! I then can fix my new converter (at [http://bitbucket.org/anders/wwiseconv](http://bitbucket.org/anders/wwiseconv)) which currently only works for some files, because I reverse engineered the Wwise SDK and put a breakpoint on vorbis_info_init which gets blocksize0 and blocksize1 passed to it!

Stay tuned 

PS: I see you parsed the codebooks yourself, perhaps you've noticed I was a bit lazy: I just copied libvorbis and added a "dst" oggpack_buffer to every read function.. so they copy everything, and when they get to the time stuff it just writes that.
## Post #15
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-04T10:41:56+00:00
- Post Title: WWise RIFF Vorbis format?

I just committed some new changes to my repository, still doesn't work for some files (blocksize_0_pow / blocksize_1_pow seems to be 8 / 11 for these files).

I know the code is really ugly, sorry for that :\
## Post #16
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-04T14:58:48+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Well the reason I had to mess with the codebooks is because they cut out a lot more than just the time domain transform stuff.
updated version [http://hcs64.com/files/ww2ogg01.zip](http://hcs64.com/files/ww2ogg01.zip) fixes a few things (as listed in hist.txt)
## Post #17
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-04T17:12:22+00:00
- Post Title: Re: WWise RIFF Vorbis format?

In EVE they don't seem to use any loops, so that's nothing I've been able to try.

Can you explain what they seem to have removed from the codebooks? ATM there are a few files that convert, but don't make any sense when they're played. I've uploaded an example here: [http://dl.dropbox.com/u/773354/15849750.ogg](http://dl.dropbox.com/u/773354/15849750.ogg)

vorbose -w does not complain about it, so it really puzzles me...

EDIT: Can you also shed some light on what you mean by the codebooks being stored separately? With the Wwise SDK at least, they are in the same files. I have the latest one released. But I haven't decoded the BNK files yet... someone emailed me about them, and he managed to figure out an older version.
## Post #18
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-04T17:24:12+00:00
- Post Title: Re: WWise RIFF Vorbis format?

As I was examining the decoder I was following along with the Tremor lowmem branch and making the changes there.  It isn't meant to be buildable, but the diff should show clearly enough how I understand the changes: [http://hcs64.com/files/Wwise_tremor.diff](http://hcs64.com/files/Wwise_tremor.diff)

Not sure if I made every change there.
## Post #19
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-04T17:39:01+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from hcs
>
> As I was examining the decoder I was following along with the Tremor lowmem branch and making the changes there.  It isn't meant to be buildable, but the diff should show clearly enough how I understand the changes: http://hcs64.com/files/Wwise_tremor.diff

Not sure if I made every change there.
Weird thing is, you comment things out such as reading the "BCV" header... these exist at least in the version of Wwise that EVE uses. I'm not sure which SDK that is though..
## Post #20
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-15T16:37:14+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from hcs
>
> Well the reason I had to mess with the codebooks is because they cut out a lot more than just the time domain transform stuff.
updated version http://hcs64.com/files/ww2ogg01.zip fixes a few things (as listed in hist.txt)
I found this on their page:

> Codebooks have been removed from the Vorbis file headers and moved to a decoder library resulting in less runtime memory usage, less space taken on DVD, and smaller prefetch loaded in RAM.

I'm guessing either A) EVE doesn't use 2009.03 SDK B) it's not used for the EVE files somehow, might be a setting

Can you please upload a song from the game so I can have a look and compare to the files I've got here. It works 100% for EVE now.
## Post #21
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-17T00:02:08+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Here's the files I worked with:
[http://hcs64.com/files/ac2files/](http://hcs64.com/files/ac2files/)
unconvfile.rar was those that didn't convert after I'd added support for the other two.

(Newer version of ww2ogg (0.3) since a while, btw)
## Post #22
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-17T02:11:20+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from hcs
>
> Here's the files I worked with:
http://hcs64.com/files/ac2files/
unconvfile.rar was those that didn't convert after I'd added support for the other two.

(Newer version of ww2ogg (0.3) since a while, btw)
OK, thanks. Seems "RIFX" is something different from the files I've seen in EVE and generated by the Wwise SDK. Might be some kind of optimized format (like the change log entry I pasted in my previous post)

output from my program:

magic is not RIFF
Info: 512 channels, 8192000 rate, -1926299648 bps
Info: -105677824 samples
Error: could not submit ident header

obviously screwed up =)

Edit: AHH! RIFX is big-endian. I see. Well, I suppose it's time for me to fix that in my code
## Post #23
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-17T02:55:54+00:00
- Post Title: Re: WWise RIFF Vorbis format?

RIFX is just RIFF with all multibyte values big endian.  In Wwise this includes the headers for the Vorbis frames.
## Post #24
- Username: Klimt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 24, 2009 3:15 pm
- Post datetime: 2009-12-24T08:04:58+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Anders,

Thanks for writing this tool - I look forward to trying it out on my EVE OGG files.  What do you suggest compiling this with?  On Windows I have Visual Studio .NET 2005 - will that work?  Or in Linux, would I use gcc?  Have you considered providing a ready-to-use Win32 executable?

Best regards,

Klimt
## Post #25
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-25T08:03:36+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from Klimt
>
> Anders,

Thanks for writing this tool - I look forward to trying it out on my EVE OGG files.  What do you suggest compiling this with?  On Windows I have Visual Studio .NET 2005 - will that work?  Or in Linux, would I use gcc?  Have you considered providing a ready-to-use Win32 executable?

Best regards,

Klimt
There is a Makefile for Linux in the repository, same for Windows but it requires that you install mingw. I can't imagine it would be a lot of work to make it compile in Visual Studio, but you'll have to find a compiled libogg for VS.
## Post #26
- Username: Klimt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 24, 2009 3:15 pm
- Post datetime: 2009-12-27T04:09:07+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Great tool!  I was able to get it working in Linux very easily (quicker to install Ubuntu and libogg-dev on a spare PC rather than futz around with Visual Studio).

In case someone else runs across this thread, I've pieced together the listing for the post-Ambient061 (Forgotten Places) Oggs.  Previous Oggs can be had from earlier versions of the EVE client that did not use WWise.

EVE Dominion 6.20.120813 (1.0.3):

```
Ambient061 1059862145	Forgotten Places
Ambient062 240482530	 Precious Ore
Ambient063 217101372	 It Ends Here
Ambient064 810669328	 Shifting the Balance of Power
Ambient065 920880696	 Where Evil Lurks
Ambient066 33618264	  Point of No Return
Ambient067 1009835561	Theme from Jita
Ambient068 289182861	 New Moon
Ambient069 52606086	  Seek and You Shall Find
Ambient070 45159949	  Learning from the Past
Ambient071 798101877	 Close to a Holy Place
```
## Post #27
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2009-12-27T11:45:42+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from Klimt
>
> Great tool!  I was able to get it working in Linux very easily (quicker to install Ubuntu and libogg-dev on a spare PC rather than futz around with Visual Studio).

In case someone else runs across this thread, I've pieced together the listing for the post-Ambient061 (Forgotten Places) Oggs.  Previous Oggs can be had from earlier versions of the EVE client that did not use WWise.

EVE Dominion 6.20.120813 (1.0.3):
Code: Select alltrack      fileID	 	title
Ambient061 1059862145	Forgotten Places
Ambient062 240482530	 Precious Ore
Ambient063 217101372	 It Ends Here
Ambient064 810669328	 Shifting the Balance of Power
Ambient065 920880696	 Where Evil Lurks
Ambient066 33618264	  Point of No Return
Ambient067 1009835561	Theme from Jita
Ambient068 289182861	 New Moon
Ambient069 52606086	  Seek and You Shall Find
Ambient070 45159949	  Learning from the Past
Ambient071 798101877	 Close to a Holy Place
You can find these in resPlaylists.stuff or something, it's in a .yaml file. My old Python based tool read that file and fixed the filenames, shouldn't be too hard to do again.
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-12T23:28:51+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Can we get a compiled exe version of your lates tool anders?
## Post #29
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2010-01-16T15:14:52+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from OrangeC
>
> Can we get a compiled exe version of your lates tool anders?
[http://dl.dropbox.com/u/773354/releases ... -win32.zip](http://dl.dropbox.com/u/773354/releases/wwconv-20091215-win32.zip)
## Post #30
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-17T06:52:38+00:00
- Post Title: Re: WWise RIFF Vorbis format?

I finally got around to downloading EVE Online to test, it seems that it uses the same format as The Sabotuer, which I added support for yesterday.  All convert with ww2ogg 0.8 using --full-setup.
## Post #31
- Username: Anders Bergh
- Rank: n00b
- Number of posts: 18
- Joined date: Wed May 13, 2009 6:28 am
- Post datetime: 2010-01-17T12:57:37+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from hcs
>
> I finally got around to downloading EVE Online to test, it seems that it uses the same format as The Sabotuer, which I added support for yesterday.  All convert with ww2ogg 0.8 using --full-setup.
Really nice, I just hope they don't change the format again.

Could you take a look at the .BNK files in EVE?
## Post #32
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-17T15:13:56+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Easiest thing to do right now is to just pull out the RIFF sections from the .bnk.  The rest of the file (in some cases the whole file) is metadata that apparently isn't super-important.  Don't think I'll go into actually parsing it just now.
## Post #33
- Username: sel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 19, 2010 6:04 am
- Post datetime: 2010-01-19T06:58:44+00:00
- Post Title: Re: WWise RIFF Vorbis format?

The BNK container format has already been analyzed by some russian guys.

[http://ipb.extractor.ru/index.php?showtopic=1976](http://ipb.extractor.ru/index.php?showtopic=1976)

I can't read russian, but the Google-translation is good enough. There is a description of the format as well as an extraction program called "bnkextr" which extracts one or multiple wav-files from the BNK-container. The program comes with Delphi/Pascal source, it should be easy to create a C-Version.

I want to thank Anders for the ww2ogg program, which - together with bnkextr - made me able to listen to the "Divinity 2: Ego Draconis" soundtracks.
## Post #34
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-01-25T12:23:08+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@hcs, what is with the inconsistancies between original file size and the resulting ogg since both hold vorbis data? (using ww2ogg08 and previous versions)

for example original vorbis wav was 1.21mb and resulting ogg comes out as 415kb, is there that much unrelevant junk data in wwise or potentially vorbis data dismissed?

just wondering as to my understanding wwise was trimmed down in stuff so ogg should be larger not smaller.
## Post #35
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-25T16:50:34+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@apollo you right some ogg vorbis riffx have metada inside.
It' s possible to make a parser/spliter to separate the data from the audio and then a joiner?
## Post #36
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-27T00:05:16+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@apollo, you're right, the resulting .ogg should only be bigger than the original wwise file.  There is only a little data that is thrown away, namely the seek table, and it shouldn't be nearly that big.  You might want to check the original file for another RIFF or RIFX further down, there might be more than one file in there, and ww2ogg will only use the one at the start of the file.  If that isn't the case, could you upload the file for me?  My converter may be missing something and I'd like to figure out what it is.

@Savage, I don't understand what you're saying.  Is there something large that I'm getting rid of?
## Post #37
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-01-27T08:51:11+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@hcs, Well, looks like there is multiple riff vorbis files in same file after all, which i did not realise to check for when file began with riff header instead of any archive container stuff so my mistake.   

any chance of adding a check routine to process file for additional files by looking additional riff headers? (if not default, add a command line command?) this seems be similar case on Watchmen where oggsrain did not always notice the multiple vorbis streams and just took the first one i believe.
## Post #38
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-27T12:15:40+00:00
- Post Title: Re: WWise RIFF Vorbis format?

It's possible.  ww2ogg actually used to complain if the RIFF wasn't exactly equal to the total file size, now it allows for stuff at the end because it turned out that many files were padded.  I could add fsbii-like functionality to look for more RIFFs, we'll see if I get the chance.  If you can upload an example I'll be much more motivated :)
## Post #39
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-27T18:53:45+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Would be great if it can look into bnk archives also, just a suggestion?
## Post #40
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-03-06T08:18:56+00:00
- Post Title: Re: WWise RIFF Vorbis format?

First off, forgive my ignorance or just having selective blindness. But with the all the tools I've gone through for these wwise sfx files have left me completely dumbfounded. I've gotten out the major batches of vocals but looking to get into some of the actual Foley's and such. So I've batched up a few, of what I think might be the sfx archive/compressed files that hold the audio. It reminds me of the rfmodsound from batman/bioshock... but through all the tools, nothing seems to work. 


Also, sorry if this does not belong in this thread, thought it would make more sense to post in here.
[wisesfx.zip](https://xentaxbackup.github.io/file/2842_wisesfx.zip)
## Post #41
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-03-06T19:25:24+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Looks like extracted with gildor's tool from an upk anyhow I don't think these files contain any audio, just control files and what not for engine, hint, try looking for bigger files in the folder/subfolders.
## Post #42
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-03-06T22:58:36+00:00
- Post Title: Re: WWise RIFF Vorbis format?

That is in fact what I used for the .pcc's. I haven't found anything else of bigger size. But I'll go through them all today just in case. Thanks for takin a look at em.
## Post #43
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-03-08T07:56:02+00:00
- Post Title: Re: WWise RIFF Vorbis format?

NP, what you should be looking for is *.wwisebank files given pcc (me2 i believe), everything else is meaningless junk for you, once found such file, take hex editor and remove all start junk until RIFF and save as own wav and feed it to hcs's ima rejigger and also would help have xbox adpcm codec installed for playback.

Just additional note that wwisebanks can contain multiple riff files.
## Post #44
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-03-08T11:28:35+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from Apollo
>
> NP, what you should be looking for is *.wwisebank files given pcc (me2 i believe), everything else is meaningless junk for you, once found such file, take hex editor and remove all start junk until RIFF and save as own wav and feed it to hcs's ima rejigger and also would help have xbox adpcm codec installed for playback.

Just additional note that wwisebanks can contain multiple riff files.

Okay, ignorance again here. I know that these contain a few and I am sure I will get lost in that area as well, but right now, where would I cut the hex out at? I'm not familiar with code and can only assume to take you literally and cut it right at the 'R' for  RIFF but, saving it, Changing it to .wav and using HCS tool does not convert/extract it... Any help?  

Screenshot @ [http://i41.photobucket.com/albums/e283/ ... iffhex.jpg](http://i41.photobucket.com/albums/e283/geevious/riffhex.jpg)
## Post #45
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-03-08T12:07:32+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Well, i deleted the 764 bytes from the start (your example file pic) so file begins with RIFF and end the file before next RIFF mention, renamed extension to wav, run ima_rejigger file.wav and hex edit 69 to 11 for ima adpcm, used vlc player to playback or encode to other format.

hcs tool only edits the wav you feed it directly, it does not give you a pcm wav. Admittedly this isn't very convenient process to do with converting to other format as header remains somewhat incompatible for most media players/converters and hcs tool does not edit the header.

hcs tool won't do the fix to the file if it doesnt start by RIFF or file cuts out at end too soon before the defined header lenght.
## Post #46
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2010-03-21T21:57:22+00:00
- Post Title: Re: WWise RIFF Vorbis format?

The contents of this post was deleted because of possible forum rules violation.
## Post #47
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-03-21T23:17:12+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Thank you very much for making my life easier. This did the trick for the sound banks!
## Post #48
- Username: JakeARoonie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 23, 2010 11:22 am
- Post datetime: 2010-03-23T11:38:28+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Hey all, forgive the noobishness, I ran across this while searching for something that could not only extract audio files from EVE Online, but put them back in too. Does such a tool exist? I'd like to extract the ship computer's voice files ("Docking permission requested...") and replace them with EDI and Joker in Mass Effect ("This is SSV Normandy requesting vector and a berth..."). Anyway, does a tool exist that could do that? And do we know which file the voices are in? Gotta be one of the BNKs or one of the OGGs, just not sure which. So far in this thread it looks like everyone's just interested in extracting music...
## Post #49
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-25T16:21:21+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Hello guys here i have some WWise BNKS from the army of two DLC, they don't decode with WWi2ogg. I use full setup and inline codebooks, but nothing.



After extracting the wavs of course 


[http://www.mediafire.com/?znunmgymweb](http://www.mediafire.com/?znunmgymweb)

EDIT: nvm figured it out.
## Post #50
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2010-03-27T06:40:05+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@ DerPlaya

I dld your me2 Audio Tool, updated .net framework and tried it out on the MASS EFFECT files, although they are not in a game directory (I got them through a friend back up on a dvd). Anyway, nothing happens.

What am I doing wrong? Can you do a step by step approach to ripping the .afc files? i'm not a complete n00b....
## Post #51
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2010-03-27T06:41:26+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@ DerPlaya

I dld your me2 Audio Tool, updated .net framework and tried it out on the MASS EFFECT 2 files, although they are not in a game directory (I got them through a friend backed up on a dvd). Anyway, nothing happens.

What am I doing wrong? Can you do a step by step approach to ripping the .afc files? i'm not a complete n00b....
## Post #52
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2010-03-28T13:54:26+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@ Bioscope

any chance your're using Vista or 7... I only test this on xp, Vista and later block certain things when not running as admin (UAC)
...if there's no error message i can't tell you what the problem is...

edit: the tool doesn't work DIRECTLY on afc files... you need the pcc files too
afc files are like tfc files for textures, afc = audio file cache, tfc = texture file cache.
they contain no header or directory information. the sounds are referenced in the *.pcc (unreal package) by offset, size and name
## Post #53
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2010-03-29T04:15:26+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@ DerPlaya

ok, I see the problem

Thanks!
## Post #54
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2010-12-04T22:55:14+00:00
- Post Title: Re: WWise RIFF Vorbis format?

The contents of this post was deleted because of possible forum rules violation.
## Post #55
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-12-04T23:12:52+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Try with batch file:
for %%a in (*.RIFX) do ww2ogg.exe "%%a"
packed_codebooks.bin, ww2ogg.exe, *.RIFX, run.bat must be in same dir
## Post #56
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2010-12-05T00:14:33+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from mauzerX
>
> Try with batch file:
for %%a in (*.RIFX) do ww2ogg.exe "%%a"
packed_codebooks.bin, ww2ogg.exe, *.RIFX, run.bat must be in same dir

Thanks, it works !!!
## Post #57
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2010-12-16T03:35:54+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@JeffT How did you get it working? I can't convert any of the oggs in the game directory.
## Post #58
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-04-30T16:39:17+00:00
- Post Title: Re: WWise RIFF Vorbis format?

I tried to convert some audios from Assassin's  Creed 3 (Pc version) but some files can't be converted to ogg vorbis

> This application has requested the Runtime to terminate it in an unusual way.
>
> Please contact the application's support team for more information.

Here is the example:
[http://www.multiupload.com/36A4V1TP89](http://www.multiupload.com/36A4V1TP89) (90.02 KB)
and 0 waiting time:
[http://glb-b5.cjoint.net/get/55zs00/example1.zip](http://glb-b5.cjoint.net/get/55zs00/example1.zip)
## Post #59
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-08T20:03:02+00:00
- Post Title: Re: WWise RIFF Vorbis format?

I think this file hasn't been extracted properly from whatever archive it was in.  Note that there are RIFF headers throughout the file.
## Post #60
- Username: asciutto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 12, 2012 1:23 am
- Post datetime: 2012-05-11T17:35:51+00:00
- Post Title: Re: WWise RIFF Vorbis format?

I hate to thread necro, but I'm having the toughest time getting this to work.

Using the wwconv-20091215-win32 version I get the error:

```
Debug: unhandled chunk 'Ux\ 'dhlpRIFFb1/4'
```


The command I'm doing is:

```

```

With ww20gg019 I get this error:

```
Parse error: invalid codebook identifier
```


The command I'm doing is:

```
ww2ogg "D:\Program Files (x86)\CCP\EVE\res\audio\4528202.ogg" -o test.ogg --full-setup
```


Thanks for the great tools and for reading!
## Post #61
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-05-12T01:21:38+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Hm, that's odd, that command line seems like it should work for EVE according to my records.  I don't have any of the files around to test with in more detail, if you could post a hexdump of the first 0x100 bytes (which ought to be fine under the new rules, right?) I can take a look.
## Post #62
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2015-03-16T21:49:45+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Hey!

Does anybody know how to convert the audio from the Xbox 360 version of Toy Story Mania!? all the conventional ways I've used to convert WWise audio have failed for this. Its a wem file.... but thats as far as I know about it.

I can post a sample if needed.
## Post #63
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-03-17T07:43:00+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Post the .WEM
## Post #64
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2015-03-17T17:10:40+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from brendan19
>
> Post the .WEM

Here Ya Go! 

[https://mega.co.nz/#!Y1dlDTqB!oWETU-o6U ... Pd88PQet7g](https://mega.co.nz/#!Y1dlDTqB!oWETU-o6U6SP77JOdM-6cwawyZrvhxZ8jPd88PQet7g)
## Post #65
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-03-20T01:32:32+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Its wwise adpcm, not vorbis (ogg). There is no convertor for this format.
## Post #66
- Username: Palo Samo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 23, 2015 3:04 am
- Post datetime: 2015-12-29T00:17:29+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Yes, there is.
[http://forums.lastbullet.net/showthread.php?tid=101](http://forums.lastbullet.net/showthread.php?tid=101)
## Post #67
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-01-16T02:45:50+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from Palo Samo
>
> Yes, there is.
http://forums.lastbullet.net/showthread.php?tid=101

Cool, I'd love to see the source for that, wwise adpcm has been bugging me for years.

(btw new ww2ogg 0.24 that fixes a few issues is out)
## Post #68
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2016-02-23T23:35:12+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from Palo Samo
>
> Yes, there is.
http://forums.lastbullet.net/showthread.php?tid=101

I tried that and it didnt work. Neither did the newest update for ww2ogg :/
## Post #69
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-24T16:34:41+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from jasonpatrick72
>
> Palo Samo wrote:Yes, there is.
http://forums.lastbullet.net/showthread.php?tid=101

I tried that and it didnt work. Neither did the newest update for ww2ogg :/

Because it's Little Endian ADPCM version.
## Post #70
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-02-26T21:37:31+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from daemon1
>
> jasonpatrick72 wrote:Palo Samo wrote:Yes, there is.
http://forums.lastbullet.net/showthread.php?tid=101

I tried that and it didnt work. Neither did the newest update for ww2ogg :/

Because it's Little Endian ADPCM version.
If the format is in Little Endian ADPCM version, then is there any way to convert it?
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-27T06:45:06+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from AnonBaiter
>
> If the format is in Little Endian ADPCM version, then is there any way to convert it?

I think the only way is to write a new tool for this format.
## Post #72
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2016-02-28T17:00:39+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Only for for mono or stereo files , don't work for files with 2+ channels.

[viewtopic.php?p=105829#p105829](http://forum.xentax.com/viewtopic.php?p=105829#p105829)
## Post #73
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-04T21:06:28+00:00
- Post Title: Re: WWise RIFF Vorbis format?

I think Ravioli Game Tools will work just fine. Try it out here: [http://www.scampers.org/steve/sms/other.htm](http://www.scampers.org/steve/sms/other.htm)
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T06:05:47+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from Pepsee
>
> I think Ravioli Game Tools will work just fine.

No. It will NOT work at all.
## Post #75
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-03-05T16:10:05+00:00
- Post Title: Re: WWise RIFF Vorbis format?

> Reply from daemon1
>
> AnonBaiter wrote:If the format is in Little Endian ADPCM version, then is there any way to convert it?

I think the only way is to write a new tool for this format.
Unfortunately I don't know how to program a tool so... yeah, we're definitely stuck here.
## Post #76
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-03-31T10:54:19+00:00
- Post Title: Re: WWise RIFF Vorbis format?

@jasonpatrick72 , I just tested your file out with my new [ima_rejigger5](https://hcs64.com/files/ima_rejigger5.zip) decoder, it seems to work.
## Post #77
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2017-04-02T04:08:04+00:00
- Post Title: Re: WWise RIFF Vorbis format?

Found new variant of wem audio.
ima_rejigger5 report that isn't ADPCM(0x2), ww2ogg reports 'unknown chunk size' or 'expected 0x42 fmt if vorb missing'.
Few samples - [http://dropmefiles.com/2UFBU](http://dropmefiles.com/2UFBU)
## Post #78
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-02T05:50:09+00:00
- Post Title: Re: WWise RIFF Vorbis format?

This is IMA ADPCM. ima_rejigger5 decodes them with no problems.
## Post #79
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2017-04-04T04:39:50+00:00
- Post Title: Re: WWise RIFF Vorbis format?

A few of the files are not IMA (2746867.wem and 554404705.wem), but they are just PCM, any player should be able to play them if you just rename the file .wav.
