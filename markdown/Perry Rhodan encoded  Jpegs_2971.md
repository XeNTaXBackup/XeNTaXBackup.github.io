## Post #1
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-03-16T10:55:42+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Hi, i've been trying to display the textures from the new Perry Rhodan adventure game but they seem to be encoded somehow   

i have attached the head texture of perry(atleast i think so   )

maybe someone can figure out how to make it viewable again  
[perry_head_diffuse.zip](https://xentaxbackup.github.io/file/1473_perry_head_diffuse.zip)
## Post #2
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2008-03-22T20:08:26+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Hi,

I've made a little tool which decrypts the file you sent. Please tell me if it works with other files, too.

You can download it from [http://gamefileformats.the-underdogs.in ... tperry.zip](http://gamefileformats.the-underdogs.info/files/decryptperry.zip)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-22T23:06:59+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Care to share the algo?
## Post #4
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2008-03-23T10:49:52+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Of course:

```
    byte xorValues[3] = {0x42, 0x99, 0x80};
    for (uint32 ofs = 0; ofs < size; ofs++) {
        uint32 value = ofs % 3;
        data[ofs] ^= xorValues[value] - 0x6E;
    }
}

```
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-03-25T18:17:12+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

thanks john_doe   

works fine, i tried a few different files(128x128 up to 1024x1024) and it converted them properly

would it be possible to convert them back with a simple tool too?

i saw the algo but unfortunately im no programmar and have no idea how it works
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-25T18:20:51+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Try using the same program. It might work.
## Post #7
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-03-25T20:35:17+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

lol yeah it does...   
thanks
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-25T20:46:45+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

btw this works because the algorithm uses XOR.
## Post #9
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2008-03-27T15:46:33+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

I dont know how good is the game but look great!

another xoring,congrats to john.

btw how did you reverse the xoring method,analysis of file or reversing exe?
## Post #10
- Username: kurt28
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 08, 2010 1:00 am
- Post datetime: 2010-09-08T17:48:04+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

> Reply from john_doe
>
> Hi,

I've made a little tool which decrypts the file you sent. Please tell me if it works with other files, too.

You can download it from http://gamefileformats.the-underdogs.in ... tperry.zip

Please, can you upload the file again?

Thanks.
## Post #11
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-09-09T16:56:01+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Of course, I hope I can still find it somewhere...
## Post #12
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-09-13T08:22:46+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

I found it and upload the tool here:
[http://www.xentax.com/uploads/author/jo ... tperry.zip](http://www.xentax.com/uploads/author/johndoe/decryptperry.zip)
## Post #13
- Username: kurt28
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 08, 2010 1:00 am
- Post datetime: 2010-09-14T16:46:05+00:00
- Post Title: Perry Rhodan encoded ? Jpegs

Thank you very much.
