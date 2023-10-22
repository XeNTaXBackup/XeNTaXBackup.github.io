## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-02-04T02:17:00+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

I'm trying to translate the text of this game and it turns out that it is only possible by doing through a memory viewer/editor but there is no way to save it.
The memory viewer somehow decompress the text while loading the game through the an emulator, is there a way to decompress/compress a file so the translation can be possible through an hex editor?

Sample: [https://drive.google.com/open?id=1N8UPK ... J2C0epmfxf](https://drive.google.com/open?id=1N8UPKMkyCXwXhVY-jgkEWjJ2C0epmfxf)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2019-02-04T21:50:50+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

no idea what this is compressed with. the sample can be read like so though

```
uint count;

struct c
{
  uint chunk;
  uint datalen;
  uint padlen;
};

c cs[count];

FSeek(0x800);

local uint i;
for(i=0;i<count;++i)
{
  struct
  {
    byte data[cs[i].datalen];
    byte pad[cs[i].padlen-cs[i].datalen];
  } block;
}

Assert(FEof());


```
## Post #3
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-02-04T22:54:58+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

How can I compile the code to try and decompress the file?
## Post #4
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-03-06T12:57:37+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

I don't like to double post in threads but has anyone got into it?
## Post #5
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2019-06-23T16:59:37+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

It seems that our tasks are the same - I also want to translate this game, and I have been looking for a way for this for a long time.

I think the “BZZ” file extension itself probably indicates LZ77-like compression, which is also used on PS1. I tried the appropriate PS1 LZ77 script for QuickBMS, but so far they have not unpacked anything. It is also unclear how to unpack this file: in whole or in part (after all, this is a kind of “archive”). However, in the "LOADING" folder there are BZZ files of the type "L_MCOOK.BZZ", and I understand that this is a compressed TIM file. While I work with him.
## Post #6
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-07-03T08:43:14+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

Hello, thanks for this! For now isn't possible to translate as the TXT tool is being made but unpacking the BZZ file is possible, someone developed a tool. (The BZZ's use LZ compression)

As soon everything is texted and fully working I will release a TOOLPACK for this game.


  Note: This BZZ tool works with the other Behaviou Interactive games that use BZZ and also works with BZE that is used in the PC ports.
## Post #7
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2019-07-24T21:35:25+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

> Reply from rubinho146 ↑Wed Jul 03, 2019 4:43 pm at Wed Jul 03, 2019 4:43 pm
>
> 
I will release a TOOLPACK for this game.
 It would be great!
## Post #8
- Username: JanoxDev545
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 20, 2019 12:04 am
- Post datetime: 2019-08-19T16:21:10+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

Are the bzz files not part of BuzzBundle? did I read like that?

I would also like to rip some textures and models

When is your tool pack available?


here is the link where I read this:
[https://www.file-extension.org/extensions/bzz](https://www.file-extension.org/extensions/bzz)

byebye say Jannik.
## Post #9
- Username: JanoxDev545
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 20, 2019 12:04 am
- Post datetime: 2019-08-19T16:32:49+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

But somehow you can not open it in BuzzBundle. ?_?
## Post #10
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-10-01T11:35:21+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

Sorry for the wait, for around this month or the next one will create a pack with every detail on how to extract both files, sounds, textures and import back too. Regarding models you would need someone to help in that regard since I don't know how that would work, will post news soon.
## Post #11
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2020-04-16T09:50:06+00:00
- Post Title: Bugs Bunny Lost in Time psx (BZZ File)

Here is the toolpack to translate the game.

[viewtopic.php?f=32&t=22006](https://forum.xentax.com/viewtopic.php?f=32&t=22006)
