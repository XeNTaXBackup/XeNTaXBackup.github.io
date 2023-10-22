## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-02T22:42:35+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

Hey Guys,

me and five friends of mine want to translate the Game "300 Heroes" (fake League of Legends clone from China) to english Language.

Right now, we're able to extract all files from the data.jmp (519MB ~ ).
We're already changed all texts from the image-files from chinese to english.

We opened it in "Excel" (works with notepad++, too) to "read" it.
It looks like this:



We opened the same file in hex-editor, but it looks like this (because of chinese letters)


We know that we can't replace the chinese signs with letters in notepad++, it will destroy the file, that's the reason why we want to "decompress/decrypt" it to modify this file like we want (add stuff, replace stuff).

Would be cool if you can help us with this, this would be the first English translation for this game! 

Here's the file to check it.
[string_client_c.rar](https://xentaxbackup.github.io/file/8586_string_client_c.rar)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-02-03T00:40:25+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

fairly straightforward, except the string sizes - which are bit swizzled!


edit 
decoded the length swizzling   

```
//--- 010 Editor v5.0 Binary Template
// v2 - completely parsed!
//--------------------------------------

#include "prelen.bt"

local uint p;

struct varbyte
{
    local uint len = 2;

    ubyte marker_begin;
    Assert(marker_begin == 0xa);
    ubyte size;
    ubyte unknown; // or marker_end
    if( unknown != 0xa )
    {
        //len = 3;
        ubyte marker_end;
    }
};

struct entry
{
    varbyte entry_size;

//    if( entry_size.unknown != 0xa )
//    {
//        Printf("%u and %u\n", entry_size.size, entry_size.len);
//    }

    str name(plen8);

    // this condition is wrong!!
    // todo: decode the size (same routine as below?)
    if( (entry_size.size - name.len - entry_size.len) > 0 )
    {
        ubyte hint;
        Assert(hint == 0x12);

        ubyte val_size;

        local uint real_len = ReadUByte(FTell());
    
        // general logic (10 picked because samples goes up to 9)
        if( real_len < 10 )
        {
            ubyte _lenhint;
            real_len = val_size;

            // bit swizzling logic:

            if( (_lenhint & 1) == 0 )
                real_len ^= 0x80;

            real_len |= (_lenhint >> 1) * 0x100;
        }
        else
        {
            real_len = val_size;
        }
        
        str val(real_len);
    }
};

while( !FEof() )
{
  entry e;
};

```
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-03T08:10:08+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

Nice 
One Question, how can I decrypt and re-encrypt the file with this? 

EDIT:
I see that I can find all values now in Template Results.
But is ist possible to add new Entrys or edit entrys with more characters than the original one?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-02-03T23:16:04+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

hey - i didn't think i'd have time to, but i'm writing a tool   

source: [https://github.com/x1nixmzeng/300HLoc](https://github.com/x1nixmzeng/300HLoc)

can you test the attached file please! i want to know if the game can handle slightly different flags

edit
removed file
## Post #5
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-04T08:42:37+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

> Reply from WRS
>
> hey - i didn't think i'd have time to, but i'm writing a tool   

source: https://github.com/x1nixmzeng/300HLoc

can you test the attached file please! i want to know if the game can handle slightly different flags

It seems that the Game can't handle it.
It does not load anything from this file anymore.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-02-04T23:39:54+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

> Reply from ChrisX930
>
> It seems that the Game can't handle it.
It does not load anything from this file anymore.

nevermind. i've finished the tool   
it requires the .net 4.5 runtime

very easy to use, here we go:

to get the strings into a text file:

```
300HLoc.exe string_client_c.dat strings.txt
```


to convert back

```
300HLoc.exe strings.txt string_client_c.dat
```


note: strings with extra lines have been replaced with <NEWLINE> - do not translate that 

enjoy ! and post a link or pm me when you translate the game to english  
[300HLoc.zip](https://xentaxbackup.github.io/file/8603_300HLoc.zip)
## Post #7
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-05T16:29:07+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

IT WOOOOORKS! O.O
THANK YOU! 

One moe thing, that need to be decrypted, after this, We're able to edit all language-Parts in this game *-*
Could you help us to decrypt this file, too? (I've edited it already in Hex, so you should be able to see some names there :3
it would be AWESOME if you could help us to decrypt this file, too :3


EDIT: Btw. here are some screenshots to show that it works 
IMAGE
[item_item_lan_c.rar](https://xentaxbackup.github.io/file/8610_item_item_lan_c.rar)
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-02-07T18:35:05+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

here you go
[300HLoc-v0.2.zip](https://xentaxbackup.github.io/file/8623_300HLoc-v0.2.zip)
## Post #9
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-02-07T20:28:10+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

> Reply from WRS
>
> here you go
It works *-*
Thank you very much
## Post #10
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2015-02-18T01:00:37+00:00
- Post Title: 300Heroes - dat-file decrypt/decompress? We want to trans it

You know i was about to post a project to do the same thing as you doo, i'm glad this is happening, i really like the game, too bad it has so much ping.

thanks a lot for this
