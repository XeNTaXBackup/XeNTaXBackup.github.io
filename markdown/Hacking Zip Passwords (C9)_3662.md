## Post #1
- Username: Caboose
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-21T04:18:47+00:00
- Post Title: Hacking Zip Passwords (C9)

Here is a simple to follow guide that involves 0 knowledge of debugging to follow.
You will need the following tools.
1. HXD or a hex editor that can open a program in ram.
2.Cheat Engine or another program that can pause a process.
3.The game C9

Step1

Launch the game update program.


Step2

Launch Cheat Engine


Step3

Setup the hot key to pause the process in cheat engine


Step4.

Set the hot key to your choice (I choose 7)


Step5

Click on the Process list button (magnifying glass) in cheat engine until you see our process (Exlauncher.exe)
do not attach to the process yet.



Step6

This is what it will look like if you attach to the process in cheat engine and pause it.



Step7

Log into C9 and after you are logged in attach to the process and pause it hitting the key you assigned to that and it should look like this.



Step8

Take note of the file name and the progress bar when you see the file finish and the text change pause the process so it looks close to this.



Step9

Now that you have the process paused while it is extracting a file open up HXD and choose open ram



Step10

in the process list you will notice a new process that was created while the game was extracting the files(Launcher.exe)
so this must be what handles extracting the files so lets attach to it.



Step11

Now lets do a search for our file



Step12

We end up here take a look and see if anything looks odd.



Step13

Take note of the long string that looks like it could be a password and it keeps repeats 2x in this view



Step14

if I scroll a little further down it is still repeating this seems like we have our number



Step 15

Try our password on the zip file and it works.
I will post some more advanced tutorials if there is a demand for it let me know

```
66b4427013838ceb5b275d5ba884b0ed9df353e0dc6220955e008d9d
```
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-08-21T06:35:46+00:00
- Post Title: Hacking Zip Passwords (C9)

This could come in handy for some users. Thanks for posting your method!
## Post #3
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-26T12:00:06+00:00
- Post Title: Hacking Zip Passwords (C9)

I have a question ? please
i considered that usually data in RAM kept in fragmented form !
whether when we open the memory that assigned to a process in hex editor , it defragment it and show us in its integrated form ?
very very thanks Master
## Post #4
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2010-03-06T13:27:39+00:00
- Post Title: Hacking Zip Passwords (C9)

Data in ram is normally not fragmented.

For example if you alloc 200 bytes of memory for an password, the whole memory is one block.
But when you again alloc memory it could be directly behind the other block or somewhere totally else, you just dont know.
## Post #5
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2010-04-21T12:33:53+00:00
- Post Title: Hacking Zip Passwords (C9)

There`s a game that also uses a password-protected ZIP, Metal drift. I tried your method and found some repeating text but it doesn`t work as a password! To be honest there wasn`t actually written "game.zip" inside the launcher.exe but I decided to check it out because of its periodicity
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-21T13:42:28+00:00
- Post Title: Hacking Zip Passwords (C9)

because this method is not universal.
for example in Metal Drift Demo the key is 37493752032567301837 and I used the classical method to find it:

```
  0042b6f8 2273 function where is handled the ZipCrypto password [32.le.12&]
