## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2023-01-30T21:10:14+00:00
- Post Title: Compressed game files

Hello guys! 
I need a help with decompressing those files, compression type should be oodle. Though, unfortunatelly I can't do anything with them, something might be wrong with them! I'll be very grateful if anyone could give me a tip or advice. Thanks 
[sample.7z](https://xentaxbackup.github.io/file/23366_sample.7z)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-31T12:51:57+00:00
- Post Title: Compressed game files

If it's really oodle blocks, around last 7 bytes from blocks are not actual part of them, second byte doesn't represent supported compression scheme (it should be around 1-12) and you didn't provide output sizes for samples - oodle decoder doesn't have safe api to process block partially if input/output sizes are incorrect, and guessing it not an option unless you're trying to brute-force them.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2023-02-01T10:12:51+00:00
- Post Title: Compressed game files

Good to know that they are indeed compressed with oodle! It's giving some hope  Files came from bigger archive, maybe it will help more [https://www.mediafire.com/file/dl0a0w5p ... 00.7z/file](https://www.mediafire.com/file/dl0a0w5pwo7m2p6/asset_game_00.7z/file)
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-01T18:41:25+00:00
- Post Title: Compressed game files

@zaramot: Such containers are extractable, but without filenames (names table is either encrypted or it's hashes table). What's the game name?
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2023-02-01T18:49:16+00:00
- Post Title: Compressed game files

I sent you PM  I don't care much about filenames - of course it's very cool to have them, though for me personally only clear and decompressed data is important!
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-01T19:27:21+00:00
- Post Title: Compressed game files

Here is script for extracting files from such containers. May not work for other containers though, it's hard to guess things from only one sample. 



 fh_extract.zip
(592 Bytes) Downloaded 36 times
## Post #7
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-23T13:31:48+00:00
- Post Title: Compressed game files

Sorry to hijack this post but i guess i also have file with similar compression.
Seems like script not working on it.

Is it possible to extract attached file "Spiritovod" .
(I zip file to attached , you find main file which i wanted to extract inside it)
[plugin.zip](https://xentaxbackup.github.io/file/23435_plugin.zip)
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-23T13:58:28+00:00
- Post Title: Compressed game files

@SubZer0: It's just stack of oodle chunks of different sizes with no info about output sizes, so it's not possible to do anything with them. You need more data to process them, it may be somewhere in the file (if it's a fragment) or in a separate related file. Anyway, it's not related to the format used by the game discussed in this topic.
## Post #9
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-23T15:17:14+00:00
- Post Title: Compressed game files

> Reply from Spiritovod ↑Thu Feb 23, 2023 9:58 pm at Thu Feb 23, 2023 9:58 pm
>
> 
@SubZer0: You need more data to process them, it may be somewhere in the file (if it's a fragment) or in a separate related file.

Sorry for off topic question.
Where do or how do i get this fragmented size related info.
Is there any knowledge base from where i can learn reading files like you.
## Post #10
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-24T12:11:03+00:00
- Post Title: Compressed game files

@Spiritovod  : i found output size of all 7 files in that bin.

file 1 -1055 bytes
file 2 - 656 bytes
file 3 - 1130 bytes
file 4 - 1227 bytes
file 5 - 682 bytes
file 6 - 584 bytes
file 7 - 571 bytes

So can we make script which extract file from compressed bin if we know output?
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-25T01:22:43+00:00
- Post Title: Compressed game files

@SubZer0: Judging by contents, it seems you're trying to extract raw data from an UE package. UE packages, including io store packages (utoc/ucas) are supported in UE related tools like fmodel or umodel, it's better to try them out first. But, again, it has nothing to do with this topic.
