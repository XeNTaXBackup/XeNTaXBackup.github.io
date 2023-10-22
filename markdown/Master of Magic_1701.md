## Post #1
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-19T15:46:26+00:00
- Post Title: Master of Magic

Hi!

I would like to translate Master of Magic to hungarian, and i considered that MultiEx Commander can edit Master of Magic's lbx files. But after that i can not edit with the program, i checked the game list of MultiEx, and i saw, that Master of Magic is in the supported games list, but not editable. Can you make MultiEx Commander to be capable to edit Master of Magic?

Best Regards,
gandrus
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-19T17:37:33+00:00
- Post Title: Master of Magic

Hi, thanks for the tip. It's an old format and MexCom support is also old. I will see what I can do.
## Post #3
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-01-19T17:51:42+00:00
- Post Title: Master of Magic

```
Get FILENUM Int 0 ;
Math FILENUM -= 1 ;
Get FOO Long 0 ;
Get FOO Int 0 ;
Get FNX Long 0 ;
For F = 1 To FILENUM ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos NEXTFILE 0 ;
Get FSIZE Long 0 ;
Math FSIZE -= FOFFSET ;
GoTo FNX 0 ;
GetDString FNAME 20 0 ;
SavePos FNX 0 ;
Log FNAME FOFFSET FSIZE FOFFSETX 0 ;
GoTo NEXTFILE 0 ;
Next F ;
```

