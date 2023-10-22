## Post #1
- Username: NHIM
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 05, 2006 1:15 pm
- Post datetime: 2006-06-05T05:18:34+00:00
- Post Title: Translate language in Game use HEX workshop(help)

hi everybody
i want translate somethings in my game ( strings on button) 
i see someone who translate it by using HEX WORKSHOP 
this is the menu in file EXE before translate(Japanese)

this is the menu in file EXE after translate(English)


How do they do? Could you help me using HEX to do it?(or direct me what should i do)

i read about EXE file but i don't understand what address(offset?) i can realize to modify it 
Help me
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-02T22:38:20+00:00
- Post Title: Translate language in Game use HEX workshop(help)

Sorry for the late response, but other chores are taking up all of my time.

See [http://www.xentax.com/?p=90](http://www.xentax.com/?p=90)

But when I'm done with that, I will go through the requests and check if I can help out.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-21T23:22:41+00:00
- Post Title: Translate language in Game use HEX workshop(help)

Just search for the string (in unicode) in the exe and replace it. The problem is, that your translated string has to be less than or equal in length to the original one.
