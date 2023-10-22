## Post #1
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-24T01:31:47+00:00
- Post Title: Need help adding .wave header to .82m file

Hi! I need some help with the standard .wave header. I need to add it to a .82m file to play it. I've made made an application for that purpose but the file I get doesn't work. I think I've used a wrong header, here is it:

// .82M FILE
// PCM sound - 8000 Hz - 16 bits - Mono.
//It can be converted to wav adding this estructure before:

typedef struct {
  char signature[4] = {'RIFF'}; 
  unsigned long[4] fileSize;       /* =  36 + .82m file size */

  char cabForm[8] = {'WAVEfmt '}; 
  signed   long[4] longCab = 16; 
  signed   int[2]  tag = 1;
  unsigned int[2]  channels = 1;
  unsigned long[4] freFrames = 8000;  
  unsigned long[4] freBytes = 8000;               
  unsigned int[2]  nBlockAlineation = 1; 
  unsigned int[2]  bitsPerFrame = 16;  
  char cabDat[4] = {'data'};                    /*Always 4 chars */
  unsigned long[4] longDatos;                  /*.82m File Size*/               


  unsigned char datos[longDatos];               /*.82m File*/
}


Possible errors:
-Number of bytes of any part is wrong.
-Heroes 2 changed frequency of frames or any other part. (the file description is based on Heroes I researchs) Any idea how to check this out??
-A part of the standard .wave file header was forgotten.

Please help, my project cannot go further until I get this files to work.
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T08:27:20+00:00
- Post Title: Need help adding .wave header to .82m file

As far as I can see, the block alignment value is wrong. You're working with mono data at 16 bits per sample, so the alignment should be 2 bytes, not 1. The "freBytes" value, which should indicate the average amount of data per second, should also be twice as large: The player has to read 8000 samples per second, each 2 bytes in size, for one channel, resulting in 16000 bytes per second.

The second error is probably not serious, but the first might cause players to fail.

