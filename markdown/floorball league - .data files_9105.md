## Post #1
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-06-17T07:37:01+00:00
- Post Title: floorball league - .data files

Hi
Can anyone unpack the files in this game?
Here is a demo game:
[http://www.fbl-game.com/downloads.php](http://www.fbl-game.com/downloads.php)
If you needed files PM me.
I think its engine is Ogre3D.
Thanks.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-22T18:48:55+00:00
- Post Title: floorball league - .data files

[http://aluigi.org/papers/bms/fbl.bms](http://aluigi.org/papers/bms/fbl.bms)
## Post #3
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-06-25T09:44:32+00:00
- Post Title: floorball league - .data files

Thanks for the script.It works perfectly.
why doesn't the reimport option work?
It says it x files reimported but it didn't.
regards.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-25T11:16:30+00:00
- Post Title: floorball league - .data files

> Reply from deepshit
>
> Thanks for the script.It works perfectly.
why doesn't the reimport option work?
It says it x files reimported but it didn't.
regards.
They must be the exact same size.
## Post #5
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-06-25T12:52:39+00:00
- Post Title: floorball league - .data files

I know that.
They are the same size.I just change the color of some textures.that's it.
I think it's because of MEMORY_FILEs files.
## Post #6
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-07-01T07:07:34+00:00
- Post Title: floorball league - .data files

@aluigi
I analyzed your script line by line.I can almost understand how it extracts files.
But I can't understand how did you find the encryption.
How did you do that?examining the .exe file?
thanks
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-01T09:35:01+00:00
- Post Title: floorball league - .data files

for the reimporting in reality it's possible to accomplish it by adding another step.
in short if you divide the script in one that does the decryption and another that does the extraction you can use:
- the first to decrypt the original file
- the second to extract the content
- modify the needed files and remove the others
- reimport the modified files using the second script
- use the first script (normally, so no -w -r) to re-encrypt the new archive, the function works in both the ways

for the algorithm I used the classic way debugging the executable adding breakpoint on ReadFile, the function that does the decryption job is visible immediately
## Post #8
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2012-07-03T07:48:57+00:00
- Post Title: floorball league - .data files

> Reply from aluigi
>
> for the reimporting in reality it's possible to accomplish it by adding another step.
in short if you divide the script in one that does the decryption and another that does the extraction you can use:
- the first to decrypt the original file
- the second to extract the content
- modify the needed files and remove the others
- reimport the modified files using the second script
- use the first script (normally, so no -w -r) to re-encrypt the new archive, the function works in both the ways

for the algorithm I used the classic way debugging the executable adding breakpoint on ReadFile, the function that does the decryption job is visible immediately

Thanks.It worked.You're genius and awesome.
I converted your script to c# functions and it works like a charm.
