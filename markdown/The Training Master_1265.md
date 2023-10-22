## Post #1
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-21T02:53:46+00:00
- Post Title: The Training Master

I'm working on a small project, The Training Master.

This will be a trainer system for pc games.  A trainer, for all you that doesn't know, is a program that allows you to change features in a game that is normally unchangable from within the program.  For example, you could change the name of your character.  However, trainers are usually developed to modify parts of the game as to make it easier to play for people who problems but still like the game or story of the game, and wish to see it through. IE, Infinity Life (aka God Mode).

Anyway, similar to MexCom, this program will support a wide variety of games, and will allow user addins.  A difference, that maybe Mr Mouse might incorporate into MexCom, maybe not.  Is that it will allow 3 different type of updates, one is for the software client itself, at the moment, the USER client is around 25k (real lightweight).

Then there is the game database, which will have 2 versions. One is the official version, which will have test/tried sections and the other is the Unofficial version, this one will allow people to add to the database through a web interface that gets rolled into the unofficial database for others to download.  Next they get "voted" on, if they worked for you, and after so many "OKs" then it get automatically rolled into the official database for downloading.

Any thoughts on this? or ideas on how it might be better?
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-22T21:09:09+00:00
- Post Title: The Training Master

Well, adding HTTP support for downloading from HTTP only added 6k to the program, i think thats pretty good, considering its all hand written.  So I'm at 25k for the app so far. No external software needed except standard winapi dlls.

```
GetHttpToFile(Url, Filename);
ParseUrl(Url, TUrlParse);

TUrlParse = record
  Username: String;
  Password: String;
  Host: String;
  Port: Word;
  Path: String;
end;

```


Haven't implemented Username/Passwords yet, but only cuz i don't have a need for it.  If someone else would like these wrapped in a dll, feel free to ask.
## Post #3
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-05-23T00:09:40+00:00
- Post Title: The Training Master

I'm sort of replying out of pity but I think you've got a good thing going and you should continue it. I have a problem with the name though. "The Training Master" just doesn't roll off the tongue the way it should.
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-23T00:14:43+00:00
- Post Title: The Training Master

Well, I wasn't going for something that rolls off the tongue, but what would you suggest?
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T02:22:38+00:00
- Post Title: The Training Master

Hi mate,

Good concept for a program, but it might be a fair bit of work. I mean, writing code to open an archive is easy enough, but this type of program would need you to know what files to edit, what byte offset to edit, etc., or assuming that you want the trainer to run while the game is running, it means that you will have to hack the memory addresses.

This is a great idea, and definately go ahead and give it a go - I just hope you don't spend too much time trying to do it because I know it will be quite time consuming 

Good luck!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T07:07:49+00:00
- Post Title: The Training Master

Rahly and I first PMed each other about this idea, and as I said there, I think it is a good idea. 

The idea of running the trainer that gives you the chance to get infinite health/ammo/lives in your favourite game is appealing, especially if other hackers/users can upload a scripted process that will be included in the database that the trainer can connect to. 

However, this is indeed a lot of work, considering that any trainer running should either alter memory locations while the game is running, or alter files on the harddrive (of course backing-up old original files). 

What might be another problem, but it depends on what kind of programs/trainers you allow, is hidden processes in these trainers. Sure, a game might be changed so it will have a God Mode, but meanwhile the script/program may perform hidden tasks that the user won't be particulary fond of. If it does this in a smart way, the trainer may still "pass the vote". 

Yet, the idea of updating via the web is also an interesting feature that may be something to do with MexCom in the future. As it is, I just completed a new feature in the program itself that will allow users to quick-add a custom script to their own resource file (while backing up and adding to a collection the current MRF). Also, they can choose to use another MRF and set it as the Base MRF. It works as a charm, and you can even use a custom MRF that only contains one script, if you want, while easily being able to switch back to a previously saved MRF.
## Post #7
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-05-23T08:14:03+00:00
- Post Title: The Training Master

> Reply from Rahly
>
> Well, I wasn't going for something that rolls off the tongue, but what would you suggest?
Something like ULTIMATE CHEAT SYSTEM 2000?

Actually, I don't know. I'll let you know if I think of something.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-23T22:11:46+00:00
- Post Title: The Training Master

Well the only reason I was going to use "The Training Master" was because I have an Icon and Logo picked out.  A buff guy with no shirt and a large axe who is the "training master"
## Post #9
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-05-24T03:32:40+00:00
- Post Title: The Training Master

Ah. That makes sense then. The best I could do was 'Godmode' as the name of the tool but it isn't that good a name.
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-05-25T00:09:04+00:00
- Post Title: The Training Master

could always go by the acronym, TTM