- launched the game with ollydbg and set breakpoint at offset 0042B6F0 (that is the starting of the function)
- olly breaks and the password is clearly visible
```

if the game can't be debugged easily you can even place a byte 0xcc at 3 bytes before the offset reported by signsrch, the debugger will popup immediately when the game will crash.

while if the game executable is encrypted you can launch signsrch when the game is running:
signsrch -P MetalDriftDemo.exe
and then attach olly to the process or write a simple writeprocessmemory tool for placing the 0xcc byte in the process

let us know if the key for the full game differs than the onf of the demo.

oh I forgot the link to signsrch:
[http://aluigi.org/mytoolz.htm#signsrch](http://aluigi.org/mytoolz.htm#signsrch)
## Post #7
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2010-04-21T17:24:34+00:00
- Post Title: Hacking Zip Passwords (C9)

Thanks for a quick response, at least one of my problems is solved now. And the key you gave me fits the full version ZIP too.
## Post #8
- Username: Klaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 01, 2008 3:40 pm
- Post datetime: 2010-04-25T09:29:49+00:00
- Post Title: Hacking Zip Passwords (C9)

Can someone help me with another ZIP password protected game? It's called Beat Hazard.

I already found this in hge.dll (beforehand unpacked with UPX):

> 000042ac 2273 function where is handled the ZipCrypto password [32.le.12&]
But no idea what is next.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T09:50:42+00:00
- Post Title: Hacking Zip Passwords (C9)

be sure to have ollydbg installed and that it's set as "Just-in-time debugger":
select "Options->Just-in-time debugging"
click on "Make Ollydbg just-in-time debugger"
open hge.dll with a hex editor (make a backup before)
go at offset 0x42a9
place the byte 0xcc there
save the file and start the game
windows will show an error dialog, press CANCEL
when ollydbg starts watch in the right-down window (aka "stack window")
the password should be one of the first text strings visible in that list
keep us updated if everything worked as expected... and naturally let us know the password :)
## Post #10
- Username: Klaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 01, 2008 3:40 pm
- Post datetime: 2010-04-25T10:52:10+00:00
- Post Title: Hacking Zip Passwords (C9)

So, the password is lippylippy, lol. aluigi, thanks for help!
Packing whole resources back into ZIP also works fine, see the attachment.
[test.jpg](https://xentaxbackup.github.io/file/2971_test.jpg)
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-04-27T21:49:34+00:00
- Post Title: Hacking Zip Passwords (C9)

Excellent everyone!
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-14T11:36:19+00:00
- Post Title: Hacking Zip Passwords (C9)

example of how to get the password of Metal Drift using only signsrch 0.1.6 (yeah a fresh new release) and partially ollydbg (partially because it's set only as JIT debugger so it has only the "display" purpose, you don't need to "touch" it):
[http://aluigi.org/video/zipcrypto_example.avi](http://aluigi.org/video/zipcrypto_example.avi)
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-02-28T21:28:22+00:00
- Post Title: Hacking Zip Passwords (C9)

Hey guys,
What to do in this case:

```
10009f09 2273 function where is handled the ZipCrypto password [32.le.12&]

