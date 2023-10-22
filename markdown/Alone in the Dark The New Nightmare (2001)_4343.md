## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2010-04-17T22:05:08+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-04-18T12:20:39+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

In official aitd4 translations, there is a separated file with all texts. There you are, 2 language: brazil and italien(?). (Extracted texts are included, but the game can't use them!)
Copy the Provider folder into the root folder of the game.

The files without extensions, are compressed with gzip, but if you repack them, the game crash. But the game can be handle the unpacked file too, just rename to the original name. The textures are in these files. All of them are DDS, without header.

Any other question? 

By the way: "The New Nightmare", not the "A New Nightmare".
[aitd4_2lang.zip](https://xentaxbackup.github.io/file/2954_aitd4_2lang.zip)
## Post #3
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2010-04-18T14:27:50+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

Not in Dreamcast. PC and PS2 versions have their language files aside, but on Dreamcast (And I've checked both the English and French versions) the texts are translated in those files. I pretend to translate the Dreamcast version.
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-04-18T16:35:31+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

You didn't mentioned that.
Than you have to unpack all file(based on pc this is a lot files) and edit with hex editor. I don't know other way.
(unpack: rename to xy.gz and use an unpacker; 7zip, Winrar etc.)
## Post #5
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2010-04-18T19:08:59+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

Just wanted to know if someone could unpack the uncompressed files, before trying to do it the Hex way. I'm trying to adapt the official Spanish translation to Dreamcast (DC got only English and French).
## Post #6
- Username: MiLOxentax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 26, 2010 10:39 am
- Post datetime: 2011-06-29T09:07:52+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

Hi there. 
I have a question about extracting the contents from those files without extensions. evin, you said they are gzip compressed, so what do I need to unpack them? The gzip.bms from aluigi's website didn't work. Actually what I'm trying to get is the background images, which suppose to be inside those files alongside with texture files, and I'm guessing they can have DDS extension as well. It wouldn't be a problem to get a good dds viewer later, but first I need to get all the images out of the gzip containers. Please help.
## Post #7
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-06-29T10:40:03+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

Like I said: "unpack: rename to xy.gz and use an unpacker; 7zip, Winrar etc." Forget the BMS (but it could works).

But as hard as I tried, I couldn't make a working repacked file. So after you unpacked, you have to work with the unpacked files. The game can read them.

DDS compression in the game: 1.5.5.5 ARGB Mipmap2
I don't have DDS extractor or other texture tool! What I did, I did with hex editor.
[dcsel60.zip](https://xentaxbackup.github.io/file/4403_dcsel60.zip)
## Post #8
- Username: MiLOxentax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 26, 2010 10:39 am
- Post datetime: 2011-06-30T23:19:31+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

Oh, thank you evin! I opened that dds file you posted with IrfanView and it had one pre-rendered background image in it:

[http://s14.photobucket.com/albums/a340/ ... csel60.png](http://s14.photobucket.com/albums/a340/Sergunyasha/?action=view&current=dcsel60.png)

Which is awesome, and that's exactly what I was trying to get. If only there was a quick way to do the same with all the other files containing these dds pics, but looks like it takes some hustle with hex editor and I'm definitely not good with that.

I tried to do what you suggested: rename to xy.gz and use Winrar, but inside the archive there's an xy file which cannot be opened in any DDS Viewer, so I guess there's some kinda tweaking needs to be done to it.
## Post #9
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-07-01T13:08:45+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

That "xy file" is just the uncompresed data, not DDS. That contain texts, textures, and other things. Basically those contain everything.
## Post #10
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2013-12-29T05:00:17+00:00
- Post Title: Alone in the Dark: The New Nightmare (2001)

Hi.

I tried to find the texture of the character according to the information given by Evin, but it gives nothing.

Someone would he extract it ?

Thank you in advance 

Normally the start of the texture starts in the position  00095610 or the vicinity^^

sorry for my english. (translate google)

[http://www.mediafire.com/download/nkryn ... line02.zip](http://www.mediafire.com/download/nkryn65qkc33lwd/Aline02.zip)
