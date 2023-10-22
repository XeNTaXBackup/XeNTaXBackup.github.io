## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-01-11T16:25:56+00:00
- Post Title: Ghostbusters Wii .tex files

Simply enough, all textures in this game are similarly named to other counterparts. However, through emulator extraction, I have determined that the Wii graphics for this game are a bit higher quality than the other versions. Mind you this is the stylized version and not the realistic version. The .tex files are different than other versions as well. I was hoping someone could have a little look at them and maybe throw together a conversion tool or script to extract the textures.

[http://www.sendspace.com/file/nveiif](http://www.sendspace.com/file/nveiif) A sample .tex from the Wii version of the game that I'm pretty sure is unused, as it's number exceeds the number of entries that appear in-game in the Spirit Guide.
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-01-20T04:34:30+00:00
- Post Title: Ghostbusters Wii .tex files

Block is Zlibd

Output chunk
[http://cra0kalo.com/upload/staging/stor ... 000000.dat](http://cra0kalo.com/upload/staging/store/push/00000000.dat)


```
// Little Endian
// Tex ALg unknown
struct TexHeader
{
uint32 HeaderMagic
uint32 UnknownA
uint32 UnknownB
uint32 UnknownC
uint32 UnknownD
uint32 UnknownE
uint32 UnknownD
uint32 ImageWidth
uint32 ImageHeight
uint32 BufferPadding1
uint32 BufferPadding2
uint32 BufferPadding3
}

struct TexChunk
{
//Datablock
}

```


No idea what format the image compression is get me more files
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-01-20T11:52:57+00:00
- Post Title: Ghostbusters Wii .tex files

Sure, no problem.

Here ya go. These are a few from the UI and then a character (Stay Puft, specifically).

[https://www.dropbox.com/s/0mpkf41mp0zwbg2/gbwii-tex.zip](https://www.dropbox.com/s/0mpkf41mp0zwbg2/gbwii-tex.zip)