```

- substracted 3 bytes => 10009F06
- open hge.dll in HxD, Ctrl+G, 10009F06, HxD wrote that file doesn't contains that offset (it ends on 0x4BFFFF)

It's from game Akhra The Treasures and I would like to find password for its data.zip

Thanks in advance
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T11:43:18+00:00
- Post Title: Hacking Zip Passwords (C9)

10009f09 is the memory address assigned to that instruction in hge.dll when it's loaded by Windows.
if you are lucky you should find the relative file offset at 0x9f09 of the file.
otherwise use an rva2file offset tool like my quickrva:
[http://aluigi.org/mytoolz.htm#quickrva](http://aluigi.org/mytoolz.htm#quickrva)
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T12:14:49+00:00
- Post Title: Hacking Zip Passwords (C9)

the password of the data.zip in "Akhra - The Treasures" is 2yKJ6KhRJKJ/18J5
found in less than one minute :)
## Post #16
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-03-01T12:59:56+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Can this method (or similar) be used to find a straight RAR archive file password?
Every "password unlocker/cracker" app out there seems to simply be a virus or malware ITSELF.  

Even if anyone knows of a non-infected app that can do this already would be appreciated.
## Post #17
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-03-01T13:05:27+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from aluigi
>
> the password of the data.zip in "Akhra - The Treasures" is 2yKJ6KhRJKJ/18J5
found in less than one minute

Yeah, I've found it too. Thanks a lot for help and your tools-for-everything
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T13:18:16+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

@SLIFallen
don't confuse the finding of the password located in the memory of the program that opens the archive with cracking an unknown passowrd.
they are 2 completely different things
## Post #19
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-03-05T21:53:31+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Here's another case: game Aztec Tribe has .zip with password called AztecTribe.dat. I've used signsrch for scanning .exe and all of .dll files there, but non of them contains reference to ZipCrypto. Any ideas?
## Post #20
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-06T02:43:34+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

a very handy tutorial indeed
Thanks
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-06T10:36:19+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

@merlinsvk
the executables of the games on bigfishgames are encrypted with armadillo but in this case the problem was hge.dll compressed with upx.
so after having unpacked hge.dll you can scan it with signsrch without problems :)

anyway the password of Aztec Tribe is {0D8FD1A3-DEBF-4ef2-8A91-CDB0A105F6C0}
## Post #22
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-03-06T11:23:53+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from aluigi
>
> @merlinsvk
anyway the password of Aztec Tribe is {0D8FD1A3-DEBF-4ef2-8A91-CDB0A105F6C0}

Oh my God, I was looking at that in HxD, but didn't realize it can be password. I thought it is some key from Windows Registry   



But thanks for pointing to UPX, I forgot that .exe/.dll can be packed
## Post #23
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-07T08:08:57+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

for anyone interested I remember that I maintain a list of games zip password retrieved by myself and I just updated it yesterday after having downloaded various trials from bigfishgames and other websites (I used some keywords to know the games using passworded zips):
[http://aluigi.org/papers.htm#info](http://aluigi.org/papers.htm#info)
## Post #24
- Username: Tantal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 17, 2011 5:38 pm
- Post datetime: 2011-04-17T10:18:31+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Hi, I used all that is written here for this [game](http://tinyurl.com/3rs4n3q), but can not find anything please help me find the password or another way to full of advise if there is.
Thanks all
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T16:23:50+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

the method worked perfectly also in this case but there were 2 problems:
1) the key doesn't contain only alphanumeric chars but also some others, that's why it wasn't quickly visible 
2) these other chars are hard to copy&paste in the normal zip programs when they ask for password so you can't use the password

luckily exist QuickBMS and zip.bms just for avoiding these problems :)

so get both:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
[http://aluigi.org/papers/bms/zip.bms](http://aluigi.org/papers/bms/zip.bms)

and now:

open zip.bms with a text editor (notepad, notepad++ and so on)
delete the line containing:
Code: Select allset ZIP_PASSWORD string ""  # put the password here (only ZipCrypto supported at the moment)
replace it with the following:
Code: Select allset ZIP_PASSWORD binary "\xed\xe0\xf5\x23\x69\x6e\x63\x6c\x75\x64\x65\x20\x63\x6f\x72\x65\x2f\x66\x69\x6c\x74\x65\x72\x53\x74\x72\x65\x61\x6d\x2e\x68\xc1\xcb\xdf"
save the file and use it in quickbms as usual
## Post #26
- Username: Tantal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 17, 2011 5:38 pm
- Post datetime: 2011-04-17T18:00:10+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thank you so much it really helped me soon plan to upgrade the game and can change the password, could you write like myself find this password?

End when i extract some archives i got this error

can i something do with this ?
## Post #27
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T22:10:09+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

the method has been the same described before, the only additional step was selecting the second number in the stack window (right-bottom) and selecting "Follow in dump", so that the password was visible in the dump window (left-bottom).

about that error I have noticed that some files in offices.awa are not password protected and my script was written to decrypt all the files in case ZIP_PASSWORD was set (the reason was simply that usually all the files are encrypted).
I have updated the script so that now only the encrypted files (flag & 1) will use the password.

anyway from the image you pasted I noticed that the file you were trying to unzip is corrupted because the name is clearly wrong.
here I have downloaded the game and that file doesn't exist.
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T22:26:26+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

I have forced the update of the game and I have noticed the problem you talk about like "missioPK" and the other files.
it's just a problem of the zip files that contain some garbage.

the reason why zip.bms doesn't handle them correctly it's because it uses an alternative (simpler) method to read them.
there is no solution at the moment.
## Post #29
- Username: Relict
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 12, 2010 5:49 am
- Post datetime: 2011-04-24T15:03:58+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

The contents of this post was deleted because of possible forum rules violation.
## Post #30
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T13:23:22+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

the password is HappyMuff69
## Post #31
- Username: Relict
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 12, 2010 5:49 am
- Post datetime: 2011-04-25T16:13:13+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thank you aluigi
## Post #32
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-03T16:05:30+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Cool!
## Post #33
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-16T22:03:03+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

If somebody need to unpack "DATA" file in Mini Robot Wars, password is EC?^!98$$%ab17
## Post #34
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-12-02T19:33:08+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

For [Beat Hazard Ultra](http://store.steampowered.com/app/49604) the password is

```
8sF32UfxK97j#@$JЈ$[]soIumMWL;ASOMVPW{QOE<LDSAMKFD
```

and game.dat XOR'ed with 0x35.
## Post #35
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-12-31T21:34:37+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

I'm trying to get the passwords for Heroes in the Sky. Specifically HIS2.res and HIS3.res. They are .zip files with passwords, here's a sample: HIS2.res [http://www.mediafire.com/?w4b3wmarxgu0qkq](http://www.mediafire.com/?w4b3wmarxgu0qkq)
## Post #36
- Username: gutterkid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 22, 2011 3:49 am
- Post datetime: 2012-01-13T20:18:18+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Hello hoping you can help me out here, SWTOR has multiple files that it uses (ie: .bundle;.patchmanifest;.version,etc). These files are all archives. When you open them up with WinRAR or WinZIP you see the files however it shows they are passworded. I have tried every method mentioned here to no prevail. The main "launcher.exe" also has an files in itself. I can find the ZipCrypt function fine and when i set the -3 as shown in the video it does not break. I have also tried with IDA or OllyDBG and cannot find it. I know it has to be right infront of my face.

```
>0041cef6 2273 function where is handled the ZipCrypto password [32.le.12&]

