## Post #1
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-03-20T12:23:27+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

Hello, anyone can convert this file to xml / excel files equal to the PC?

Thank you.
[crysis2-3.xml.rar](https://xentaxbackup.github.io/file/6223_crysis2-3.xml.rar)
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-02-26T17:32:18+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

Can anyone help with this?
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-04-23T11:03:21+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

Up.

Someone managed to change the texts of the PS3, please help me.

Att
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-23T13:17:19+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

> Reply from timartinelli
>
> Hello, anyone can convert this file to xml / excel files equal to the PC?

Thank you.Did someone manage to do this for PC CryXmlB files? If so then please give a link.

On the other hand: did you have a look using a hex editor?

There's a may be index table and a bunch of zero terminated strings some containing LF (0x0A).
So marking a block and replacing 00 by 0D0A would give you this snippet:

...
Hold %1 to Activate Engine
Hold %1 to Activate Engine

ui_interaction_openvalve
[act] %1 to Open Valve
[act] %1 to Open Valve

ui_interaction_openvalve_hold
Hold %1 to Open Valve
Hold %1 to Open Valve

ui_interaction_jump
[act] %1 to Jump
[act] %1 to Jump

ui_interaction_sprint
Hold %1 to Sprint
Hold %1 to Sprint

ui_interaction_swim
Hold %1 to Swim Faster
Hold %1 to Swim Faster
...
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-04-23T14:04:41+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

extraxt text is not a problem, problem is repack of the text it does not matter if it is PC,X360 or PS3 all the same
## Post #6
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-04-23T14:40:36+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

So in Crysis 2. I used the files from the PC, and did again. pak (zip), and it worked, however in crysis 3 could not do it....

The xml PC, files are xml excel.
## Post #7
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-04-24T11:24:21+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

Friends, I saw that the problem is not in the xml, well I can not get to them to know all the files. Pak (zip) I'm doing the PS3, says the game is corrupted.

I've tried with winrar, 7zip, 7zip without compression, and still the same error.

I could only edit the text changing. Pak directly in notepad + +.

I am attaching the xml text of the ps3, if anyone has any idea.

english_xml
[http://www.mediafire.com/?2cota9bgbnajf1n](http://www.mediafire.com/?2cota9bgbnajf1n)
spanish_xml
[http://www.mediafire.com/?mab54vpqd0ucbi2](http://www.mediafire.com/?mab54vpqd0ucbi2)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-24T15:06:03+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

> Reply from timartinelli
>
> [...]Pak (zip) I'm doing the PS3, says the game is corrupted.

> I've tried with winrar, 7zip, 7zip without compression, and still the same error.
Hmm, don't get what you are doing.

First step is to unpack a pak using PakDecrypt.exe, right?

Then text strings in an xml are to be changed. As for a safe test only overwrite one string
(NOT to insert any additional char) and let us hope the index table can be left unchanged.

Last step would be to repack the xml(s) into a pak what is not possible so far.
(Using winrar or something similar would only make sense if the same tool allowed unpacking the (original) pak before.)

> I could only edit the text changing. Pak directly in notepad + +.
The game does not accept your modified pak, does it?
## Post #9
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-04-24T15:17:54+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

> Reply from shakotay2
>
> Hmm, don't get what you are doing.

First step is to unpack a pak using PakDecrypt.exe, right?

Then text strings in an xml are to be changed. As for a safe test only overwrite one string
(NOT to insert any additional char) and let us hope the index table can be left unchanged.

Last step would be to repack the xml(s) into a pak what is not possible so far.
(Using winrar or something similar makes no sense.)
I used PakDecrypt.exe and also 7zip to unpack. to unpack is no problem.

I did several tests because in Crysis 2 PS3, so I made a new pak using 7zip, and worked well.

> The game does not accept your modified pak, does it?

Yes agreed, but I did not increased the size of the string, look what I did.

Original
menu_press_start_continue
PRESS START BUTTON TO CONTINUE
PRESS START BUTTON TO CONTINUE

modified
menu_press_start_continue
PRESS START BUTTON TO CONTINUE
APERTE O BOTÃ„O START               

completed by the end with space to stay with the same size of the original string.

That changed the text in the game, and he did not catch. working well.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-24T15:27:23+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

> Reply from timartinelli
>
> That changed the text in the game, and he did not catch. working well.Ok, that's fine.   (Although somewhat restricted.)

I made a request in another thread concerning rc.exe of the Crysis SDK.

Not sure whether the zips to be created with it are identical with the paks(?)

But atm it doesn't work either.
## Post #11
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-04-24T15:36:39+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

Got it, let's see if anyone can.
## Post #12
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-07-12T13:25:24+00:00
- Post Title: Crysis 2/3 CryxmlB(.xml) - _xml.pak (PS3)

hello friends, anyone will be able to extract the xml to an xml normal?
please if anyone can help ...
