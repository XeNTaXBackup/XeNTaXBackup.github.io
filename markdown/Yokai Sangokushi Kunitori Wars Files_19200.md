## Post #1
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2018-12-17T07:00:29+00:00
- Post Title: Yokai Sangokushi Kunitori Wars Files

I need some help opening the BIN files found in Yokai Sangokushi Kunitori Wars, not to be mistaken with the 3DS title Yokai Sangokushi. Since it's a mobile game, Aluigi's Yokai Sangokushi BMS script doesn't work. If it's not too much to ask, would anyone tell me what kind of program can be used to open them so I can grab the artwork? Here's a sample: [link](https://www.mediafire.com/file/0fqobmlv6mq5wxi/Yokai_Sangokushi_Kunitori_Wars.zip/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-17T12:38:58+00:00
- Post Title: Yokai Sangokushi Kunitori Wars Files

You can use the following BMS commands to decrypt the file:

```
goto 0xC
get Key byte
filexor Key
get Name basename
string Name + ".dec"
log Name 0 Size
```

Still the data is compressed. Not sure about the algo..
## Post #3
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2018-12-17T15:20:46+00:00
- Post Title: Yokai Sangokushi Kunitori Wars Files

Thank you for the prompt response. Are there any programs out there that can decompress a file of this type?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-17T16:02:30+00:00
- Post Title: Yokai Sangokushi Kunitori Wars Files

> Reply from offering7866
>
> Are there any programs out there that can decompress a file of this type?
No idea. But without knowing the algorithm, there's nothing more I can do.
## Post #5
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2018-12-17T16:40:25+00:00
- Post Title: Yokai Sangokushi Kunitori Wars Files

> Reply from Bigchillghost
>
> offering7866 wrote:Are there any programs out there that can decompress a file of this type?
No idea. But without knowing the algorithm, there's nothing more I can do.
I see. Unless I need to upload more samples for analysis, it looks like we've hit a roadblock here. But still, the only clue I can think of is that the maker of this title (Level-5) has already made several Yo-kai Watch mobile games that may or may not share the same file format.
