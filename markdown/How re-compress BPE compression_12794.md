## Post #1
- Username: Futballo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 12:42 am
- Post datetime: 2015-04-24T01:54:34+00:00
- Post Title: How re-compress BPE compression?

I have these texture files which are compressed in an unknown format. I've ask a few people, but all of them couldn't identify what kind of compression was used for these textures. Most said it is a custom format.

I managed to get the uncompressed file through extracting from CheatEngine.

The compressed file here:

[https://www.dropbox.com/s/kw6anb3pulxgv ... 9.unk?dl=0](https://www.dropbox.com/s/kw6anb3pulxgvic/f%28771%29.unk?dl=0)

The uncompressed file here:

[https://www.dropbox.com/s/rzllgazc86ssc ... d.bin?dl=0](https://www.dropbox.com/s/rzllgazc86ssc2y/771%20uncompressed.bin?dl=0)

The file it's an image of 256colors 256 width and 512 height.

Hope someone knows what kind of compression these files are on   .

------------------------------------------------
Thanks to Barti it was found it that the files use BPE compression. Now, the only big question that remains is
How to re-compress the file back to BPE in order to allow editing?
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-24T16:25:31+00:00
- Post Title: How re-compress BPE compression?

It's BPE (byte pair encoding).

QuickBMS script:

```
string NAME += "_unpacked.dat"
comtype bpe

get SIZE long
get ZSIZE long

clog NAME 8 ZSIZE SIZE
```
## Post #3
- Username: Futballo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 12:42 am
- Post datetime: 2015-04-24T16:31:01+00:00
- Post Title: How re-compress BPE compression?

Is that it? ohh wow, amazing

Although, I'm sorry for my ignorance but how would I go using that QuickBMS script?
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-24T16:37:24+00:00
- Post Title: How re-compress BPE compression?

Copy it to a text file, then get QuickBMS [here](http://aluigi.altervista.org/quickbms.htm). Open QuickBMS, it will ask you to select the script, then the input file, and then output folder.
## Post #5
- Username: Futballo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 12:42 am
- Post datetime: 2015-04-24T16:45:14+00:00
- Post Title: How re-compress BPE compression?

Awesome, it decompress the file.

But, how could I compress it back after I'm done editing?

This is great
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-24T20:27:22+00:00
- Post Title: How re-compress BPE compression?

Unfortunately QuickBMS doesn't have a recompress algorithm for bpe as far as I know. But you can ask aluigi on [ZenHAX](http://zenhax.com/) about it - he often responds there.
## Post #7
- Username: Futballo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 12:42 am
- Post datetime: 2015-04-24T20:35:28+00:00
- Post Title: How re-compress BPE compression?

That's very unfortunate
