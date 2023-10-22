## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-09-29T20:24:25+00:00
- Post Title: S3TC compression on those textures?

Could it be that these textures use the S3TC compression? I read it was introduced in DirectX 6, so it could be possible, cause Dungeon Keeper 2 was released in 1999.
[textures.rar](https://xentaxbackup.github.io/file/2404_textures.rar)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-10-03T09:29:17+00:00
- Post Title: S3TC compression on those textures?

S3TC has a fixed compression ratio, and those textures seem to have a variable compression ratio.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-03T13:11:08+00:00
- Post Title: S3TC compression on those textures?

Yeah I also read that.
Anyway in the meantime I found the class that handles the textures in the code.
Gotta investigate it as soon as I have some time.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-08T19:53:14+00:00
- Post Title: S3TC compression on those textures?

Ok, so I've been in touch with Darren Pattenden, one of the game's artists, and he tells me that the original textures were .PNG. Perhaps that helps.
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-08T19:58:28+00:00
- Post Title: S3TC compression on those textures?

Yeah I know, but the main engine textures are somehow compressed.
Here's the progress thread if anyone's interested:
[http://forum.keeperklan.com/dk2-texture ... -t220.html](http://forum.keeperklan.com/dk2-texture-format-t220.html)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-08T20:27:05+00:00
- Post Title: S3TC compression on those textures?

Yes, therefore I have asked Darren if he remembers anything about what the programmers did to those .PNG files he created. 

Good work by the way! Nice thread you got there!
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-08T20:59:42+00:00
- Post Title: S3TC compression on those textures?

Thanks for that 
Artists normally don't have much insights into code internals though.
Yeah, we finally found the code for de-/compression, we "just" need to misuse the exe as a dll for our purposes 
Pretty interesting, but yet complicated task.
