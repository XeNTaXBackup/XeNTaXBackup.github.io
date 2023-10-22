## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-27T22:58:33+00:00
- Post Title: [xbox360] Mafia 2 texture file

Hello, I want to look at the mafia 2 textures from xbox but they seem compressed or something.
Can anyone look at the file: [http://www.mediafire.com/download/w231c ... 0000003.7z](http://www.mediafire.com/download/w231cecpn0cbhwv/00000003.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-29T04:29:38+00:00
- Post Title: [xbox360] Mafia 2 texture file

i have not been able to get a clean texture yet but i will post what i've seen so far, it is big-endian header and 1024x1024 dxt1 and possibly a normal map texture and probably swizzled.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-29T07:10:53+00:00
- Post Title: [xbox360] Mafia 2 texture file

> Reply from AceWell
>
> i have not been able to get a clean texture yet but i will post what i've seen so far, it is big-endian header and 1024x1024 dxt1 and possibly a normal map texture and probably swizzled.this is exactly what you said. thanks for looking in it   I can post more samples if needed.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-29T07:23:46+00:00
- Post Title: [xbox360] Mafia 2 texture file

> Reply from Tosyk
>
> I can post more samples if needed.
yes please, i am stuck on this one
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-29T17:46:59+00:00
- Post Title: [xbox360] Mafia 2 texture file

> Reply from AceWell
>
> yes please, i am stuck on this onesorry for the delay I jest get back home. here the files: [http://www.mediafire.com/download/h39p9 ... /ccerb3.7z](http://www.mediafire.com/download/h39p91sc22ni9yg/ccerb3.7z)
not sure which files are textures.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-15T11:12:53+00:00
- Post Title: [xbox360] Mafia 2 texture file

i made a Noesis script to open your samples  


 tex_Mafia2_X360_dat.zip
(734 Bytes) Downloaded 19 times



it turns out all i had to do to get a clear image was swap the byte order from big to little endian
