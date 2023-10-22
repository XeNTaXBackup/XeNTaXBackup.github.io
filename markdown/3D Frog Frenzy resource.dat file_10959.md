## Post #1
- Username: Jamie0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 11, 2013 4:12 am
- Post datetime: 2013-11-13T12:49:15+00:00
- Post Title: 3D Frog Frenzy resource.dat file

Hi,

I'm trying to look inside the 3D Frog Frenzy "RESOURCE.DAT" file, however, a look with a hex viewer indicates some form of encryption. 3D Frog Frenzy is an awesome game, and for a small project I'm porting it to use JS/canvas, so it will run on new systems, but this file contains graphics, sounds, etc.


I've attempted to use a DreamKiller quickbms script to decrypt/extract the archive, but to no avail. I get the following


This lead me to think that the archive was either compressed (hence the zlib reference) or encrypted. I attempted using various zlib libraries to in/deflate the RESOURCE.DAT file, but all attempts failed.

I've seen a suggestion that the RESOURCE.DAT might be a hidden .cab file, but cabextract spits errors, and the headers aren't wrong. Because I can't use a known plaintext on the first several bytes compared to what they should be (so not RC4 or anything similar), I'm guessing that AES is (likely) used, or a similar function. 

Binaries and data files are available on request, thanks.
## Post #2
- Username: computerlife22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 11, 2014 3:09 am
- Post datetime: 2014-08-10T19:12:00+00:00
- Post Title: 3D Frog Frenzy resource.dat file

I'm having the same problem. I own 3D Frog Frenzy, but the DAT file seems to be completely encrypted. Is it possible to maybe pull the files from memory while the game is running?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-11T12:05:43+00:00
- Post Title: 3D Frog Frenzy resource.dat file

[http://zenhax.com/viewtopic.php?f=9&t=55](http://zenhax.com/viewtopic.php?f=9&t=55)