Regarding your other assumptions, the header you have constructed seems to be complete and correct otherwise (that is a space at the end of "fmt ", isn't it?). Whether the frequency is correct or not does not affect the validity or playability of the wave file. If you choose the wrong frequency, the file will just sound funny (i.e. play too fast or too slow). There is no way to extract this information automatically from the wave data if it is not given somewhere, so you'll have to perform some trial and error.
## Post #3
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-24T11:59:02+00:00
- Post Title: Need help adding .wave header to .82m file

Thanks for answering!

I understand what you meant, but a friend of mine told me that he found Heroes II .82m has some differente parameters:

22050Hz / 8-Bit Unsigned / Mono

I tried this out opening a file with cool edit and using that parameters and it just sound fine! When I tried to do this with the other parameters I only heard a noise...   

So, If it's 8 bit I don't have to change alignament, do I?

Now the problem... My program seems to add some spaces sometimes between header parameters, and the file size doesn't match, this is a big problem. I don't know why it's that happening, because I write all parameters one after the other, like this:

WriteFile.Write(FileSignature);
WriteFile.Write(FileSize);
etc, etc

Thanks again for helping.
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T12:22:37+00:00
- Post Title: Need help adding .wave header to .82m file

> Reply from Balder
>
> So, If it's 8 bit I don't have to change alignament, do I?
In that case not, no.

> Reply from Balder
>
> My program seems to add some spaces sometimes between header parameters
That is probably a memory alignment problem -- compilers usually align fields in structures on certain memory boundaries (usually 4 or 8 bytes on today's systems) for performance reasons, thus the unwanted "spaces".

To circumvent this problem, you have at least two possibilities:
- Turning alignment off, either for the whole program (through compiler options; generally not recommended) or only for this particular structure (via syntactical means; I'd prefer this method).
- Writing each field at a time while using a method that you can pass the desired number of bytes to (a bit tedious).

Your options depend on the language you are using ...
## Post #5
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-24T20:37:10+00:00
- Post Title: Need help adding .wave header to .82m file

Sorry, but I wasn't able to turn off memory alignment in visual studio 2005 nor find any C# code for that purpose.

I've tried to do that using also a function to place the writer in the desired offset, but it still wrote extra chars so some parameters overwrote others... 

I've also thougt about doing it with another function which works with arrays, but there's some data which cannot be stored as chars... so that wouldn't work anyway...

If you have any idea please help, friend!

(Sorry for bothering you again, but I started on this just last summer studying some books in my free time)

Thanks anyway!
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T21:37:35+00:00
- Post Title: Need help adding .wave header to .82m file

> Reply from Balder
>
> Sorry, but I wasn't able to turn off memory alignment in visual studio 2005 nor find any C# code for that purpose.
I'm not fluent in C#, but there should be a BinaryWriter class for that purpose. Check the entry for Tuesday, June 6, 2006 on [this page](http://www.gamedev.net/community/forums/mod/journal/journal.asp?jn=323030&cmonth=6&cyear=2006). As far as I can see, this code does something quite similar to yours.

> Reply from Balder
>
> (Sorry for bothering you again, but I started on this just last summer studying some books in my free time)
No problem. "Learning by doing" is the best way to get programming knowledge, so keep your spirit up!
## Post #7
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-25T13:32:19+00:00
- Post Title: Need help adding .wave header to .82m file

Lots of thanks, Deniz!

I attach the application and a .82m file to test it. If anyone needs to convert any HoMM audio files, this can be used. It's a bit rudimentary but it's does what it has to do.

Another thing, even using the function from the code you gave me I had to change all variable strings to arrays, because the writer still added a character before every string it wrote... don't ask me why...    

Now I can continue working on .icn images, or trying to work on it.

Many thanks again. 

P.D: If you have time to try, please give opinion about how do converted files  sound (I don't remember game sounds very well but some of the converted samples sounded... strange for me)

See you friend! 
[82M to WAV Converter by Balder.zip](https://xentaxbackup.github.io/file/1285_82M to WAV Converter by Balder.zip)
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-25T22:30:41+00:00
- Post Title: Need help adding .wave header to .82m file

> Reply from Balder
>
> Lots of thanks, Deniz!
No problem, you're welcome.

> Reply from Balder
>
> Another thing, even using the function from the code you gave me I had to change all variable strings to arrays, because the writer still added a character before every string it wrote
Strange. I can't tell you the reason without taking a look at the source code, but even then I can't guarantee for anything. But maybe an experienced C# programmer is reading this thread ...

> Reply from Balder
>
> I don't remember game sounds very well but some of the converted samples sounded... strange for me
Well, you're right -- some sounds felt "strange" for me as well, but
a) I don't know how they sound in-game, so this might be perfectly normal and
b) the waveforms look normal, so the format is probably correct. The only variable parameter would be the sampling rate, but seeing as the sounds are probably supposed to represent a boar, this seems to be reasonably correct as well.

As long as you don't encounter a significantly distorted or crackling file, you shouldn't worry about it too much; I'd say you chose the correct format.

Anyway, thanks for the work!


By the way: Your next tasks on the way to the perfect converter tool: 
- First, make the program accept the file name via command line, as in

```
tool.exe sound.82m
```

- Next step (a bit more advanced, just if you're feeling ambitious): Make it accept wildcard input and convert every matching file found, so that you can call your program like

```
tool.exe *.82m
```

(Hint: FindFirstFile)

Good luck and keep up the good work!
## Post #9
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-26T00:23:25+00:00
- Post Title: Need help adding .wave header to .82m file

Well, I was not planning to introduce multifile converting for now, because I only need a few files to start playing around the remake (main menu sounds and things like that) but I'll try to add that features (if I can) on a later version, when I need to work with many sounds (a bit tedious to convert one by one)

For now, I'll try to code another little application to handle (also one by one at this stage) .icn images (and with this and the fonts I can start some serious coding on Heroes II remake).

Fortunately, I also have Heroes I .icn specification from.
Unfortunately, I was checking that on Heroes II files and it didn't match (as happened with the files we talked here about).
You can see .icn structure in this topic: [viewtopic.php?t=2711](http://forum.xentax.com/viewtopic.php?t=2711)

Rheini tried to help me, but I just can't understand very well C++ and even if I could I still don't understand how do palettized images work (how to make a converter, then?:D).
I attach a .icn file and, if you have some free time, you can have a look at it, and see if you get any info or maybe if my info it's correct.
Furthermore, if you know how do this kind of images (palettized, 256 colors) work and you can explain me easily, I'll be very pleased.

I'm getting a bit bored of myself always asking for help. Excuse me again but the project seems to be a bit difficult for only one begginer person.
[icn image and palette.zip](https://xentaxbackup.github.io/file/1288_icn image and palette.zip)
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-26T00:38:29+00:00
- Post Title: Need help adding .wave header to .82m file

Well this is a for for audio and would be more convenient to do audio and images separately rather than in one thread. Seems inconvenient to try to change the subject so radically since images and sound are quite different.
## Post #11
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-26T11:09:02+00:00
- Post Title: Need help adding .wave header to .82m file

I know, but I've given url to the other topic for answering there. Sorry if this was inconvenient.
