## Post #1
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-10-22T09:34:49+00:00
- Post Title: Battlefield 3 , Packages .cas

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-10-23T05:44:19+00:00
- Post Title: Battlefield 3 , Packages .cas

.cas files are for origin to decrypt and rebuild game files from on launch date. i doubt it would be legal to decrypt them with something other than origin.
## Post #3
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-10-23T16:09:14+00:00
- Post Title: Battlefield 3 , Packages .cas

> Reply from Pepper
>
> .cas files are for origin to decrypt and rebuild game files from on launch date. i doubt it would be legal to decrypt them with something other than origin.

Are you sure about that ?!
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-10-23T18:55:03+00:00
- Post Title: Battlefield 3 , Packages .cas

pretty sure. considering they werent in the beta, and the files that were in the beta are now only kb, the .cas file is decrypted by origin and puts the contents into the real files. kinda like .sid/sim with steamworks titles.
## Post #5
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-10-25T16:15:36+00:00
- Post Title: Battlefield 3 , Packages .cas

> Reply from Pepper
>
> pretty sure. considering they werent in the beta, and the files that were in the beta are now only kb, the .cas file is decrypted by origin and puts the contents into the real files. kinda like .sid/sim with steamworks titles.

The game is out now , and after install with orgin the same files , and nothing decrypted so it's not like .sid/sim    

any one can help ??
## Post #6
- Username: mitsuhiko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 29, 2011 9:30 pm
- Post datetime: 2011-11-03T22:31:39+00:00
- Post Title: Battlefield 3 , Packages .cas

> Reply from killerpepo
>
> Pepper wrote:pretty sure. considering they werent in the beta, and the files that were in the beta are now only kb, the .cas file is decrypted by origin and puts the contents into the real files. kinda like .sid/sim with steamworks titles.

The game is out now , and after install with orgin the same files , and nothing decrypted so it's not like .sid/sim    

any one can help ??

CAS files:

```
          char header[4];
          char sha1[20];
          int32 data_length;
          char padding[4];
      };
```


CAT files:

```
          char sha1[20];
          int32 offset;
          int32 size;
          int32 cas_num;
      }

```


CAS at CAT files are basically just long lists of entries. The CAT file additionally has the header "NyanNyanNyanNyan" before the first entry. CAT points to CAS files.

A Python library to read the contents of those and others is available here: [https://github.com/mitsuhiko/frostbite2-stuff](https://github.com/mitsuhiko/frostbite2-stuff)
## Post #7
- Username: Ponderance
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 10, 2011 6:42 pm
- Post datetime: 2011-11-10T10:56:47+00:00
- Post Title: Battlefield 3 , Packages .cas

My question now appears to be, do I want to learn Python just to get into these .cas files?  Hmmm..
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-11-15T21:57:41+00:00
- Post Title: Battlefield 3 , Packages .cas

I was very wrong, sorry about that, but yeah, how do you use these? running the latest version with python doesnt work after the refactoring.
## Post #9
- Username: KIWIDOGGIE
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Jul 28, 2009 1:33 am
- Post datetime: 2012-06-01T13:16:30+00:00
- Post Title: Battlefield 3 , Packages .cas

I have been working on these

[Main.cas](http://allenthinks.com/VenicePkg_CasOutput.log)
[Patch](http://allenthinks.com/VenicePkg_CasOutputPATCH.log)
