## Post #1
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-17T20:15:34+00:00
- Post Title: Tinker .dat file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-19T16:14:27+00:00
- Post Title: Tinker .dat file

it's necessary the tinker executable to know the blowfish key used for the filenames
## Post #3
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-19T16:42:05+00:00
- Post Title: Tinker .dat file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-19T19:23:41+00:00
- Post Title: Tinker .dat file

[http://aluigi.org/papers/bms/tinker.bms](http://aluigi.org/papers/bms/tinker.bms)
remember that you need QuickBMS 0.3.11 that I have released just yesterday (what a luck ih ih ih)
## Post #5
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-19T20:00:35+00:00
- Post Title: Tinker .dat file

Thank you so much.
It worked and extracted all the data, but the music is in a file format called xwma.
Now I'll just have to find a converter. (ToWav which works on some Xbox titles (e.g. Lucidity), doesn't work here.)

Edit: I can convert the xwma files to wav files using xwmaencode.exe
But I have to do it manually for each file since I don't know how to write batch files.

Thanks again aluigi.

Edit 2: Just in case there's someone else who is as unexperienced as I am and wants to convert the xwma files to wav files, here's what I did:

1. Make a new text file in the folder where you put the xwma files
2. name it to whateveryoulike.bat
3. right click -> edit
4. insert this:

> xwmaencode.exe -b 48000 track1.xwma track1.wav
>
> xwmaencode.exe -b 48000 track2.xwma track2.wav
>
> xwmaencode.exe -b 48000 track3.xwma track3.wav
>
> xwmaencode.exe -b 48000 track4.xwma track4.wav
>
> xwmaencode.exe -b 48000 track5.xwma track5.wav
>
> xwmaencode.exe -b 48000 track6.xwma track6.wav
>
> xwmaencode.exe -b 48000 menu.xwma menu.wav
>
> xwmaencode.exe -b 48000 robotwin.xwma robotwin.wav

And that's it. After some seconds you should have the wav files.
You can convert other files in the folder to wav files, just copy a line, add it and edit the filename.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-19T20:44:56+00:00
- Post Title: Tinker .dat file

for executing the same command over multiple files exists the comfortable "find" tool which does the job.
it's a command-line tool derived from unix (findutils) and that has been ported also on windows.

you can find some useful info and examples here:
[viewtopic.php?p=29970#p29970](http://forum.xentax.com/viewtopic.php?p=29970#p29970)

so for this exact case the command was:
find c:\your_folder -iname "*.xwma" -exec c:\xwmaencode.exe -b 48000 "{}" "{}".wav ;
or (started from the same folder)
find -iname "*.xwma" -exec xwmaencode.exe -b 48000 "{}" "{}".wav ;
or
find -exec xwmaencode.exe -b 48000 "{}" "{}".wav ;
