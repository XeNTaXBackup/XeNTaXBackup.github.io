## Post #1
- Username: NunamedDragon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 7:31 pm
- Post datetime: 2021-02-08T12:14:42+00:00
- Post Title: Fatal Frame 1 Sub File

Hi i've been trying to create a proper undub of Fatalframe 1 for the og Xbox. I've manage to identify the English sub file (its just placeholders text, see image attached). Unfortunately I've been unable to identity a way to edit it. I believe it to be a compiled C file (if its the case then I'm screwed).

Would someone please just take a look at the attached and confirmed my suspicions and that its not a proprietary file format? 
I'm not familiar with c
Thanks
[FF1X_E_Placeholder.7z](https://xentaxbackup.github.io/file/19492_FF1X_E_Placeholder.7z)
## Post #2
- Username: lehieugch68
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 09, 2019 7:09 pm
- Post datetime: 2021-04-07T11:43:31+00:00
- Post Title: Fatal Frame 1 Sub File

This is the decoded text, but I'm not sure about the file's structure.
[ig_msg_e.obj.txt.zip](https://xentaxbackup.github.io/file/19867_ig_msg_e.obj.txt.zip)
## Post #3
- Username: NunamedDragon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 7:31 pm
- Post datetime: 2021-04-07T12:15:21+00:00
- Post Title: Fatal Frame 1 Sub File

> Reply from lehieugch68 ↑Wed Apr 07, 2021 7:43 pm at Wed Apr 07, 2021 7:43 pm
>
> 
This is the decoded text, but I'm not sure about the file's structure.

Omg thanks so it was possible, was it easy?
If so is possible to reencode the file once edited?

I'd would be more than eternally grateful if you could at minimum just point me in a right direction
## Post #4
- Username: valiuspiu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 23, 2021 6:09 pm
- Post datetime: 2021-06-23T10:19:21+00:00
- Post Title: Fatal Frame 1 Sub File

I have a question, how were you able to get the placeholder sub files to show up in-game?

Also, I too am interested in this project, but I'm new to modding Xbox OG games in general.  Anyone knowledgeable about decrypting and reencrypting obj files for this game?
## Post #5
- Username: NunamedDragon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 7:31 pm
- Post datetime: 2021-06-24T10:24:00+00:00
- Post Title: Fatal Frame 1 Sub File

> Reply from valiuspiu ↑Wed Jun 23, 2021 6:19 pm at Wed Jun 23, 2021 6:19 pm
>
> 
I have a question, how were you able to get the placeholder sub files to show up in-game?

Also, I too am interested in this project, but I'm new to modding Xbox OG games in general.  Anyone knowledgeable about decrypting and reencrypting obj files for this game?

By cheating, switched the game to french and change the sub files located /msg by renaming ig_msg_e (english) to ig_msg_f (french) assuming your using the pal version,

to properly do it you'll have to learn hex editing and edit the xbe. 

/tim contains,  item images, gui, title screen, option screen backgrounds . such a title screen that first loads. Try switching to french or another language that FF supports, and changing the language suffix to that and have a play, such as getting the Japanese load screen and title to appear while in french language etc.

I didn't bother doing more trial & error/research as someone else messaged me that they where doing their own. This was back in march.
As for decoding and recoding the sub file, I'm afraid I'm unable to help.

They lazy way i had attempted to undub it. would edit the hex and force it to another language. Then replace the _f suffix with the edit sub file (if i had figured it out) and load in the japanese menu items.

Good luck

My log of me manipulating the files
Fatal Frame 1,

File play around
letter at end of file name denotes language e = english, j = japanese etc
m0_event_e.obj = english 
m0_event_j.obj = japanese 

* = Unconfirmed
event\

m0_event_e.obj effects text for mirrors, clocks no critical items.

*ig_msg_e.obj possible text of critical items, camera,books etc

tim\
Folder of textures for menu items such as title screen loading screen etc
.xp2 Image File

title_e.xp2 initial fatl frame/project zero on inita loading

*msn00ttl_e.xp2 00-04 Starting images for each night including the Hurimo intro

msg\
contains the subtitle files
## Post #6
- Username: valiuspiu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 23, 2021 6:09 pm
- Post datetime: 2021-06-25T07:20:44+00:00
- Post Title: Fatal Frame 1 Sub File

Thank you for all the info and explanation!  Ah, I had forgotten that the non-English languages would've required subs for the English audio as well.  So the person working on this is in this forum?

At least, it seems the mystery is how to edit the text for the English placeholder subs in the obj and then re-encrypt it to work with the game.