```


I have attached the launcher.exe.
[http://www.mediafire.com/?fubcihi997i43t3](http://www.mediafire.com/?fubcihi997i43t3)


Any help would be appreciated or atleast pointed in the right direction if i am looking at this right or wrong.

Thank you kindly!
## Post #37
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-14T21:52:13+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

it's simple, open launcher.exe with ollydbg, put a breakpoint at address 0041cef3 and wait when it breaks.
maybe try to post also one of these zip files.

*update*
just for my fun I tried to convert my zip.bms in a zip passwords scanner using all the strings available in launcher.exe but it found nothing useful.
## Post #38
- Username: gutterkid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 22, 2011 3:49 am
- Post datetime: 2012-01-15T04:48:50+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Hmm. 

Here is patcher.version file

[http://www.mediafire.com/?6ssjw6b4k3pwri5](http://www.mediafire.com/?6ssjw6b4k3pwri5)

and when i load up ollydbg i cannot find that offset to set a breakpoint? (yeah i'm a noob  )

Here is a picture of what i see in olly.
[http://www.mediafire.com/imageview.php? ... wch1qg9bu5](http://www.mediafire.com/imageview.php?quickkey=uin9nwch1qg9bu5)


Thank you in advance for your help and paitence!
## Post #39
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-16T10:11:52+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

the zip password for Heroes in the Sky is:
9aa0c9335fc08bb6
## Post #40
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2012-01-19T15:32:34+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from aluigi
>
> the zip password for Heroes in the Sky is:
9aa0c9335fc08bb6
 Thank you for that!
## Post #41
- Username: smallxiong
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 16, 2012 12:53 am
- Post datetime: 2012-04-17T19:49:34+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

i got more knowledge ..thx
## Post #42
- Username: warr11r
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 07, 2011 8:30 am
- Post datetime: 2012-06-30T20:26:31+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

For game Fruit Ninja HD password is 
```
f83j#j;.!nZ+94(mB523+=+*vaeuq4TyU2bxoe,bcuy%zXz3719#YDWb531&^724h3#12b34
```
## Post #43
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-13T14:55:40+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Mahjong. World Contest

```
Password
```


```
h7-eRT099-456odper34juv9

XML/levels
werOIR92Jd993ofI94m-10Kdke91359k

data/audio
guiit045-lfiivmm4555lLRJFofmdlLSDFk934

data/tiles
DHi7490&nfjJF&#(jdj895BNF040fmmFOO__

data/trophies
fuut**499mfj28883jDOofnmiIFI-++0-4__ekk300fm41293878450JDFFShjwe

