## Post #1
- Username: anpharos
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 09, 2020 2:38 am
- Post datetime: 2020-08-08T18:59:14+00:00
- Post Title: Translate *.vis

Hi, I know this topic has already been discussed but I'm new in this and I hope you can guide me a little, I'm trying to translate a game developed in Visionaire (.vis) so far only and managed to get the images but I am only interested in getting the texts and replace them with a translation. 

I already tried using [download/file.php?id=9382](https://forum.xentax.com/download/file.php?id=9382) but it tells me that it can't read the key. 

Any ideas?
## Post #2
- Username: anpharos
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-08T19:57:49+00:00
- Post Title: Translate *.vis

Ok, I have some questions:

1. Can you attach example VIS files?
2. Did you try to use quickbms or Unpakke or any other tools? [viewtopic.php?p=79505#p79505](https://forum.xentax.com/viewtopic.php?p=79505#p79505)
3. What key did you use?
4. What is the title of this game?


As you can read [here](https://zenhax.com/viewtopic.php?p=6507&sid=9c3f5734def1fd97c59d275fb9e26d1b#p6507) quickbms script 
should support reimporitng. Read manual [here.](https://aluigi.altervista.org/papers/quickbms.txt)
## Post #3
- Username: anpharos
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 09, 2020 2:38 am
- Post datetime: 2020-08-08T20:28:39+00:00
- Post Title: Translate *.vis

Ok, first thanks for the answer.
Following your recommendation I used the quickbms method and it works very well to extract everything, I suppose that the texts I am looking for will be either in the .dat or .vbi file. Do you know how I can extract or read those files?

By the way, the game I'm trying to translate I don't know if I can comment on it in this forum since it's for people over 18 years old and I don't want to get anyone in trouble.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-08T21:05:22+00:00
- Post Title: Translate *.vis

You can PM me game title and some sample files.

To be sure where are the text strings, you can use 
basic text searching in Total Commander (if files are uncompressed)
[https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #5
- Username: anpharos
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 09, 2020 2:38 am
- Post datetime: 2020-08-08T23:06:35+00:00
- Post Title: Translate *.vis

I already sent you the files by PM, however the files I assume are compressed since it is not possible to see understandable text in them.
## Post #6
- Username: anpharos
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-09T09:33:09+00:00
- Post Title: Translate *.vis

I have checked your samples. DAT files are uncompressed (you can see some XML file on the end in hex editor).

But VBI files are compressed with zlib. You can use offzip to extract data

```
offzip.exe -a 000008ff.vbi C:\VBI_OUT
```

Here is the link [https://aluigi.altervista.org/mytoolz/offzip.zip](https://aluigi.altervista.org/mytoolz/offzip.zip)

When you extract data and open file in hex editor, you will se some
text strings [https://imgur.com/a/6bS1PPn](https://imgur.com/a/6bS1PPn)

Then you can edit them and use reimport option of offzip to replace those strings

> -r       reimport mode that works EXACTLY like in QuickBMS

And as for VBIN file format, it is something like this:

```
4 bytes - unknown
4 bytes - uncompressed file size
4 bytes - compressed file size
x bytes - compressed file data
```
## Post #7
- Username: anpharos
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 09, 2020 2:38 am
- Post datetime: 2020-08-09T19:47:30+00:00
- Post Title: Translate *.vis

Thanks, I managed to open the file with the Hexadecimal editor, and reintegrate everything correctly, it is a shame that the useful texts cannot be filtered to edit them more easily and that it cannot weigh more than the original file but outside of that it is great at last be able to access those.
