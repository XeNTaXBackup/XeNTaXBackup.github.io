## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-06-04T23:55:36+00:00
- Post Title: [PC] Angry Birds Rio

Hi guys,
I would like to make tiny-translation of this game, but I got one problem.
Game shows texts that are not in TEXTS_BASIC.DAT file (where they were in normal Angry Birds).
E.g. "Are you sure you want to quit?"

[](http://www.ulozisko.sk/obrazky/409937/angry.jpg)

It's not in string file nor in .png files. So where is it?

Game has some .lua files, but they are xored/encrypted/don't know. Is it possible that missing texts are defined there?

I attach some .lua, if somebody is interested.
## Post #2
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-06-06T02:46:30+00:00
- Post Title: [PC] Angry Birds Rio

Dude, check your PM.
## Post #3
- Username: amin fear
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 24, 2011 10:03 pm
- Post datetime: 2011-08-24T14:32:44+00:00
- Post Title: [PC] Angry Birds Rio

Hi to all experts in this great forum ...

this is my first post and i need help about translating the " Angry Birds " game ...

anybody here can help me for editing this game ?

i need to change the strings of " TEXTS_BASIC.DAT " file .... in UNICODE format .... 

which tool i must use for changing the strings of this .DAT file ?

and i want to ask the user of previous post : (( Herdell )) ... to send me a PM too about other strings editing ....

plz ?

any help would be appreciated ...
## Post #4
- Username: rraallvv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 31, 2012 11:45 am
- Post datetime: 2012-03-31T03:55:18+00:00
- Post Title: [PC] Angry Birds Rio

any one?

I need to translate angrybirds too
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-31T12:00:48+00:00
- Post Title: [PC] Angry Birds Rio

So LUA files encrypted with AES 256bit CBC mode and nulled initialization vector.

Here are the keys that I managed to pull out :

Angry Birds
Str = USCaPQpA4TSNVxMI1v9SK9UC0yZuAnb2
Hex = 55534361505170413454534E56784D49317639534B39554330795A75416E6232

Angry Birds Rio
Str = USCaPQpA4TSNVxMI1v9SK9UC0yZuAnb2
Hex = 55534361505170413454534E56784D49317639534B39554330795A75416E6232

Angry Birds Seasons
Str = zePhest5faQuX2S2Apre@4reChAtEvUt
Hex = 7A65506865737435666151755832533241707265403472654368417445765574

Angry Birds Space
Str = RmgdZ0JenLFgWwkYvCL2lSahFbEhFec4
Hex = 526D67645A304A656E4C466757776B5976434C326C5361684662456846656334

Example using OpenSSL

```
openssl enc -aes-256-cbc -d -K 55534361505170413454534E56784D49317639534B39554330795A75416E6232 -iv 0 -in gamelogic.lua -out gamelogic.lua.dec
```


For HighScores & Settings lua files other keys. If needed i can post it 

h4x0r.
## Post #6
- Username: rraallvv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 31, 2012 11:45 am
- Post datetime: 2012-04-01T02:02:53+00:00
- Post Title: [PC] Angry Birds Rio

thanks very much my friend!
very useful info
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-02T15:04:29+00:00
- Post Title: [PC] Angry Birds Rio

For encrypt back use -e instead of -d
## Post #8
- Username: escribblings
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 13, 2013 8:40 pm
- Post datetime: 2013-04-13T13:12:37+00:00
- Post Title: [PC] Angry Birds Rio

> Reply from Ekey
>
> So LUA files encrypted with AES 256bit CBC mode and nulled initialization vector.

Here are the keys that I managed to pull out :

Angry Birds
Str = USCaPQpA4TSNVxMI1v9SK9UC0yZuAnb2
Hex = 55534361505170413454534E56784D49317639534B39554330795A75416E6232

Angry Birds Rio
Str = USCaPQpA4TSNVxMI1v9SK9UC0yZuAnb2
Hex = 55534361505170413454534E56784D49317639534B39554330795A75416E6232

Angry Birds Seasons
Str = zePhest5faQuX2S2Apre@4reChAtEvUt
Hex = 7A65506865737435666151755832533241707265403472654368417445765574

Angry Birds Space
Str = RmgdZ0JenLFgWwkYvCL2lSahFbEhFec4
Hex = 526D67645A304A656E4C466757776B5976434C326C5361684662456846656334

Example using OpenSSL
Code: Select allopenssl enc -aes-256-cbc -d -K 55534361505170413454534E56784D49317639534B39554330795A75416E6232 -iv 0 -in gamelogic.lua -out gamelogic.lua.dec
For HighScores & Settings lua files other keys. If needed i can post it 

h4x0r.

Hi - first post here.

I have been trying to obtain the encryption key for Seasons highscores.lua, with no luck at all.

I tried following some rather comprehensive instructions over here: [[Q] Angry Birds Rio encrypts settings/highscores with AES](http://forum.xda-developers.com/showthread.php?t=1015380), but I don't have the first clue about what I am doing.

Is there any chance you could help out with the AES key for Seasons highscores?

As far as Original, Rio, Space and StarWars goes, I am good - but there are others over at XDA who would like those keys as well.  However, I am only asking for Seasons.

Thank you for your time.
