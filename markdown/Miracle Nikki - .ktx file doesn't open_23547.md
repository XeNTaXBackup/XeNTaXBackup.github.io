## Post #1
- Username: Lucy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 04, 2016 2:37 pm
- Post datetime: 2021-03-05T15:11:26+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

I have taken textures/sprites from a mobile game (Miracle Nikki) but I can't open them. They are in .ktx format but PVRTexTool doesn't open the files, tells that it is a wrong format or corrupted. I thought maybe its deciphered in some way, but I don't  know anything about that so I can't know for sure, so I need some help with that ^^' 
Attached is on of the textures..  
[10001-1.7z](https://xentaxbackup.github.io/file/19648_10001-1.7z)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-05T18:14:48+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

Yeah, it is not standard KTX Image.
You can see here how it should look like [http://wiki.xentax.com/index.php/KTX_Image](http://wiki.xentax.com/index.php/KTX_Image)

The one you have posted is encrypted in some way.
## Post #3
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-03-06T14:27:04+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

> Reply from Lucy ↑Fri Mar 05, 2021 11:11 pm at Fri Mar 05, 2021 11:11 pm
>
> 
I have taken textures/sprites from a mobile game (Miracle Nikki) but I can't open them.

This is custom made file format with blowfish encryption that was reverse engineered several times.
Latest version was deleted as tencent started the pursuit of enthusiasts.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-06T14:31:48+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

@aspadm, can you link to some documentation or at least some discussion regarding this format?

Also, what do you mean by "deleted"?
## Post #5
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-03-06T14:58:19+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

> Reply from ikskoks ↑Sat Mar 06, 2021 10:31 pm at Sat Mar 06, 2021 10:31 pm
>
> 
@aspadm, can you link to some documentation or at least some discussion regarding this format?

Ow, looks like they changed format.
Previous was like this:

```
char sign[2]; // "dr"
unsigned char version_a;
unsigned char version_b;
unsigned char trim; // number (0-7) of padding bytes
char ftype[3]; // "lua" of "png"

```


data is the blowfish encrypted (ECB for "png", CBC for "lua").
version_a and version_b is used in app to chose parts for key generation.

Decrypted data can be packed with LZ4.

> Also, what do you mean by "deleted"?

Some time ago there was a thread on xentax where somebody  posted a tool that decrypt files of MN (also known as "Love Nikki" etc.).
After that, one of the users (presumably from Vietnam) used this to publish information about the game events that have not yet been released, which is why tencent launched an investigation in the direction of localizers and others. The topic was removed from the forum, as the author of the tool asked for it.
## Post #6
- Username: Lucy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 04, 2016 2:37 pm
- Post datetime: 2021-03-08T18:59:42+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

Thanks everyone for responses   Thing is I know that the older version, that used .png was decrypted. But the tools for cracking the old one (at least the ones I tried before they were scrapped from internet or the ones that are still there) don't seem to work with the .ktx version. (I mean, duh, they weren't made for .ktx)
## Post #7
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-03-08T19:03:31+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

From which game version did you take sample .ktx file?
"png" signature also was in .ktx files, it's just flag for chosing right encryption method.
## Post #8
- Username: Lucy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 04, 2016 2:37 pm
- Post datetime: 2021-03-08T19:14:13+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

It's from miracle nikki for mainland china.
## Post #9
- Username: lunar23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 16, 2021 1:46 pm
- Post datetime: 2021-03-19T11:01:12+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

hope someone can decrypt the ktx file
## Post #10
- Username: lunar23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 16, 2021 1:46 pm
- Post datetime: 2021-03-21T03:20:50+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

I have several ktx files encoded from png files (the current png file is also an encrypted file but I can decrypt them). I used some softwares like Mali or PVRTexTool but can't open ktx file.
I hope someone can help me method to decode this ktx file. Attachments include the ktx file and the original png file. 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/14vjVYGft7oSTdWVA1q_MgiJxizy_2jmt?usp=sharing)
## Post #11
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-03-23T11:23:26+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

> Reply from lunar23 ↑Sun Mar 21, 2021 11:20 am at Sun Mar 21, 2021 11:20 am
>
> 
I hope someone can help me method to decode this ktx file. Attachments include the ktx file and the original png file.

Well, this is the encrypted textures. You can see characters "dr***png" at the end of files.
They have known file structure, but sharing the decryption keys is prohibited.
## Post #12
- Username: lunar23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 16, 2021 1:46 pm
- Post datetime: 2021-04-15T20:21:01+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

I desperately sought the decoding. I think the old key still works, but the script structure in bms doesn't match the new structure. Hope someone can help write a code that is suitable for the new structure.
## Post #13
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-04-15T20:33:36+00:00
- Post Title: Miracle Nikki - .ktx file doesn't open

Well, old script or LN_decode still works for files that use old key.
For the files encrypted with new keys you must change script AND aquire 26*26-1 = 675 new keys. After that you must use right key that chosed by version_a/b fields.
Sorry, but I can't say more as it will against forum rules (rule item 3, as the keys is a part of application).
