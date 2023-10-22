## Post #1
- Username: SAUDX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 03, 2014 11:06 pm
- Post datetime: 2020-06-06T17:26:17+00:00
- Post Title: need to extract This War Of Mine localization file

hello there

I wanted to localize this game but not have idea how to do that.

How can I unpack and pack the the text components (texts and font files) ?

thank you
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-07T17:23:58+00:00
- Post Title: need to extract This War Of Mine localization file

Hello. Did you see those topics?

[viewtopic.php?f=35&t=12286](https://forum.xentax.com/viewtopic.php?f=35&t=12286)
[viewtopic.php?f=10&t=11378](https://forum.xentax.com/viewtopic.php?f=10&t=11378)
[viewtopic.php?t=12383](https://forum.xentax.com/viewtopic.php?t=12383)

Also, in game folder there is something called ModdingInstructions,
you should read that.



screenshot000553.png (5.05 KiB) Viewed 139 times
## Post #3
- Username: SAUDX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 03, 2014 11:06 pm
- Post datetime: 2020-06-10T10:37:56+00:00
- Post Title: need to extract This War Of Mine localization file

> Reply from ikskoks ↑Mon Jun 08, 2020 1:23 am at Mon Jun 08, 2020 1:23 am
>
> 
Hello. Did you see those topics?

viewtopic.php?f=35&t=12286
viewtopic.php?f=10&t=11378
viewtopic.php?t=12383

Also, in game folder there is something called ModdingInstructions,
you should read that.

screenshot000553.png

thanks 

Im really sorry but I'm new here
can you tell me how to run the scripts mentioned in the links you gave to me please? (I installed the programs)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-10T14:27:41+00:00
- Post Title: need to extract This War Of Mine localization file

Ok. No problem. 

1st topic --> those are QuickBMS scripts, you need to download this tool [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
and click exe to select script and files (full documentation here --> [https://aluigi.altervista.org/papers/quickbms.txt](https://aluigi.altervista.org/papers/quickbms.txt) )

3rd topic --> these are scipts for 010 Editor, you can download it here [https://www.sweetscape.com/download/010editor/](https://www.sweetscape.com/download/010editor/)
and open scripts in editor, documentation for scripts and templates is here [https://www.sweetscape.com/010editor/manual/](https://www.sweetscape.com/010editor/manual/)
## Post #5
- Username: SAUDX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 03, 2014 11:06 pm
- Post datetime: 2020-06-11T09:36:14+00:00
- Post Title: need to extract This War Of Mine localization file

> Reply from ikskoks ↑Wed Jun 10, 2020 10:27 pm at Wed Jun 10, 2020 10:27 pm
>
> 
Ok. No problem. 

1st topic --> those are QuickBMS scripts, you need to download this tool https://aluigi.altervista.org/quickbms.htm
and click exe to select script and files (full documentation here --> https://aluigi.altervista.org/papers/quickbms.txt )

3rd topic --> these are scipts for 010 Editor, you can download it here https://www.sweetscape.com/download/010editor/
and open scripts in editor, documentation for scripts and templates is here https://www.sweetscape.com/010editor/manual/

I appreciate it 

But sorry I'm not sure if I missed something or not

couldn't understand what the instruction mentioned here :

> - select the script for the type of archive you want to extract, for
>
>   example zip.bms if it's a zip file.

I copied the script text (from the first topic) and paste it in a .txt file then I ran the .exe (not sure about this step I made)
then selected the .txt as the BMS script
after that I select the .BinFont file (which I wanted to extract)
then chose the save location

then this message showed to me:

```
by Luigi Auriemma
e-mail: me@aluigi.org
web:    aluigi.org
        (Oct 20 2019 - 14:53:23)

                          quickbms.com  Homepage
                            zenhax.com  ZenHAX Forum
                     @zenhax @quickbms  Twitter & Scripts

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select BMS script. type ? for using the content of clipboard like a script
- select input archives/files, type * for the whole folder and subfolders
- select output folder where extracting files
- open input file G:\sr\thiswar\quickbms\_system.ttf.BinFont
- open script G:\sr\thiswar\quickbms\BinFont.txt
- set output folder G:\sr\thiswar\quickbms

  offset   filesize   filename
--------------------------------------

- signature of 4 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: "
#"
  e4 0a f2 23                                       ...#

  expected: "
#"
  e3 0a f2 23                                       ...#

- 0 files found in 0 seconds
  coverage file 0     0%   4          1056670    . offset 00000004

Press ENTER or close the window to quit
```


Were my steps correct ?

Sorry again
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-11T10:04:20+00:00
- Post Title: need to extract This War Of Mine localization file

Yeah, your parameters seems to be ok:

> - open input file G:\sr\thiswar\quickbms\_system.ttf.BinFont
>
> - open script G:\sr\thiswar\quickbms\BinFont.txt
>
> - set output folder G:\sr\thiswar\quickbms

I would change BinFont.txt to BinFont.bms but it is a detail and should work anyway.

As for your error:

> signature of 4 bytes at offset 0x00000000 doesn't match the one
>
>   expected by the script

This script has line like this:

> idstring "\xE3\x0A\xF2\x23"

So it expects to see those values in file and it aborts when they aren't there.
Those are old scripts, so maybe file format changed. Maybe you can ask the author in that topic for update of those scripts.
## Post #7
- Username: SAUDX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 03, 2014 11:06 pm
- Post datetime: 2020-06-11T10:18:06+00:00
- Post Title: need to extract This War Of Mine localization file

> Reply from ikskoks ↑Thu Jun 11, 2020 6:04 pm at Thu Jun 11, 2020 6:04 pm
>
> 

Really thanks for your help 

Ill try to contact with him hope he can update the string

thanks again