data/fonts
dfgdfgkKKRNEWOR728347)!@)(#jjidoasiueKLQWEKU*(!@#

data/btns
sdfmbiskd@#()fjjwe994jj5nKSIDnm199JJw992"

data/surfaces
gkgiiitnR**3204jjRjoowJSDOIISUDFNQ))(#(FNNFIIR*(((#JOQWK)!@#
```

Paradise Cracked

For all packs.

```
stereosystem
```

COPS 2170: The Power of Law

For all packs.

```
wowyouhaveguessedthepassword
```
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-07-14T09:14:41+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from Ekey
>
> COPS 2170: The Power of Law

For all packs.
Code: Select allwowyouhaveguessedthepassword
That's awesome. =D
## Post #45
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-14T15:42:22+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Yeah funny passwords
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-21T01:17:59+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Jigsaw Boom

> Folder/Pack
>
> Password

```
its_my_book.jar

DATA/effects
effects

DATA/fonts
fonts

DATA/gui
window_mini.png

DATA/hi
lets_play.tga

DATA/level
lets_play.tga

DATA/loading
load_me_plz.png

DATA/low
lets_play.tga

DATA/menu
mY_menu_title.png

DATA/mid
lets_play.tga

DATA/music
music.ogg

DATA/pocket
pokeymon.jpeg

DATA/pre
lets_play.tga

DATA/trofei
trofeis
```
## Post #47
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-23T14:40:28+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Adelantado. Trilogy. Book one

```
XV34gd97WaP22
```
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-25T19:32:24+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

SevenCore

```
bighit!777
```
## Post #49
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-08-12T04:04:16+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

thanks =)
## Post #50
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-04-12T19:33:32+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Cadenza: Music, Betrayal and Death Collectors Edition

```
7nGxrOcLvCy2SY557Vtyx939LQjeaFewPRsAnmNzypYmizOmATpMwt2uhL7Q
```
## Post #51
- Username: tmgley
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 04, 2011 8:07 am
- Post datetime: 2014-07-10T03:16:35+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Hi,
I'm trying to get the passwords for 12 Labours of Hercules

Please help me
## Post #52
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-07-10T09:49:35+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Password for 12 Labours of Hercules:

```
yE?objectives_episode_%02_cost_%02d
```
## Post #53
- Username: tmgley
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 04, 2011 8:07 am
- Post datetime: 2014-07-15T18:55:55+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thank you so much merlinsvk

Now I have another problem, I need to unpack this game: Dead Reckoning: Silvermoon Isle Collectors Edition


I appreciate any help you can give me
## Post #54
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-15T22:06:24+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from tmgley
>
> Thank you so much merlinsvk

Now I have another problem, I need to unpack this game: Dead Reckoning: Silvermoon Isle Collectors Edition


I appreciate any help you can give me

```
7VtaFesmATpMwtiL7Q79nzOyx2mNzypYmwPR39LY55AuhGxrOcLvCy2SnQje
```
## Post #55
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-16T03:37:25+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

damn this will come in handy XD thank you!!
## Post #56
- Username: tmgley
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 04, 2011 8:07 am
- Post datetime: 2014-07-17T01:05:31+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thank you so much merlinsvk again

you are the best buddy
## Post #57
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-08-20T04:28:02+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Got a request for a game called Patriarch Xtasy.
The ".res" archive is a password protected zip file.

[http://www.mediafire.com/download/39x7z ... /client.7z](http://www.mediafire.com/download/39x7zz0k67dh69f/client.7z)
## Post #58
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-21T15:01:33+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from finale00
>
> Got a request for a game called Patriarch Xtasy.
The ".res" archive is a password protected zip file.

http://www.mediafire.com/download/39x7z ... /client.7z
ZipCrypto used. Here parts of password. I don't know how it's formed. Need full game

```
891882f7d4235da
```
## Post #59
- Username: clang7775
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 29, 2014 2:31 am
- Post datetime: 2014-09-28T18:39:17+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Wow excellent work!
## Post #60
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2014-10-08T15:54:47+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

not unpacking for me.
## Post #61
- Username: VegaRoXas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 05, 2014 5:06 am
- Post datetime: 2014-11-04T21:11:25+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thank you bro :3
Will try this
## Post #62
- Username: woliyanwei
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Dec 17, 2014 5:36 pm
- Post datetime: 2015-01-08T05:40:47+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thanks for posting your method!
## Post #63
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-05-14T23:24:43+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Anyone have the password for blackprophecy?
## Post #64
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-15T04:06:36+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Will this work with searching winrar password?
## Post #65
- Username: Swiss72
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 22, 2019 12:47 pm
- Post datetime: 2019-06-22T06:37:03+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Can you find the password from this zip file!

Thanks Daniel

The Zip File in Mediafire: [http://www.mediafire.com/file/bs666q14p ... 0.zip/file](http://www.mediafire.com/file/bs666q14p0qsc4x/model3-v240.zip/file)
## Post #66
- Username: nat56
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 22, 2018 11:29 pm
- Post datetime: 2021-07-27T09:07:30+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

> Reply from aluigi ↑Tue Mar 01, 2011 7:43 pm at Tue Mar 01, 2011 7:43 pm
>
> 
10009f09 is the memory address assigned to that instruction in hge.dll when it's loaded by Windows.
if you are lucky you should find the relative file offset at 0x9f09 of the file.
otherwise use an rva2file offset tool like my quickrva:
http://aluigi.org/mytoolz.htm#quickrva
game
Legendary Mahjong
[https://www.bigfishgames.com/games/1409 ... ry-mahjong](https://www.bigfishgames.com/games/14097/legendary-mahjong)
Searching the hge.dll file
100de8ab 3052 function where is handled the ZipCrypto password [32.le.12 &]
Could you write a detailed sequence of steps for finding a password?
## Post #67
- Username: benettonb1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 13, 2021 6:01 pm
- Post datetime: 2021-12-02T13:13:23+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Thank you bro :3
spicemoneylogin.in myfiosgateway
## Post #68
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2022-01-29T14:43:56+00:00
- Post Title: Re: Hacking Zip Passwords (C9)

Can anyone find the password to extract the files in this zip?

link to zip: [https://file.io/GdK3PUZ2Z7KL](https://file.io/GdK3PUZ2Z7KL)

The zip file is 86.6 mb.
