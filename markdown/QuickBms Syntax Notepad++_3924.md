## Post #1
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-04T21:43:22+00:00
- Post Title: QuickBms Syntax Notepad++

I made some really not notable Syntax Highligther for Quickbms, its not perfect (yet).

Just add this:

```
download zip.

```

Into the file C:\Documents and Settings\Username\AppData?\Notpad++\userDefineLang.xml
Enter %APPDATA%\Notepad++\userDefineLang.xml  in Start -> Run, thx aluigi 
I am not hundred percent sure about the path, because i dont have a english system.

Cheers Evilpie

*Edit*
[userDefineLang.zip](https://xentaxbackup.github.io/file/2596_userDefineLang.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-04T23:30:57+00:00
- Post Title: QuickBms Syntax Notepad++

excellent idea, I was thinking to it just a couple of days ago while watching the black-only font that was starting to become boring :)

you can add also the put putdstring and putct commands added in the last version of the quickbms.
then there are some small mistakes, for example the first line must be "<NotepadPlus>" without the '/' and the file where placing it is called UserDefineLang.xml (without 'd') which is loaded from the same folder of Notepad++ (at least here, I use the zip only package not the installer).
if the installer uses the user's path I guess the correct one should be %APPDATA%\Notepad++\userDefineLang.xml (place it in Start->run)

for the rest it works good, maybe would be good to improve it a bit adding also the Math/If operators (like '&=' and '&'), the TEMPORARY_FILE keyword, the list of encryption and compression names and so on (if you want I can do it, I have all the stuff listed here so it's a quick job)
## Post #3
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-04T23:44:09+00:00
- Post Title: QuickBms Syntax Notepad++

Thank you,

i've added the things you mentioned, but could you please add the alogs, its a bit more work if you dont have proper list.

Cheers evilpie
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-05T00:28:08+00:00
- Post Title: QuickBms Syntax Notepad++

if I have done everything correctly the following covers all the stuff supported by quickbms (current 0.3.10).
I can't paste it here because the forum returns an Internal Server Error if I do it, so I have attached it to the post
[UserDefineLang.zip](https://xentaxbackup.github.io/file/2593_UserDefineLang.zip)
## Post #5
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-05T00:42:20+00:00
- Post Title: QuickBms Syntax Notepad++

Nice, this was fast.
I made one more change, now strings gets marked.

I've attached it to this post.

Cheers
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-05T11:53:56+00:00
- Post Title: QuickBms Syntax Notepad++

do you know how to mark as comments also the strings like #mycomment and not only # comment?
a small thing, when I uploaded the script the first time I used >< (><) which was wrong so I immediately corrected it with <> but seems you already downloaded the first version with that little mistake
## Post #7
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-05T12:19:11+00:00
- Post Title: QuickBms Syntax Notepad++

Okay i made this 2 minor fixes for #comment and ><. 
This time i attached the zip to the first post 

Cheers Evilpie
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-06T07:44:14+00:00
- Post Title: QuickBms Syntax Notepad++

Nice!
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-12-26T16:40:03+00:00
- Post Title: QuickBms Syntax Notepad++

could you add the "include" ans "quickbmsver" function to the list please? I'm too dumb to figure it out myself...
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-12-27T09:53:43+00:00
- Post Title: QuickBms Syntax Notepad++

This is awesome. I've tinkered with the custom syntax highlighting stuff in Notepad++ before, but never thought to do it for QuickBMS (or MexScript, for that matter). Great work, guys!
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-12-27T14:05:37+00:00
- Post Title: QuickBms Syntax Notepad++

I have just finished to write a Notepad++ userDefineLang.xml from scratch:

[http://aluigi.altervista.org/papers/bms ... neLang.xml](http://aluigi.altervista.org/papers/bms/userDefineLang.xml)

I have tried to add everything and, most important, I have tried to choose the best colors limiting the "xmas tree" effect and at the same time highlighting what it's most used and useful.

for example the counter variables like 'i' and 'j' are now in red bold trying to limit common mistakes like using them outside cycles or the same variable in nested cycles.
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-12-28T15:40:39+00:00
- Post Title: QuickBms Syntax Notepad++

Thanks a lot for this Luigi! Magnificent update on the old xml!     
Working with QuickBMS is so much smoother now!
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-12-28T19:51:34+00:00
- Post Title: QuickBms Syntax Notepad++

Hm, keywords in the comments are marked with a color - should be grey.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-12-29T22:17:27+00:00
- Post Title: QuickBms Syntax Notepad++

here I have tried to create a bms containing the following data and I don't see the problem, it's all gray:

```
# open
#clog "asdf" OFFSET SIZE
# asdf encryption asdf
```
I use Notepad++ 6.2.3
## Post #15
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-12-31T11:54:14+00:00
- Post Title: QuickBms Syntax Notepad++

Oh, sorry, I've checked again and you're right - it only seems to be the case with "if".
