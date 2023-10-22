## Post #1
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2015-05-14T20:35:03+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

I'm trying to extract the 3D Models from the Godzilla game for PS3, which at the moment is only released in Japan. The game contains .pac files which can easily be extracted, but all of the files appear to be LZS compressed. The game apparently uses the PhyreEngine, if that information can be of any help.

Here's a link to all of the files I've extracted from ch01a_00.pac: [http://www.mediafire.com/download/g1qd2 ... 282%29.rar](http://www.mediafire.com/download/g1qd2z7zhmhshc8/Godzilla%282%29.rar)

Any help decompressing these files would be appreciated!
## Post #2
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-08-04T02:27:20+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

Just wanted to bump this one to see if you, or anyone else had managed to get anywhere with this. The models in this game look fantastic!
## Post #3
- Username: Xasoduste
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 17, 2015 7:26 pm
- Post datetime: 2015-09-17T11:36:51+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

It is not strange, yet it would have been talking about for a long time.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-29T04:24:51+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

it looks like aluigi's lzs bms script should decompress your samples but it goes off track somewhere  
[http://aluigi.altervista.org/bms/lzs.bms](http://aluigi.altervista.org/bms/lzs.bms)

*edit*
thanks to daemon1 for posting the source code that revealed the 
byte swap so aluigi could fix the script to decompress properly  

```
# script for QuickBMS http://quickbms.aluigi.org

quickbmsver "0.5.25"
idstring "LZS\0"
getdstring DUMMY 4
get OFFSET long
if OFFSET u> 0x10000
	endian big
	reverselong OFFSET
endif
get DICT_OFFSET long
get SIZE long
get ZSIZE long
getdstring DUMMY 8
get NAME string
goto DICT_OFFSET
math DICT_SIZE = ZSIZE
math DICT_SIZE -= DICT_OFFSET
getdstring DICT DICT_SIZE
comtype LZS_UNZIP DICT DICT_SIZE
math ZSIZE = DICT_OFFSET
math ZSIZE -= OFFSET
encryption swap 16                  #this line was the fix
clog NAME OFFSET ZSIZE SIZE
```
## Post #5
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-11-29T16:23:00+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

Would love to know what it is -- this game has EASILY the best and broadest selection of Godzilla models to date!
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-14T16:56:22+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

Unpacked the files. Now getting models


textures


and skeletons
## Post #7
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-12-14T20:53:09+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

Hey there! Would someone be able to perhaps take a look into these .pac files? Looking for a way to get at the assets inside... It appears to be using a different compression method to the NTSC version of the game, which I find interesting!

[https://mega.nz/#F!nZ4V0TqC!sKjWNJu1VTrpkowRTa288Q](https://mega.nz/#F!nZ4V0TqC!sKjWNJu1VTrpkowRTa288Q)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-14T22:49:18+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

> Reply from daemon1
>
> Unpacked the files....
what was the solution to the lzs compression so aluigi can fix his script
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-15T15:39:29+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

> Reply from AceWell
>
> what was the solution to the lzs compression so aluigi can fix his script

This is what I did:

I took the quickbms LZS code, and rewritten it looking at the file data. It was all done correct, as luigi's code describes. So I don't know why script is not working, maybe some endianess issue.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-15T16:07:53+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

i guess the byte order could be the problem here since the script follows the file structure
perfectly and ps3 files sometimes has big endian headers with little endian data
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-15T16:36:39+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

meanwhile i found bone remaps and it seems it all work ok
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-15T21:06:09+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

> Compressed files and methods
> Godzilla PS3 LZS Compressed Files
> all of the files appear to be LZS compressed....Any help decompressing these files would be appreciated!

i've spent more time than i care to admit trying to figure out why the bms script didn't work, which is why i am curious
about this elusive solution you have figured out, so to avoid spinning our tires further here i'll just go ahead and ask - 

how did you decompress the files properly and can you post your code associated with this lzs decompression? 

forget about the bms script, i'm asking how you solved the decompression, i'm sure it wasn't accidental.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-16T04:50:09+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

sure i will post the code as soon as i get back home this evening
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-16T15:57:04+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

ok this is the code. First reading the header:

```
            int dataoff = br.ReadInt32();
            int dictoff = br.ReadInt32();
            int usize = br.ReadInt32();
            int psize = br.ReadInt32();


```

then reading the whole data block into memory:

```
            fs.Seek(dataoff, SeekOrigin.Begin);
            int[] data = new int[datasize + 16];
            int tmp, flags;
            for (int i = 0; i < datasize; i++)
            {
                tmp = br.ReadByte();
                data[i] = (tmp << 8) + br.ReadByte();
            }

```

and then decompressing it according to Luigi's code. Note that I was too lazy to make any checks present in his code.

```
            byte[] outb = new byte[usize + 16];
            int outs = 0;
            int roff, rsize;

            for (int i = 0; i < datasize; i++)
            {
                flags = data[i];
                for (int j = 0; j < 16; j++)
                {
                    if (((flags >> j) & 1) > 0)
                    {
                        // copy byte from dictionary
                        outb[outs++] = br.ReadByte();
                    }
                    else
                    {
                        // repeat already unpacked bytes
                        rsize = (data[i + 1] & 0x1f) + 2;
                        roff = (data[i + 1] >> 5);
                        for (int k = 0; k < rsize; k++, outs++) outb[outs] = outb[outs - roff];
                        i++;
                    }
                }
            }

```

in the end write output to file

```
            File.WriteAllBytes("out.bin", outb);
```


As you can see, this code does exactly the same what LZS code from quickbmx does.
## Post #15
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2016-12-18T07:23:53+00:00
- Post Title: Godzilla PS3 LZS Compressed Files

Woah, that's awesome! Thanks a lot! 

EDIT: How did you get the model itself? Should I try to extract it with Hex2Obj or is there an easier way to do it?
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-18T08:10:00+00:00
- Post Title: Re: Godzilla PS3 LZS Compressed Files

The convertor is almost ready. Testing now. All monsters work, except one. I need to fix him.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-18T14:31:26+00:00
- Post Title: Re: Godzilla PS3 LZS Compressed Files

Model tool released:

[viewtopic.php?f=16&t=16930](http://forum.xentax.com/viewtopic.php?f=16&t=16930)
## Post #18
- Username: Darwin45
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 25, 2018 8:01 am
- Post datetime: 2018-10-25T00:12:28+00:00
- Post Title: Re: Godzilla PS3 LZS Compressed Files

So what happened to this forum non of this information of decompressing lzs compression dae file work on Quickbms 
can someone please explain this I'm new here and I would very like to rip the environment from this Godzilla game.
