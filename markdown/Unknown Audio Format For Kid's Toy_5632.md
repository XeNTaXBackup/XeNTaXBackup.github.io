## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-12-26T04:59:57+00:00
- Post Title: Unknown Audio Format For Kid's Toy

This is probably a request unlike the normal ones here, because it involves a kid's toy, and not a game, but I am trying to figure out the audio format used on my son's LeapFrog MyPals Scout.  I have figured out how to trick the update software to load files from a server running on my own PC onto the toy, using the proprietary software for the toy, the problem is that I can't quite figure out the audio files.  I know it sounds like a lame thing to try and figure out, but I and a bunch of parents that are posting on their forums want to be able to put our own music and/or audio files onto the toy for our kids.  In fact, they don't have every child's name available, and it is upsetting that some parents can't even get the toy to say their kid's name.  Luckily, my son has the common name of Will, so the toy knows it, but it would be nice to add some custom stuff on there for him, plus it would make other parents very happy to finally get their own child's name on it.  Well anyway, I have uploaded three different audio files in a rar file here:
[http://brienj.home.insightbb.com/audiosamples.rar](http://brienj.home.insightbb.com/audiosamples.rar)

I know that NOM_0132.bin is supposed to say Bryce, but not sure what the other two are, but they are just a kid's name.  If you want to help, you can download even more audio files, using this as a template:
[http://lfccontent.leapfrog.com/myname/a ... M_0001.bin](http://lfccontent.leapfrog.com/myname/audio/en_us/mypals/NOM_0001.bin)

Just replace 0001 with larger numbers, for example, 0002, 0003, 0004, etc.   I only know about NOM_0132.bin being Bryce though.  The other ones could be any kid's name.

I know that almost all LeapFrog products use Linux as the OS, so that should help narrow it down, because I'm sure the audio format should be open-source, and I was thinking it was a headerless .ogg file, but have not had any luck with it yet.  It's pretty ironic that that company uses an Open-Source OS and software for its products, but won't make it easier for people to change the audio on the toy.  In fact, on their forums, they say that the audio is some special format and protected, which I really highly doubt, considering as I said, all their stuff is based on Open-Source things.  They also say it's impossible for anyone to hack, so I take that as a challenge.   

They just want to try and control what people put on the toy, and are probably afraid of people making the toy say something naughty or something stupid like that, when they would just be making a bunch of parents happy if they didn't keep it so closed and hard to change the audio on them.

Well anyway, sorry to ramble on about it, and hopefully someone can help, because I am not the greatest at audio formats, but I know there are others here that are.  Thanks for any help you can give me.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-12-27T04:52:11+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Nothing as complicated as Vorbis, it is some kind of 4-bit ADPCM (possibly DPCM). Unlike most 4-bit formats the low bit is the sign, the upper 3 bits are the magnitude. 0000 seems to be 0 (as it is the most common and shows up in long strings), but 0001 shows up occasionally and -0 doesn't make sense, it appears at about the same frequency as the largest magnitudes, so it might be -8.  I haven't been able to otherwise work out the format, though, it doesn't work as IMA or vox even though it looks very much like IMA once flipped.
Do you think you could get a good recording of the toy saying one of these clips as some kind of guideline?

Here's some ugly python that does even uglier sound:

```
#

from io import open
from sys import argv
from struct import pack
from math import trunc

infile_name = argv[1]
outfile_name = argv[2]
infile = open(infile_name, 'rb')
outfile = open(outfile_name, 'wb')

val_table = (0, -1, 2, -2, 3, -3, 5, -5, 7, -7, 9, -9, 11, -11, 13, -13)

lpc_hist1 = 0
lpc_hist2 = 0
while 1:
    b = infile.read(1)
    if len(b) < 1:
        break
    num = ord(b[0])
    high_nibble = (num >> 4) & 0xF
    low_nibble = num & 0xF

    for nibble in (high_nibble, low_nibble):
        sample = trunc((lpc_hist1 * 4025 + lpc_hist2 * -990)/4096.0) + val_table[nibble]*256

        if sample > 32767:
            sample = 32767
        elif sample < -32768:
            sample = -32768
        lpc_hist2 = lpc_hist1
        lpc_hist1 = sample

        outfile.write(pack("<h",sample))

```
I've been running it like:

```
./leap_lpc.py NOM_0132.bin dump.bin && sox -t raw --encoding signed-integer -b 16 -r 8000 dump.bin dump.wav && audacity dump.wav
```
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-12-27T16:44:41+00:00
- Post Title: Unknown Audio Format For Kid's Toy

hcs, thanks so much for your help, I didn't even think about it being 4bit.  That would make sense though, because of the very small sizes of the files.

To hear the audio of the toy, you can go to the website here:
[http://www.leapfrog.com/toys/scoutad.html](http://www.leapfrog.com/toys/scoutad.html)

And that one particular clip should be "Bryce".  Immediately after you type in that name and click it, it should say, "Bryce".  I could record it with a microphone, but the audio would suck compared to hearing it straight from the website, because it sounds exactly like the real toy.  I will eventually work out more of the names for each numbered audio clip, but for now, having the one known one is good enough to at least get any audio on the toy to test.  I will be putting other numbered audio on the toy and finding out what names they are once I have some more time to do a bunch of them.

Well anyway, if you get any further, please post anything you find, and now that I have a place to start, I may even be able to do it myself, I'm just not the greatest with audio stuff.   

Thanks!
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-12-27T20:33:28+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Hmm, that might be somewhat helpful, the trick is they use MP3 for the Flash thing ([http://lfccontent.leapfrog.com/myname/a ... view/*.mp3](http://lfccontent.leapfrog.com/myname/audio/en-us/preview/*.mp3) , names are in [http://www.leapfrog.com/toys/names.csv](http://www.leapfrog.com/toys/names.csv)), and it probably isn't a good representation of the decoded ADPCM. At least that makes the playback speed clearer, I guess around 10khz.
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-12-27T23:22:42+00:00
- Post Title: Unknown Audio Format For Kid's Toy

> Reply from hcs
>
> Hmm, that might be somewhat helpful, the trick is they use MP3 for the Flash thing (http://lfccontent.leapfrog.com/myname/a ... view/*.mp3 , names are in http://www.leapfrog.com/toys/names.csv), and it probably isn't a good representation of the decoded ADPCM. At least that makes the playback speed clearer, I guess around 10khz.
Ah, good find on the name file.

I can make an actual recording if you want, but saving the audio to any format for you to hear, would sound just like the sounds on that flash application.  It sounds almost identical to the real thing.
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-12-28T17:18:54+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Now I'm finding out that either there are samples on the toy, and these files are actually causing it to play those samples, or else the files are compressed.  For example, you can download some songs:
[http://lfccontent.leapfrog.com/mymusic/ ... nLargo.bin](http://lfccontent.leapfrog.com/mymusic/audio/night/en_us/mypals/BeethovenLargo.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... nlight.bin](http://lfccontent.leapfrog.com/mymusic/audio/night/en_us/mypals/Moonlight.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... winkle.bin](http://lfccontent.leapfrog.com/mymusic/audio/night/en_us/mypals/Twinkle.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... ckABye.bin](http://lfccontent.leapfrog.com/mymusic/audio/night/en_us/mypals/RockABye.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... ullaby.bin](http://lfccontent.leapfrog.com/mymusic/audio/night/en_us/mypals/BrLullaby.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... ls/ABC.bin](http://lfccontent.leapfrog.com/mymusic/day/night/en_us/mypals/ABC.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... eComin.bin](http://lfccontent.leapfrog.com/mymusic/day/night/en_us/mypals/ShellBeComin.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... s/Mary.bin](http://lfccontent.leapfrog.com/mymusic/day/night/en_us/mypals/Mary.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... ouette.bin](http://lfccontent.leapfrog.com/mymusic/day/night/en_us/mypals/Alouette.bin)
[http://lfccontent.leapfrog.com/mymusic/ ... abaloo.bin](http://lfccontent.leapfrog.com/mymusic/day/night/en_us/mypals/babaloo.bin)

And the songs are way longer than the names, of course, yet the file is much smaller in size.  Maybe they could be a type of MIDI file?

Also, I found the downloads and names for some other things(There seems to be extra audio in each, perhaps for the few other things it says with these):
[http://lfccontent.leapfrog.com/mypicks/ ... M_2747.bin](http://lfccontent.leapfrog.com/mypicks/audio/food/en_us/mypals/NOM_2747.bin)
This says "macaroni and cheese"

[http://lfccontent.leapfrog.com/mypicks/ ... M_0988.bin](http://lfccontent.leapfrog.com/mypicks/audio/color/en_us/mypals/NOM_0988.bin)
This says "green"

[http://lfccontent.leapfrog.com/mypicks/ ... M_2830.bin](http://lfccontent.leapfrog.com/mypicks/audio/animal/en_us/mypals/NOM_2830.bin)
This says "dog"

When I get time, I'll get a complete list of foods, animals, and colors.  I can even get the URLs of all of the rest of the songs if you wish.

Alright, thanks hcs for your help so far, and maybe you or someone else, or maybe even me, if I get lucky, can figure it all out, because that would be awesome.
## Post #7
- Username: sniderbr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 21, 2011 2:05 pm
- Post datetime: 2011-01-21T06:10:46+00:00
- Post Title: Unknown Audio Format For Kid's Toy

> Reply from hcs
>
> Here's some ugly python that does even uglier sound:
Code: Select all    for nibble in (high_nibble, low_nibble):

Try this instead:

```

```


...and then use sox as you originally described.  The resulting wave file should sound...different
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-01-21T14:35:28+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Good catch, that does sound significantly better.
## Post #9
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-01-27T08:22:20+00:00
- Post Title: Unknown Audio Format For Kid's Toy

sniderbr and hcs, thanks for the help guys, I will see what I can do with that code.
## Post #10
- Username: beeker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 17, 2011 2:12 pm
- Post datetime: 2011-05-17T06:17:21+00:00
- Post Title: Unknown Audio Format For Kid's Toy

I created an account just so I could respond back to this, as it seems to have not had any response since its inception.

I'm in the boat of... we named our daughter a name that LeapFrog does not know, so I want to fool the leapfrog into thinking a file is correct that I host on a local apache server.

Got that figured out, but now I need to know what to encode the audio file to, as that seems to be the crux of the issue here.

Did anyone figure anything else out?

I even downloaded some better voices (via infovox) for the "say" command utility on my mac that more closely emulate the violet child voice on my daughters toy. So that I can add to the pile of useful things that people could use.

I even downloaded sox, audacity (not sure why I hadn't downloaded that yet anyways), and got the python tool to output a playable audio file within audacity.

Now to go the other way...
## Post #11
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-17T20:07:44+00:00
- Post Title: Unknown Audio Format For Kid's Toy

> Reply from beeker
>
> I created an account just so I could respond back to this, as it seems to have not had any response since its inception.

I'm in the boat of... we named our daughter a name that LeapFrog does not know, so I want to fool the leapfrog into thinking a file is correct that I host on a local apache server.

Got that figured out, but now I need to know what to encode the audio file to, as that seems to be the crux of the issue here.

Did anyone figure anything else out?

I even downloaded some better voices (via infovox) for the "say" command utility on my mac that more closely emulate the violet child voice on my daughters toy. So that I can add to the pile of useful things that people could use.

I even downloaded sox, audacity (not sure why I hadn't downloaded that yet anyways), and got the python tool to output a playable audio file within audacity.

Now to go the other way...
And therein lies the problem ...
## Post #12
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-05-18T03:53:05+00:00
- Post Title: Unknown Audio Format For Kid's Toy

It's not hard to reverse this decoder, the question is whether it will work reasonably in the real decoder.  Here's a pair which decode (leap_lpc.py) and encode (leap_lpc_rev.py) mono 16-bit little endian PCM<->this weird ADPCM.
[http://hcs64.com/files/leap_lpc_00.zip](http://hcs64.com/files/leap_lpc_00.zip)

I'd be interested to hear how it turns out.  I think the sample rate of the source file should be around 10khz.
## Post #13
- Username: mrfunkyland
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 23, 2011 4:15 am
- Post datetime: 2011-07-22T20:24:13+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Hey everyone, I just got one of these and as a composer would love to be able to put lullabies I've written for my son on there. Anyone make any more headway with the file formats? I do suspect that the song files may contain some sort of MIDI-type file as well as audio for the singing that goes with it. That's how I heard it, at least, but I could be mistaken.
## Post #14
- Username: nomel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 29, 2011 1:17 pm
- Post datetime: 2011-07-29T05:35:43+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Regarding the music, the night songs don't seem to have lyrics, but all songs sound like a decent quality midi sound to them. There seems to be a limited instrument selection, with all of the songs I selected using the same flute as the main instrument. Most of the day songs I selected have lyrics, with a few having "inserted name here" type sections. I'm interested to see if these songs with lyrics are larger. 

How did you get access to the song files? I'm getting an xml response with "access denied" when I use my browser. I'll mess around with the python script and see if I can get a custom sound file uploaded to the toy this weekend.

I'm mostly interested in the sound files though...would be great to put on custom midi songs!
## Post #15
- Username: gazzagwire
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 11, 2011 4:58 am
- Post datetime: 2011-08-10T21:04:21+00:00
- Post Title: Unknown Audio Format For Kid's Toy

Hi, did you get anwhere with this project? I'd love to be able to get Violet to say my daughters name.
## Post #16
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-08-11T06:45:58+00:00
- Post Title: Re: Unknown Audio Format For Kid's Toy

You can try the encoder I posted on May 17, but I wouldn't expect much.  I don't know if anyone else has bothered to try it yet.
## Post #17
- Username: monkbroc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 05, 2014 5:08 am
- Post datetime: 2014-10-12T04:41:57+00:00
- Post Title: Re: Unknown Audio Format For Kid's Toy

Hello everybody,

I'm reopening this topic since it was never fully answered and there isn't any info about the file format for this toy anywhere else on the internet other than in this thread. Apparently the toy didn't change since 2011 because all the information here is still spot on.

I've done some progress in decoding the audio format, but I need help from other forum members.

Based on the information by hcs, I did some tests and came up with the following conclusions:

The sampling rate is exactly 10 kHz. I checked this by downloading a file with a periodic waveform to the toy and recording the period of the audio signal produced.

All files I have seen have a 1 byte header with a value of 0x02. They also have a 1 byte footer with a value of 0x10 or 0x11 (don't know the difference).

The audio format is similar to ADX ADPCM (4 bits/sample), but not exactly the same. For example, the low nibble comes before the high nibble has was suggested by sniderbr.

It looks like the encoded signal is the error between the sample and a prediction function.

The raw encoded value can be coverted to an error value by putting it through a look-up table. hcs had guessed that the least-significant bit was the sign and I agree.

To get the values of the look-up table, I ran these signals:

2 2 2 2 2 2 3 3 3 3 3 3 2 2 2 2 2 2 3 3 3 3 3 3 ... (6x 2 followed by 6x 3 repeated a few dozen times)
4 4 4 4 4 4 5 5 5 5 5 5 4 4 4 4 4 4 5 5 5 5 5 5 ... (6x 4 followed by 6x 5 repeated a few dozen times)
... all the way until 14 followed by 15.

The output was a nasty periodic signal (not a square, triangular or sine wave), but the series with the 4s and 5s was twice as loud as the 2s and 3s. The 6s and 7s were 3 times as large as the 2s and 3s, etc. So the conversion from raw value to error signal is linear.

In other tests, both 0 and 1 seem to make no change in the output, which leads me to believe that 1 stands for minus 0 (I'm not sure why that's helpful).

So here's the value table I came up with

```

```

The missing piece is now the prediction function. The one below suggested by hcs based on ADX ADPCM doesn't give good enough results.

```
    {
        double x,y,z,a,b,c;

        x = cutoff;
        y = sample_rate;
        z = cos(2.0*M_PI*x/y);

        a = M_SQRT2-z;
        b = M_SQRT2-1.0;
        c = (a-sqrt((a+b)*(a-b)))/b;

        coef1 = floor(c*8192);
        coef2 = floor(c*c*-4096);
    }

    sample = trunc((previous_sample * coef1 + second_previous_sample * coef2)/4096.0) + val_table[nibble]*256


```


I need help to figure out what the prediction function is.

Here's a simple file I have been working with. I extracted a sequence from a song in the toy that plays a 330 Hz tone, repeated it several times and recorded that. I was playing around in Excel with different prediction functions to see if I could match the recorded file, but I haven't hit on anything good.

[Dropbox folder with the 330 Hz tone files.](https://www.dropbox.com/sh/1gvyevvlk7k161c/AADipKENfSaODLUWGX_yRPJva?dl=0)

Can anybody take a look and help out? I can upload any other files you think will be helpful.

Thanks!
## Post #18
- Username: iva2k
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 07, 2015 5:26 am
- Post datetime: 2015-07-06T22:20:36+00:00
- Post Title: Re: Unknown Audio Format For Kid's Toy

Long time ago I worked at Leapfrog in ASIC group, and I remember that the compression algorithm uses lattice-based linear prediction (implemented in hardware, used in their ASICs from the very first Explorer). It is very efficient for speech compression, and gives very good qualiy for 10x or so of file size reduction. I doubt they changed that, so very possibly they still use it in all speech-related areas of their toys.

Simple googling revealed few sources, e.g. [http://authors.library.caltech.edu/2506 ... SPR003.pdf](http://authors.library.caltech.edu/25063/1/S00086ED1V01Y200712SPR003.pdf)

I hope that helps.
## Post #19
- Username: monkbroc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 05, 2014 5:08 am
- Post datetime: 2015-07-07T11:31:07+00:00
- Post Title: Re: Unknown Audio Format For Kid's Toy

That's very useful thanks. I'll take a look at the book. Thanks!
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-15T12:04:22+00:00
- Post Title: Re: Unknown Audio Format For Kid's Toy

> Reply from brienj
>
> hcs, thanks so much for your help, I didn't even think about it being 4bit.

No wonder. Even the latest games like Dying Light & upcoming Star Wars Battlefront use 4-bit sounds
