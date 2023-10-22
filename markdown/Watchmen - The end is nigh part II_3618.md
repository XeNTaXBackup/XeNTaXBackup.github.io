## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-07-29T21:23:32+00:00
- Post Title: Watchmen - The end is nigh part II

[http://www.megaupload.com/?d=5Q4DTDC1](http://www.megaupload.com/?d=5Q4DTDC1)

Here i have a NAZ archive of all the games data, my main interests if is the music, i can find traces of wav in there, but cant figure out the structure.

good luck
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-30T13:31:42+00:00
- Post Title: Watchmen - The end is nigh part II

The game have dos types of audio, both are headerless...
Well..a bit of explanation:
Compression of data: Zlib
Graphics: bmp and looks a DDS headerless too
Audios: Headerless, BUT the voices are compressed (maybe a dpcm variant, i don't know), and the musics are raw pcm at 44100Khz

So, you need a .naz unpacker and a audio reconvertor to dpcm to pcm

You can try yourself with a nice tool created by luigi (bugtest), called offzip
[http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)

I hope it helps a bit
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-07-30T16:54:40+00:00
- Post Title: Watchmen - The end is nigh part II

Webiste is down.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-30T17:02:56+00:00
- Post Title: Watchmen - The end is nigh part II

the website is up but it's better to use aluigi.org instead of aluigi.altervista.org when linking zip files because that hoster doesn't support direct linking (check on the Referer field).
so the link is [http://aluigi.org/mytoolz/offzip.zip](http://aluigi.org/mytoolz/offzip.zip)
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-07-30T17:19:34+00:00
- Post Title: Watchmen - The end is nigh part II

Got the file, but im confused as to which commands im suppose to use.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-30T17:30:19+00:00
- Post Title: Watchmen - The end is nigh part II

it's simple, if you want to see if a file contains one or more zlib/inflate blocks use:

```
offzip -z -15 -S file.dat 0 0
```
the second command with -z -15 is needed in case the first one finds nothing.
indeed exist 2 types of "inflate" blocks which are called Zlib (RFC 1950) and raw (RFC 1951).

if you already know the exact offset of the block you want to unpack use:

```
offzip file.dat output.dat 0xYOUR_OFFSET
```

if you want to extract any compressed block available in the file use:

```
offzip -z -15 -a file.dat c:\output_folder 0
```
## Post #7
- Username: simplesim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 01, 2009 7:52 pm
- Post datetime: 2009-08-01T12:10:19+00:00
- Post Title: Watchmen - The end is nigh part II

Hi,
I'm new here,   
Can someone help me with how to unpack and pack this archive game.naz in watchmen? I'm interested in the textures. 

Regards
## Post #8
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-10T17:29:23+00:00
- Post Title: Watchmen - The end is nigh part II

Sorry for the bump, but could I request an extractor or QuickBMS script that can extract the filenames as well? Thanks so much in advance!

Here's a fresh link of the naz:

```
http://www.megaupload.com/?d=16QTACCV
```
