## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-05T11:31:41+00:00
- Post Title: GoW GNF Textures

Hi,

I am getting some GNF textures from the GoW PS4 game, but I couldn't open them with Noesis. I am not familiar with the GNF format and don't understand much looking at the pixel data, so I don't have any info to provide unfortunately. The header looks like any other GNF I have seen, but they aren't loaded properly for some reason.

All I can do is provide some samples : [http://www.mediafire.com/file/mxvav6jyg ... W_Texs.rar](http://www.mediafire.com/file/mxvav6jyghcnhd3/GoW_Texs.rar)  I hope someone can works this out.

Thanks.
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-06-05T19:23:55+00:00
- Post Title: GoW GNF Textures

multi chunk files, and they seem to compressed. no offset matches, no nothing.

GNF header is 0x110 (0x112) bytes. some file size info at 0x0C, decompressed size seems to be at 0x104, format could be at 0x108, number of surfaces at 0x10A. no resolution info anywhere to be found tho. data start signature or compression id is 0x8C06 at 0x112. that's all i got real quick. i don't like to deal with this compression stuff.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-05T19:58:16+00:00
- Post Title: GoW GNF Textures

> Reply from episoder
>
> multi chunk files, and they seem to compressed. no offset matches, no nothing.
Thanks for taking a look.

I just got the files by finding the GNF header in the archive and copying the given data size in the header. I haven't thought more info would be required. I will extract some files properly based on the offsets and sizes in the archive toc. It might have the missing information you mentioned.
## Post #4
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2018-06-08T17:51:51+00:00
- Post Title: GoW GNF Textures

here tools for anyone need it i found them in ps4 sdk
## Post #5
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-12T00:06:26+00:00
- Post Title: GoW GNF Textures

> Reply from Sajjad Rahim
>
> here tools for anyone need it i found them in ps4 sdk
Those are highly illegal, you might want to take it down according to forum rules, plus they do not include the proper libraries to work so its useless.
## Post #6
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2018-06-12T17:04:16+00:00
- Post Title: GoW GNF Textures

> Reply from mono24
>
> Sajjad Rahim wrote:here tools for anyone need it i found them in ps4 sdk
Those are highly illegal, you might want to take it down according to forum rules, plus they do not include the proper libraries to work so its useless.

okay... deleted
## Post #7
- Username: gaylord3000
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 29, 2018 5:09 am
- Post datetime: 2018-07-29T03:45:22+00:00
- Post Title: GoW GNF Textures

Texpacks have some funny blockchain in them. Each block it seems stores texture size, 32bit number that match with number near GNF header if it is not last block or to number that always goes after 01 00 00 00 1c 00 00 00. Wad files has some references with real texture names and id attached to them. But had no luck to make any texture to be viewed in gnfviewer. Either block are not aligned or they are compressed/encrypted.
[Log.7z](https://xentaxbackup.github.io/file/14674_Log.7z)
## Post #8
- Username: gaylord3000
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 29, 2018 5:09 am
- Post datetime: 2018-07-30T01:39:58+00:00
- Post Title: GoW GNF Textures

Sharing my "research" that i managed to do. Now i hit a wall and dont know what to do next.

[https://imgur.com/a/422sHTr](https://imgur.com/a/422sHTr)
## Post #9
- Username: gaylord3000
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 29, 2018 5:09 am
- Post datetime: 2018-08-05T14:42:46+00:00
- Post Title: GoW GNF Textures

I extracted some data that I think are textures. I suspect oodle compression.
after running some data trough [https://github.com/powzix/kraken](https://github.com/powzix/kraken) decompressor I managed to get this:
[](https://ibb.co/ejM9BK)

It always decompresses 262,144 bytes and fails. I changed code in decompressor to save output buffer before exiting.
Is there anyone that could identify why its failing. Maybe data is not in solid block and it needs to be recollected before decompressing?
I adding some data that might be related.
[https://mega.nz/#!6HAj2aoK!7LORl1BMrtRN ... Jv7Piu7n9I](https://mega.nz/#!6HAj2aoK!7LORl1BMrtRNWL2jHaQvhxolazuqsPY_DJv7Piu7n9I)

Using oo2core_3_win64.dll always fails.
## Post #10
- Username: gaylord3000
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 29, 2018 5:09 am
- Post datetime: 2018-08-15T23:04:29+00:00
- Post Title: GoW GNF Textures

Never mind. Figured it myself.
[](https://ibb.co/gURRD9)
