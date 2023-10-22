## Post #1
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-01-16T18:18:34+00:00
- Post Title: Legend Of Immortal (gamebryo engine)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-16T19:22:32+00:00
- Post Title: Legend Of Immortal (gamebryo engine)

Looks like a good game.
Nothing seems useful from that file so maybe there is a file index somewhere else.
## Post #3
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2012-01-17T15:26:41+00:00
- Post Title: Legend Of Immortal (gamebryo engine)

> i don't know what is the engine verson it usesit is a mix of 20.6.0.0, 20.2.0.7 and maybe other versions of engine. so your pack is pack of textures (all files starts with "1XET" id), no nifs inside it.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-17T17:14:31+00:00
- Post Title: Legend Of Immortal (gamebryo engine)

It might also be a custom format, or at least, whatever that 20.6.0.0b is supposed to be (beta? lol)

There are just 31 wpf files all with a similar structure (all named the same way. data0.wpf, data1.wpf, ..., data30.wpf)

Another thing to notice is that for example, data0.wpf has a bunch of filenames (7586 of them to be exact) with xml extension, but the data contains absolutely no xml mark-up at all. Maybe it's compressed? Well, I opened a random archive and there I see a bunch of xml data, but then when I looked at the filenames it was a bunch of nif and kf...............

On the other hand, there are xml's in other data files, except their filenames don't include any xml's.
So it's possible that the archives are indexing into other archives to get the data.

For anyone that's interested, data2.wpf (546 MB) contains a  bunch of xml data. 

The header is kind of odd cause you read it once, and then it repeats itself exactly.

```
dword
dword tableOfs?
dword 0
dword 1
dword tableOfs + 8
dword 0
dword 4
dword FILES
dword
dword
dword[5] nulls

```


Assuming the filetable starts at tableOfs, it looks like it stores all of the entries (4 ints each), and then followed by all of the filenames.

Most of the values in the header don't change, so any indexing might occur in the filetable at the bottom.

I would expect that in order for someone who isn't as experienced with archives to figure out this format, they'd need at least another archive that is referenced. But the game is 4 GB and most of the data files are massive lol

I looked a little closer at the filenames and I see this:

```
dword some integer
dword null

```


The first name is always a folder. So there's some directory structure. That integer might be the sublevel, don't know.

The entry for each file is like

```
int could_be_massive
int slowly_increasing
int varies

```


I thought maybe it was compressed, but seeing all that xml data and nif data makes me think otherwise.
And those two ints that could be massive...don't seem to have any real pattern. And those slowly increasing ints are literally just increasing by 8, or sometimes 12, or 20, or 40 at a time.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-31T16:39:25+00:00
- Post Title: Legend Of Immortal (gamebryo engine)

Bump.

I might just manually copy out some nif files cause it's not encrypted/compressed until someone figures out how the archives are referring to each other.

In fact I don't know how large a single file is so I don't know which value might be the size.

Here some eye candy
