## Post #1
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-01-17T13:14:29+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

Modern Warfare 1 & 2

\Call of Duty 4 - Modern Warfare\zone\english
\Modern Warfare 2\zone\english

I guess a file format "ff " in english folder is sound file.
Right?

If it is right, tell me what to unpack the files?
## Post #2
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2010-01-17T14:49:03+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

I dont think so, the most sound are in the iwd files (they are just renamed zip files). ff is for mods, i think they have scripts etc in it.

Cheers evilpie
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-02-27T02:39:35+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

no, the weapon sfx and whatnot are in the ff files and not the iwds, i've "extracted" them before by decompressing the ff file with offzip and importing the decompressed file into audacity with raw import. its hard to find a specific sound, but there's alot of good stuff.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-03-05T12:53:54+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

The .ff are zlib compressed files and contains wav (adpcm) and mp3 audios
You must use offzip and change the audio.
## Post #5
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-03-13T07:10:08+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

> Reply from Pepper
>
> no, the weapon sfx and whatnot are in the ff files and not the iwds, i've "extracted" them before by decompressing the ff file with offzip and importing the decompressed file into audacity with raw import. its hard to find a specific sound, but there's alot of good stuff.

[http://www.totalcmd.net/plugring/gaup.html](http://www.totalcmd.net/plugring/gaup.html)
[http://forrox.narod.ru/readme.htm#howtouse](http://forrox.narod.ru/readme.htm#howtouse)

After *.ff files decompressed to *.iwf in ModernWarFare\zone\english folder like above, what to do?
What is "iwf" files?


Is Iwf format some kind of pack file?
Or sound files? Then tell me what application play it?
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-03-14T02:16:24+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

open audacity, import that file as raw data, you'll get a stream of static mostly, but the static stops for sfx every now and then.  there isnt an easier way, and in cod4 its not adpcm, adpcm was only in cod5 and qos.
## Post #7
- Username: Bluesoju
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 26, 2010 7:25 pm
- Post datetime: 2010-03-26T16:21:07+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

Zlib is not straightforward at all, i have no idea how to use it. Isn't there a gui version for it? I couldn't find it.

Also guap would load the files until i saw the iwd file inside, but then when I would try to exact that out I always got a disk error.
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-03-27T00:08:16+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

search for a tool called offzip, use it with cmd.

oh and guap doesnt get individual sound files out of zlib, it just decompresses. since its not really a structured format (cod4 and 6 arent, waw was a bit more structured, but also used adpcm audio) its basically a stream of compressed data you're turning into a stream of raw data.  so you have to import the "raw" stream into audacity as raw data, and you'll have a hour or so of static (other data) with the ocassional occurance of raw wave data (which sounds perfectly fine). offzip wont get you filenames or detect the files either, because its not zlibbed with that info. the audio does have its filepath before it if you look at its offset in a hex editor, but thats not enough.
## Post #9
- Username: Bluesoju
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 26, 2010 7:25 pm
- Post datetime: 2010-03-27T03:47:56+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

> Reply from Pepper
>
> search for a tool called offzip, use it with cmd.

oh and guap doesnt get individual sound files out of zlib, it just decompresses. since its not really a structured format (cod4 and 6 arent, waw was a bit more structured, but also used adpcm audio) its basically a stream of compressed data you're turning into a stream of raw data.  so you have to import the "raw" stream into audacity as raw data, and you'll have a hour or so of static (other data) with the ocassional occurance of raw wave data (which sounds perfectly fine). offzip wont get you filenames or detect the files either, because its not zlibbed with that info. the audio does have its filepath before it if you look at its offset in a hex editor, but thats not enough.

So in total commander, I go to for example the \zone\english folder in activision directory. I go to a file such as af_caves double click. Then it shows af_caves with a iwf extension. What do I do from there? If I try anything from there, i get a disk read error.

Also i'm looking mostly for multiplayer sounds (that were not found in the main folder), do you know file those would be in?

Thanks for your help
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-03-27T12:29:32+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

i think there's an mp_common.ff or something like that..


one you have the iwf file import it into audacity as raw audio.
## Post #11
- Username: Bluesoju
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 26, 2010 7:25 pm
- Post datetime: 2010-03-27T13:49:06+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

The problem is once I see iwf file, I can't do anything from there. I get a read disk error. I tried to click and drag the file elsewhere hoping I could access it in audition, but always a disk error.

Did you mean common_mp, i dont see a mp_common? I tried to access that, but it just says "error in packed file"
## Post #12
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-03-27T17:40:33+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

thats odd, sounds like the file might be corrupted or something somehow.. ill decompress one and upload for you, i just need to reinstall cod4

edit: in cod6 that file looks encrypted or something, guess they didnt want people editing multiplayer easily.

double edit: the common.ff has the files, im going to post what i did as simple as i can:

using a downloaded tool called offzip ( [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip) ) and the cmd prompt (file-> run -> cmd) i first drag in offzip.exe, then type " -a " (note the space before and after -a, this avoids problems) then drag in the .ff file to the cmd window, then hit space. then type in the path of the folder you want to extract to (C:\tempsound or w/e), then space, then the number "0" without quotes. i then hit enter, and it gives me a .dat file in the specified folder. this is your decompressed files, all in one stream. next, i look in a hex editor and search for ".wav" without quotes.  it may find a few giberish results randomly, or groups of .wav references to files in the iwd zip types, but when you find something like: user_interface/ui_arcade_streak_lost1.wav you know its a file that is followed by a bit of wav data. you can import the file using audacity ( [http://audacity.googlecode.com/files/au ... 1.3.11.exe](http://audacity.googlecode.com/files/audacity-win-unicode-1.3.11.exe) ). in audacity you select import-> rawdata and select the .dat file. you can tweak the settings in four ways to get the sounds: 44khz mono little edian, 44khz mono big edian and stereo of both these (for certain gunshots, stereo is used) (some are big, some are little, so you can do both and where static is in one file, its sound in the other and vice versa) the main thing to note is the big endian sounds tend to have a bit of very low level static, but its not very noticable at all. you can then highlight the sound you want (if doing both the little and big tracks, mute the track with the static) and file-> export -> wav file. you can use the names in the hex editor to name them. and you have your sounds! just note that the files are mostly static (other non audio data) until about half way in, so you should get aquainted with zooming in and out and moving around in audacity.
## Post #13
- Username: Bluesoju
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 26, 2010 7:25 pm
- Post datetime: 2010-03-28T05:17:21+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

I can't for the life of me run offzip. I'm using windows 7 and every time I try to do it, it just opens and closes. So then I tried using it from the "run" prompt (windows + r). Still the same thing, opens and disappears  

Run as admin doesn't work either.

Why can't people make a simple gui for their programs in 2010? I hate command lines. Ahhhhhh it's not like this is the first time I've ran command line programs, but I still hate them and I have no idea how to run this one.

(using it on mw 2 files btw)

EDIT: I finally got it using windows virtual xp running it through ms-dos.

However i'm not sure the commands you gave me were correct. It wasn't working until i typed in:

C:\offzip>C:\offzip\offzip.exe -a C:\offzip\common.ff "C:\offzip" 0

Let's see if I can get it to work now. Thanks for your help.

I did some searching and I saw other people on windows 7 64 bit systems had problems.

EDIT 3:
Do you know of another site that is investigating the findings of the content of these files and where each sound is?
## Post #14
- Username: revolution
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 28, 2010 9:16 pm
- Post datetime: 2010-03-28T17:25:15+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

Ok i tested what pepper said and it works like a charm    so i made a small package with the offzip and instructions how it works and what you exactly need to do. it really simple once you done 1    even a baby can do it   

enjoy! and thanks to Pepper  

*EDIT* only you need to do is to download that Audacity <<< download link in the instructions  

Instructions For MOdern Warfare 2 weapon sounds:
//////////////////////////////////////////////////

The weapons sound of Modern Warfare 2: Are Located in:

C:\Program Files\Steam\steamapps\common\call of duty modern warfare 2\zone\english

and the weapons sounds are in the common.ff and the common_mp.ff
//////////////////////////////////////////////////

Downloads: [http://audacity.googlecode.com/files/au ... 1.3.11.exe](http://audacity.googlecode.com/files/audacity-win-unicode-1.3.11.exe) 

//////////////////////////////////////////////////
Instruction:
//////////////////////////////////////////////////

1. place the files from the rar archive on the C drive or anydrive you want. 

2. Then open cmd: file - run - cmd or win flag (keyboard) + R en typ cmd.

3. then drag offzip.exe to the cmd and hit enter.

4. type: C:\Offzip.exe -a (drag your .ff file here) 

5. Drag your .ff file into the cmd it should look like this: C:\Offzip.exe -a C:\program files etc. etc. etc. common.ff

6. after that type in the path where you want to extract the data. example: C:\sound 0 << 0 required

   now it should look like this: C:\Offzip.exe -a C:\program files\..\..\common.ff C:\sound 0 and hit ENTER 

7. it should extract the file to the sound folder on drive C. in that folder you will find a .dat file

8. open audacity-win-unicode-1.3.11 en go to FILE - IMPORT - RAW DATA and select the .dat file

9. there you have it if you play the file you hear a stream of sounds, weapon sounds etc.

10. That's it Enjoy! can't be easier 
[Mw2 W-Sound Instruction.rar](https://xentaxbackup.github.io/file/2892_Mw2 W-Sound Instruction.rar)
## Post #15
- Username: kwek20
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 11, 2010 1:15 am
- Post datetime: 2010-05-14T14:20:08+00:00
- Post Title: Sound files from [ff] format of Modern Warfare 1 & 2 ?

is it normal thad in de _mp file only a few files are?
## Post #16
- Username: Bluesoju
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 26, 2010 7:25 pm
- Post datetime: 2010-06-21T13:53:00+00:00
- Post Title: Re: Sound files from [ff] format of Modern Warfare 1 & 2 ?

In case you guys were wondering what I did with the sounds, I made this masterpiece:

[http://www.wegame.com/watch/24-modern-warfare-2/](http://www.wegame.com/watch/24-modern-warfare-2/)

Unfortunately fox wouldn't let me upload it to youtube
## Post #17
- Username: anxs220
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 06, 2010 12:38 am
- Post datetime: 2010-07-05T19:08:22+00:00
- Post Title: Re: Sound files from [ff] format of Modern Warfare 1 & 2 ?

hey guys

anyone extracted weapon sounds from modern warfare 2 ?

please give link 

ps tried different things nothing worked...
