## Post #1
- Username: HankMoody47200
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Oct 03, 2011 6:00 pm
- Post datetime: 2011-10-05T11:27:11+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

Hi,

first of all, thanks to people currently helping me on the subject : 
TBU2, rollingtheboy, speeder from TDU:Central, among many others.

The goal of this topic to centralize discoveries about XMB format (TAG 'XMBF' in game files), with publishing the most complete specs available.

XMB is a configuration support, which can be extended to store many database tables (or files) in it.

In TDU1, they are used in :
defining sound configuration (e.g engine sounds)

In TDU2, it's a widespread usage such as :
storing database (cars, stats, clothes, pnjs, stores and so on)
sound configuration
vehicle physics
cameras
...

XMB files can be either encrypted or not. If that's the case, tdudec program should be used before opening, modifying then used to encrypt again in the end.

Feel free to contribute into this topic. Thanks in advance.

Now, ladies and gentlemen, specs below: 
[WIP]
## Post #2
- Username: tomsolo
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Sep 17, 2011 3:33 am
- Post datetime: 2011-10-05T15:52:21+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

Nice, but how become WIP ?
## Post #3
- Username: Speeder
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 05, 2011 4:17 am
- Post datetime: 2011-10-05T17:42:58+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

I've been working for half a hour on the .xmb camera file. 

Here is my investigate.   


1- You can edit the XMB format manually, with an HexEditor. The only thing to respect is the size restriction of course (you must pad with null). 

2- One interesting thing: you can swap cameras between cars just by editing their numbers. One problem: there are 163 cars in the camera's database... DLC or prototype cars should be inside.

3- Don't know how to edit X-Y-Z positions for the moment (eeh I only worked 30 minutes   ).

4- Camera offset is 940. (the car 1 camera is upper, but It must be default car or LP560 cameras  ).

5- I made only one edit, which disable auto-center function. 
[http://www.youtube.com/watch?v=IFjhqhL3Vh8](http://www.youtube.com/watch?v=IFjhqhL3Vh8)

Don't think editing clothes is interesting, gonna try to edit cars paints etc in the database, this is more interesting for us lol.   

Bonsoir.
## Post #4
- Username: HankMoody47200
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Oct 03, 2011 6:00 pm
- Post datetime: 2011-10-05T18:53:27+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

Merci bien  

> Reply from tomsolo
>
> Nice, but how become WIP ?It's not a status for people, means Work In Progress
## Post #5
- Username: tomsolo
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Sep 17, 2011 3:33 am
- Post datetime: 2011-10-06T05:41:08+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

> Reply from HankMoody47200
>
> Merci bien  
tomsolo wrote:Nice, but how become WIP ? It's not a status for people, means Work In Progress

Was a joke ))
## Post #6
- Username: Speeder
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 05, 2011 4:17 am
- Post datetime: 2011-10-08T17:51:11+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

Hey Guys! 

I made some research on the database system of TDU2, in oder to swap car colors. 

The first exemple I tried is to swap MP4-12C Green to Rosso Corsa Ferrari... looks easy hun? 

Everything worked fine during boot of the game and in game (no crashes etc...).
But when I tried to take a Green MP4, I couldn't: the color was glitched. 

I bought it so, but it didn't like a normal or basic MP4 paint (the orange one), it was a strange-metallic paint, which wasn't the basic one or the orange one.
[http://www.youtube.com/watch?v=R5R9En2Cd9s](http://www.youtube.com/watch?v=R5R9En2Cd9s)
 I'm working on this case.  

BTW I found in the file AIConfig (which is a .cpr) a Xml about physics etc... this is only for IA nope?

EDIT: it seems to be the real physics, not only the AI one.
## Post #7
- Username: tomsolo
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Sep 17, 2011 3:33 am
- Post datetime: 2011-10-09T21:02:07+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

> The first exemple I tried is to swap MP4-12C Green to Rosso Corsa Ferrari... looks easy hun?
>
> 
>
> Everything worked fine during boot of the game and in game (no crashes etc...).
>
> But when I tried to take a Green MP4, I couldn't: the color was glitched.

Hmm im tried swap color, but only works if size of bytes was same or program quit with exceptions. 

Im waiting Hank investigations, because we can't add nothing new data...

> BTW I found in the file AIConfig (which is a .cpr) a Xml about physics etc... this is only for IA nope?
>
> 
>
> EDIT: it seems to be the real physics, not only the AI one."

I think: no, this is only Ai specs.

All cars - extract bnk - have a *.dhk file, maybe contains car specific physic parameters(imho).
## Post #8
- Username: Xarlith
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 17, 2011 8:32 am
- Post datetime: 2011-10-10T05:16:51+00:00
- Post Title: [PC][Test Drive Unlimited 1/2] XMB files

> Reply from Speeder
>
> BTW I found in the file AIConfig (which is a .cpr) a Xml about physics etc... this is only for IA nope?

EDIT: it seems to be the real physics, not only the AI one.
As I can remember from my previous researches this file changes only AI behaviour. for example you can make AI faster. Other options such as physic seems to be unchanged despite of modifying AIConfig.cpr. It may be similar to Physics.cpr where only few of many options affects the game.

Don't bother simple xml files which are easy to mod. XMBF is a real challenge. Some of the parts of xmb files looks like an archive some like database...

> Reply from tomsolo
>
> All cars - extract bnk - have a *.dhk file, maybe contains car specific physic parameters(imho).
Yes, you are right. As it was said before dhk looks like havok physic file (hvk), and it changes some of the car parameters.
For test swap [any car]_high.bnk with other car's bnk and see what happens (i don't talk about looking at car model ). After swap car will accelerate faster/slower or will have different grip at launch. I wanted to know what is responsible for that and I discovered that swapping only .dhks and .xmbs inside each car's bnk package provides to the same effects. Xmbs are responsible for acceleration and dhks for grip. I don't wanted to tell about this because this will allow irresponsible people to take advantage in multiplayer but since bnk repacker is almost out it was a matter of time until someone else would find out about those 3 files.
