## Post #1
- Username: maurid
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 24, 2014 1:19 am
- Post datetime: 2014-09-24T17:43:45+00:00
- Post Title: FIFA 13/14: i need help to extract audio file .sbs or .xma

I'm trying to extract the files contained in fifa 13 or fifa 14 (PC) commentary. For example in fifa 13 I have a single file in .sbs or .xma of 299,212 KB. 
I tried to follow this procedure written by brendan19: 

> Reply from brendan19
>
> You need to adjust the header of the files before ToWAV will convert it from XMA to WAV.

You will need the following:
1. QuickBMS from Aluigi
2. AlphaTwentyThree's XMA Transform Script
3. XMA Parse from HCS

Download QuickBMS/XMA Transform script/XMA Parse and extract them into the same folder.

Run QuickBMS, select the XMA transform script, choose all of the files you wish to convert, choose where you want the XMAs to be placed.

The script will then run and manipulate the files and produce new XMA files that can be decoded with ToWAV.I got this error: 


Can anyone help me please? Or you can suggest another procedure?
Thanks.
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-10-01T12:04:56+00:00
- Post Title: FIFA 13/14: i need help to extract audio file .sbs or .xma

Hi mate,

1. Are you using a batch file for the process?
2. Can you post both code of the XMA tranform script and quickBMS script please? I would like to see something before all.

Cordialy

Vosvoy
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-10-03T19:41:59+00:00
- Post Title: FIFA 13/14: i need help to extract audio file .sbs or .xma

> Reply from maurid
>
> I'm trying to extract the files contained in fifa 13 or fifa 14 (PC) commentary. For example in fifa 13 I have a single file in .sbs or .xma of 299,212 KB. 
I tried to follow this procedure written by brendan19: 
brendan19 wrote:You need to adjust the header of the files before ToWAV will convert it from XMA to WAV.

You will need the following:
1. QuickBMS from Aluigi
2. AlphaTwentyThree's XMA Transform Script
3. XMA Parse from HCS

Download QuickBMS/XMA Transform script/XMA Parse and extract them into the same folder.

Run QuickBMS, select the XMA transform script, choose all of the files you wish to convert, choose where you want the XMAs to be placed.

The script will then run and manipulate the files and produce new XMA files that can be decoded with ToWAV.I got this error: 


It could also be what you think are .xma files aren't actually xma, so there's no way it would ever decode. you could send me a sample you extracted via private message and I'll try my hand at it.

Can anyone help me please? Or you can suggest another procedure?
Thanks.
Typically this means you messed something up in the first step, ripping the files. or you didn't use the xma transform script correctly. I suggest starting over in a sub directory of the C:\ drive named without spaces, I know most batch files take these into account, but you can never be too sure (so you should move all files you are using (exes, bms, bat, and sbs/xma) to something like C:\decodingtemp\

It's a small thing, but I've noticed alot of programs flip out when:

The directory they are called from has spaces in the path or unusual characters, like ~, #, and ! etc. Also you should post the full process log of doing all steps, and the commands you used to do those steps. if you simply ran a .bat file, copy paste the code from inside it (.bat open with notepad like .txt if you right click-> edit) over here so we can see anything you might have slipped up on.
## Post #4
- Username: maurid
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 24, 2014 1:19 am
- Post datetime: 2014-10-05T17:07:20+00:00
- Post Title: FIFA 13/14: i need help to extract audio file .sbs or .xma

No it's a exe file (quickbms.exe). I've changed directory and now i have this error:
