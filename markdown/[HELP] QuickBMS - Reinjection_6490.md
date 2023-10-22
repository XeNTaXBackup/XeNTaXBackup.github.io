## Post #1
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-24T15:23:27+00:00
- Post Title: [HELP] QuickBMS - Reinjection

Hello everyone 

Today i was editing some game files with the QuickBMS and I was wandering how to get it to "re-inject" back into the .pak file...
So that i can actually run the damn thing 

I know there are instructions but - atleast to me- they are unclear and as i am a big noob to this i do not understand how to do it :s

Any help would be much appriciated!

for now i will QQ
## Post #2
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-24T20:19:40+00:00
- Post Title: [HELP] QuickBMS - Reinjection

just bumping it up a wee bit so someone replies...

maybe ill add more info...

I have extracted the file called Editor.pak

it extracted to give 3 folders containing more stuff...

I edited one file in one of the folders - now i would like to know how would i go about putting the whole thing back into a .pak so i can run it with the game.
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-24T23:09:18+00:00
- Post Title: [HELP] QuickBMS - Reinjection

If am I right, delete those unmodified files, then 
1. open QuickBMS with -r -w parameters (e.g. make a shortcut to quickbms.exe with -r -w in Target field), 
2. select .bms script used for extracting
3. select original .pak file (rather choose its copy, if something will go bad)
4. select directory with modified files that you want to reimport back

You are done.
## Post #4
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T09:16:23+00:00
- Post Title: [HELP] QuickBMS - Reinjection

> Reply from merlinsvk
>
> If am I right, delete those unmodified files, then 
1. open QuickBMS with -r -w parameters (e.g. make a shortcut to quickbms.exe with -r -w in Target field), 
2. select .bms script used for extracting
3. select original .pak file (rather choose its copy, if something will go bad)
4. select directory with modified files that you want to reimport back

You are done.

Thanks very very much!
Does it matter if the script is a .txt file? It worked for extracting so im assuming it will work just as well


-----------------------------------------
Edit 
-----------------------------------------

It says zero files injected even though i followed the steps :s
Any tips?

had a couple of files to inject so i used the "file name" to add the entire file is that correct? (file name is just an example what i mean is i used the "" to mark the folder)


[](http://img813.imageshack.us/i/problemw.png/)

Uploaded with [ImageShack.us](http://imageshack.us)

^^^ my error
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T10:40:12+00:00
- Post Title: [HELP] QuickBMS - Reinjection

depends by the script because some scripts don't support reinjection (like mk9.bms)
## Post #6
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T10:53:34+00:00
- Post Title: [HELP] QuickBMS - Reinjection

> Reply from aluigi
>
> depends by the script because some scripts don't support reinjection (like mk9.bms)






this is where the script is found - [http://aluigi.org/papers/bms/crysis2.bms](http://aluigi.org/papers/bms/crysis2.bms)

can anyone confirm if i can re-inject?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T10:55:47+00:00
- Post Title: [HELP] QuickBMS - Reinjection

crysis2.bms works perfectly in reinjection mode, indeed it's used for creating mods and cheats
## Post #8
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T11:11:47+00:00
- Post Title: [HELP] QuickBMS - Reinjection

> Reply from aluigi
>
> crysis2.bms works perfectly in reinjection mode, indeed it's used for creating mods and cheats

thanks for the confirmation - i must be doing something wrong then 

would it bother you if i made a video of what im doing so you can tell me when i am doing wrong?
## Post #9
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T11:29:41+00:00
- Post Title: [HELP] QuickBMS - Reinjection

Alright this is what im doing:
WATCH IN 1080P OR YOU WON'T SEE THE LETTERS!
 
[http://www.youtube.com/watch?v=awd6UBoEilk](http://www.youtube.com/watch?v=awd6UBoEilk)



im going to get the shopping done now - it would be amazing if someone replied by the time i get back
## Post #10
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T13:10:06+00:00
- Post Title: [HELP] QuickBMS - Reinjection

ughhh just figured it out -_-

the modded texture was over twice the size of the original!
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T13:27:36+00:00
- Post Title: [HELP] QuickBMS - Reinjection

the problem is simple: you MUST select the folder where you extracted the files and NOT the one where is located the file you want to import.

I have explained and repeated this thing various times and that's why I say that the reimport feature is exactly identical to the extraction except that instead of clicking on quickbms.exe you must click on the link.

while for the size of the file, yes it must be minor/equal than the original one.
in case of size problems quickbms will interrupt the reimport and will show you the exact error.
## Post #12
- Username: badMan
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Apr 24, 2011 11:21 pm
- Post datetime: 2011-04-25T14:13:15+00:00
- Post Title: [HELP] QuickBMS - Reinjection

> Reply from aluigi
>
> the problem is simple: you MUST select the folder where you extracted the files and NOT the one where is located the file you want to import.

I have explained and repeated this thing various times and that's why I say that the reimport feature is exactly identical to the extraction except that instead of clicking on quickbms.exe you must click on the link.

while for the size of the file, yes it must be minor/equal than the original one.
in case of size problems quickbms will interrupt the reimport and will show you the exact error.

thanks again 

you're the best !


now... to find a program that dosent create images twice the size of the original >.>
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-30T07:39:37+00:00
- Post Title: [HELP] QuickBMS - Reinjection

> Reply from badMan
>
> aluigi wrote:the problem is simple: you MUST select the folder where you extracted the files and NOT the one where is located the file you want to import.

I have explained and repeated this thing various times and that's why I say that the reimport feature is exactly identical to the extraction except that instead of clicking on quickbms.exe you must click on the link.

while for the size of the file, yes it must be minor/equal than the original one.
in case of size problems quickbms will interrupt the reimport and will show you the exact error.

thanks again 

you're the best !


now... to find a program that dosent create images twice the size of the original >.>

Here you go mate:

```
http://loadfiles.in/21p7ghao0554/Change_File_Size.rar
```


I wrote it for exactly this kind of things
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-30T16:09:21+00:00
- Post Title: [HELP] QuickBMS - Reinjection

@michalss
he intends something completely different.

in short you can't increase the size of a file to reimport without touching all the rest of the file format because this is exactly like having a puzzle and you can replace a piece with a smaller one but you can't replace it with a bigger one without changing all the rest.
and sometimes changing all the rest is really a pain :)
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-30T16:23:37+00:00
- Post Title: [HELP] QuickBMS - Reinjection

> Reply from michalss
>
> badMan wrote:aluigi wrote:the problem is simple: you MUST select the folder where you extracted the files and NOT the one where is located the file you want to import.

I have explained and repeated this thing various times and that's why I say that the reimport feature is exactly identical to the extraction except that instead of clicking on quickbms.exe you must click on the link.

while for the size of the file, yes it must be minor/equal than the original one.
in case of size problems quickbms will interrupt the reimport and will show you the exact error.

thanks again 

you're the best !


now... to find a program that dosent create images twice the size of the original >.>

Here you go mate:
Code: Select allhttp://loadfiles.in/21p7ghao0554/Change_File_Size.rar

I wrote it for exactly this kind of things

Ahh ok. But anyway if file is smaller and you want to be sure that reimport will be ok than use it
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-02T13:42:30+00:00
- Post Title: Re: [HELP] QuickBMS - Reinjection

if the file is smaller than the original quickbms automatically cleans the remaining space filling it with zeroes