Try this BMS-script, it may work better. 
I haven't tested it though, since I don't have any archive from the game. I've also attached the compiled script in a ZIP-file. 
[lbx.zip](https://xentaxbackup.github.io/file/586_lbx.zip)
## Post #4
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-19T18:27:48+00:00
- Post Title: Master of Magic

Thank you Mr.Mouse! I shall try. I must register, when i want to use the script code, you given, right? I have no paypal account, but i shall check it when i finished the night shift.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-19T19:25:08+00:00
- Post Title: Master of Magic

And thanks PXR! I wil test it , I should have a MoM archive somewhere.
## Post #6
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-19T19:34:26+00:00
- Post Title: Master of Magic

Mater of Magic is abandonware now, you can download it from: [http://www.abandonia.com/games/en/189/MasterofMagic.htm](http://www.abandonia.com/games/en/189/MasterofMagic.htm) 
if you think you need it.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-19T19:39:47+00:00
- Post Title: Master of Magic

Thanks yeah, but I was already downloading it from The Underdogs, one of my favourite sites
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-19T22:13:46+00:00
- Post Title: Master of Magic

Okay, sorry PXR, your script doesn't work. 

Here's one that does. 

```
Get FN Int 0
Set FNJ Long 512
Set US String _
Get U1 Int 0
Get U2 Long 0
SavePos D 0 
Get STOP Long 0
GoTo D 0
For T = 1 To FN
SavePos FOO 0
Get FO Long 0
SavePos Jump 0
Get FS Long 0
Math FS -= FO
GoTo FNJ 0
If FNJ = STOP 
String FN3 += US
String FN3 += T
Log FN3 FO FS FOO 0
String FN3 -= T
String FN3 -= US
GoTo Jump 0 ;
Else
GetDString FN1 9 0
GetDString FN2 23 0
String FN1 += US
String FN1 += FN2
String FN1 += US
String FN1 += T
Log FN1 FO FS FOO 0
SavePos FNJ 0
GoTo Jump 0
EndIf
Next T
GoTo Jump 0
SavePos FOO 0
Math FO += FS
Set FS Long 0
Log "" FO FS FOO 0
```


I had to play some tricks with the MexCom script to make it possible for you to edit them. Note that the soundfx.lbx file can't hold all filenames(only some fixed space reserved), so I had to fix that. 

Also, there will allways be a placeholder "noname1" at the back of each archive. Do not replace this. It is needed to be able to replace the real last file of the archive (the one before "noname" ). 

Add it to your MRF file (Add BMS to MRF option) and enjoy!
[lbx.zip](https://xentaxbackup.github.io/file/588_lbx.zip)
## Post #9
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-01-20T08:42:44+00:00
- Post Title: Master of Magic

> Reply from Mr.Mouse
>
> Okay, sorry PXR, your script doesn't work. 

Here's one that does. 
Code: Select allImpType SFileOff
Get FN Int 0
Set FNJ Long 512
Set US String _
Get U1 Int 0
Get U2 Long 0
SavePos D 0 
Get STOP Long 0
GoTo D 0
For T = 1 To FN
SavePos FOO 0
Get FO Long 0
SavePos Jump 0
Get FS Long 0
Math FS -= FO
GoTo FNJ 0
If FNJ = STOP 
String FN3 += US
String FN3 += T
Log FN3 FO FS FOO 0
String FN3 -= T
String FN3 -= US
GoTo Jump 0 ;
Else
GetDString FN1 9 0
GetDString FN2 23 0
String FN1 += US
String FN1 += FN2
String FN1 += US
String FN1 += T
Log FN1 FO FS FOO 0
SavePos FNJ 0
GoTo Jump 0
EndIf
Next T
GoTo Jump 0
SavePos FOO 0
Math FO += FS
Set FS Long 0
Log "" FO FS FOO 0

I had to play some tricks with the MexCom script to make it possible for you to edit them. Note that the soundfx.lbx file can't hold all filenames(only some fixed space reserved), so I had to fix that. 

Also, there will allways be a placeholder "noname1" at the back of each archive. Do not replace this. It is needed to be able to replace the real last file of the archive (the one before "noname" ). 

Add it to your MRF file (Add BMS to MRF option) and enjoy!
Oh, okey. I just looked at the specs in the wiki. 
BTW, no terminators ( ; )? New MexBinder already?
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T08:56:27+00:00
- Post Title: Master of Magic

> Reply from PXR
>
> BTW, no terminators ( ; )? New MexBinder already?

That's right. I guess I have first rights to work with it.  
It will be released with the new version of MexCom. I want to make sure the stuff actually works, noticed some strange goings on while I created the above script, and really want to make sure the Open command works properly as well. I'm thinking to also include an option to load something into a buffer that you can manipulate a bit (like XORing it with some value). But perhaps that will be for a future version. Ahhh, so much to do so little time.
## Post #11
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-20T15:22:31+00:00
- Post Title: Master of Magic

I have no Paypal in here, but my older Brother sended the money to you with his Paypal, when shall he get the unlock key?
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T16:14:54+00:00
- Post Title: Master of Magic

> Reply from gandrus
>
> I have no Paypal in here, but my older Brother sended the money to you with his Paypal, when shall he get the unlock key?

What's his name?
## Post #13
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-20T17:29:35+00:00
- Post Title: Master of Magic

His name is Zoltan Andrusecz and he sent the money via paypal with this name from his yahoo emailaddress.
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T17:46:19+00:00
- Post Title: Master of Magic

Ok, you should have the code now. Thanks !
## Post #15
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-20T18:24:31+00:00
- Post Title: Master of Magic

Thank you for the code, i registered the MultiEx Commander.
## Post #16
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-20T18:47:27+00:00
- Post Title: 

Hmm, the MultiEx Commander working, but i must use the same number of characters like the english version, and i cannot use other fonts like "Ã¡" "Ã©" (i can edit lbx files with a simple FAR editor in this way), can you do anything about this problem, please?
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-20T18:57:17+00:00
- Post Title: 

I'm not sure I understand what you mean. 

When do you need those characters? What's exactly the problem?
## Post #18
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-20T19:23:26+00:00
- Post Title: 

When I am making the translation to translate a sentence to Hungarian I have to use the same number of characters like the english sentence has.
This is problematic of course.
Is there any possibility that MultiEx can change the original english sentences to a longer or shorter Hungarian ones?
If I use less or more characters for the translation then in the game it won't be good.
Besides I would use a Hungarian code page therefore a Hungarian characterset in MultiEx for the translation (like 852 codepage)?
For example: check builddat.lbx, there is a word "Granary" i want to change to "MagtÃ¡r" that is the hungarian equivalent for Granary, but if i write "Granary" to "MagtÃ¡r", in the game wont be good, many texts will be shifted.
## Post #19
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-21T00:05:27+00:00
- Post Title: 

Mexcom can't change how the game program works, only extract and/or import files from the archives.  if the game is limited to only ANSI characters, thats something you'd have to take up with the programmers of the game, not us.
## Post #20
- Username: gandrus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 19, 2006 11:37 pm
- Post datetime: 2006-01-21T06:02:20+00:00
- Post Title: 

Ok. Thx.
