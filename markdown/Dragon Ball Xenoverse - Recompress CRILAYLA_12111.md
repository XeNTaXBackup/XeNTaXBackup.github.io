## Post #1
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-14T15:48:13+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

I want to mod this game but I am having trouble repacking the all thing! 
There is no way I can find a way to repack everything in one go, but I am trying to at least split this into parts so I can mod it properly! 

[https://www.mediafire.com/?qpuax73gueib9iz](https://www.mediafire.com/?qpuax73gueib9iz)

This small cpk file works as an example of the format of this file!
There are many ways to unpack this...cpk_unpack, noesis, or even some specific "programs" for this kind of file like the one writen by the user "tpu" at this thread [viewtopic.php?f=21&t=5137&p=44220&hilit=CRILAYLA#p44220](http://forum.xentax.com/viewtopic.php?f=21&t=5137&p=44220&hilit=CRILAYLA#p44220)

As far as I could understand the headers of this file are encrypted with a simple XOR encryption and are easy to decrypt/encrypt! The problem is about the contents! They look to be compressed in something called CRILAYLA (see for example @offset 0x2800) 

The compressed and uncompressed size are easy to spot, the header is also on the end of the file (size = 0x100) the problem is the rest, I simply can't find the compression algorithm! I've looked everywhere, even at quickbms but I can't seem to find it!

Now! On that thread, user "tpu" managed to write a decompression algorithm for it 

```
    CRI layla decompress
	writen by tpu
*/

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef unsigned char u8;
typedef unsigned short u16;
typedef unsigned int u32;


u8 *sbuf;
u32 bitcnt;
u32 bitdat;
int z = 0;

u32 get_bits(u32 n)
{
	u32 data, mask;

    if (bitcnt<n){
	  data = ((24-bitcnt)>>3)+1;
	  bitcnt += data*8;
      while(data) {
		bitdat = (bitdat<<8) | (*sbuf--);
		data--;
      }
    }

	data = bitdat>>(bitcnt-n);
	bitcnt -= n;
	mask = (1<<n)-1;
	data &= mask;
	return data;
}

u32 llcp_dec(u8 *src, u32 src_len, u8 *dst, u32 dst_len)
{
	u8 *dbuf, *pbuf;
	u32 plen, poffset, byte;

	sbuf = src+src_len-1;
	dbuf = dst+dst_len-1;
	bitcnt = 0;

	while(1){
		if(get_bits(1)==0){
			byte = get_bits(8);
			*dbuf-- = byte;
			if((dbuf+1)==dst)
				goto _done;
		}else{
			poffset = get_bits(13);

			plen = get_bits(2);
			if(plen==3){
				plen += get_bits(3);
				if(plen==10){
					plen += get_bits(5);
					if(plen==41){
						do{
							byte = get_bits(8);
							plen += byte;
						}while(byte==255);
					}
				}
			}

			pbuf = dbuf+poffset+3;
			plen += 3;

			while(plen) {
				byte = *pbuf--;
				*dbuf-- = byte;
				plen--;
				if((dbuf+1)==dst)
					goto _done;
			}

		}
	}

_done:
	return (u32)(dst+dst_len-dbuf-1);
}


u32 layla_decomp(u8 *src, u32 src_len, u8 *dst, u32 dst_len)
{
	u8 tbuf[256];
	u32 decomp_size;
	u32 comp_size;

	decomp_size = *(u32*)(src+8);
	comp_size = *(u32*)(src+12);

	memcpy(tbuf, (src+src_len-256), 256);

	decomp_size = llcp_dec(src+0x10, comp_size, dst+256, decomp_size);

	memcpy(dst, tbuf, 256);

	return decomp_size+256;
}


/* test */
//#if 0

int main(int argc, char *argv[])
{
	FILE *ifp, *ofp;
	u8 *ibuf;
	u32 fsize;

	ifp = fopen(argv[1], "rb");
	fseek(ifp, 0, SEEK_END);
	fsize = ftell(ifp);
	fseek(ifp, 0, SEEK_SET);

	ibuf = malloc(16*1024*1024);
	fread(ibuf, fsize, 1, ifp);
	fclose(ifp);

	fsize = layla_decomp(ibuf, fsize, ibuf, 0);

	ofp = fopen(argv[2], "wb");
	fwrite(ibuf, fsize, 1, ofp);
	fclose(ofp);

	return 0;
}

//#endif
```


I tried to reverse this algorythm from a decompress algorithm to a recompress one, but my knowledge of low level languages is very limited and I struggle with this bit shift thingies :S

I'm begging you  Can some one give me a hand here and write a compress algorithm for this! Or if there's a better way to repack everything from this cpk after it has been unpacked and have it work, could you tell me??
Thank you
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-17T13:41:51+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

> Reply from Dakilla
>
> Or if there's a better way to repack everything from this cpk [..]??
Thank you
Did you take into account to use quickbms' reimport feature?

I decrypted data_patch.cpk (cpk header and TOC) then qbms can extract all files:

```
--------------------------------------
  00002800 38384      data/chara/CMN/CMN.bai
  00004000 10316      data/event/lobby/lobby_event_manage_beta.tsd
  00005000 7396       data/event/lobby/lobby_npc_list.tnl
[...]
  0017a800 16592      data/ui/sprite/BETATESTICON.emb
  0017c000 352        data/ui/sprite/BETATESTICON.ems
  0017c800 16592      data/ui/sprite/BETATESTICON_en.emb

- 104 files found in 0 seconds
```


So trying to repack them using qbms might be worth a try.
Restriction(s): 
"- you CANNOT increase the size of the files you want to reimport, so
  the new files must be minor or equal than the originals"

edit: well, doesn't seem to work. I changed one file, started quickbms like this:
quickbms -w -r cpk.bms data_patch_decr.cpk data
but it says "0 files reimported".

So I guess we've hit this restriction:
"if an algorithm is  not available in recompress mode the reimporting will fail"
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-17T14:53:08+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

You could always repack the archive uncompressed.
## Post #4
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-18T15:56:36+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

> Reply from shakotay2
>
> Dakilla wrote:Or if there's a better way to repack everything from this cpk [..]??
Thank you 
Did you take into account to use quickbms' reimport feature?

I decrypted data_patch.cpk (cpk header and TOC) then qbms can extract all files:
Code: Select all  offset   filesize   filename
--------------------------------------
  00002800 38384      data/chara/CMN/CMN.bai
  00004000 10316      data/event/lobby/lobby_event_manage_beta.tsd
  00005000 7396       data/event/lobby/lobby_npc_list.tnl
[...]
  0017a800 16592      data/ui/sprite/BETATESTICON.emb
  0017c000 352        data/ui/sprite/BETATESTICON.ems
  0017c800 16592      data/ui/sprite/BETATESTICON_en.emb

- 104 files found in 0 seconds

So trying to repack them using qbms might be worth a try.
Restriction(s): 
"- you CANNOT increase the size of the files you want to reimport, so
  the new files must be minor or equal than the originals"

edit: well, doesn't seem to work. I changed one file, started quickbms like this:
quickbms -w -r cpk.bms data_patch_decr.cpk data
but it says "0 files reimported".

So I guess we've hit this restriction:
"if an algorithm is  not available in recompress mode the reimporting will fail"

That's the problem with quickbms...there is no recompress algorithm :S
Also, I couldn't find the uncompress one too, to be honest...  

> Reply from chrrox
>
> You could always repack the archive compressed.

you mean "uncompressed"? cause if you're saying compressed that doesn't work since I want to edit the files!
Modding a compressed file is pretty much impossible! That's why I want to decompress, edit then recompress on with the correct format :S

I cannot properly read that code that guy wrote... but I believe the answer is there, if anyone can understand the uncompress algorithm, then it should be possible to reverse engeneer it to a compressing algorithm...
But I'm not that good  As I said, I kinda suck with low level coding ehe

That's why I'm asking if anyone can look at that and understand it
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-18T20:44:16+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

I did mean uncompressed. there is an sdk tool leaked that can create the archives for you uncompressed that should work.
I can not link it here its against the rules.
## Post #6
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-18T21:04:56+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

> Reply from chrrox
>
> I did mean uncompressed. there is an sdk tool leaked that can create the archives for you uncompressed that should work.
I can not link it here its against the rules.

Hmm... I don't know if that will work considering I have to encrypt back to .edat

But since it might I will try! I understand that you can't post a link, but can you name the tool so I can do a proper google search 

I'll search anyway but just to make my life easier in case I can't find it 

Thanks
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-10-19T10:56:02+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

> Reply from Dakilla
>
> chrrox wrote:I did mean uncompressed. there is an sdk tool leaked that can create the archives for you uncompressed that should work.
I can not link it here its against the rules.

Hmm... I don't know if that will work considering I have to encrypt back to .edat

But since it might I will try! I understand that you can't post a link, but can you name the tool so I can do a proper google search 

I'll search anyway but just to make my life easier in case I can't find it 

Thanks
Whether or not it has to be encrypted back to .edat has nothing to do with packing the archive back uncompressed and would not affect encryption to .edat since it's essentially the same file just encrypted with some dumb algorithm with a key. I don't know how the game structures work but by the sounds of it there must be a flag specifying whether the archive data is compressed or not. So rather than wasting time compressing everything, you're best off just leaving it uncompressed. Your best shot is finding those tools then.
## Post #8
- Username: Dakilla
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-19T12:21:17+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

you can encrypt anything back to edat.

CRI PACKED FILE MAKER 1.3
## Post #9
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-20T21:36:30+00:00
- Post Title: Dragon Ball Xenoverse - Recompress CRILAYLA

> Reply from chrrox
>
> you can encrypt anything back to edat.

CRI PACKED FILE MAKER 1.3

I'm totally lost, I tried everything that I could think of!

(btw...I tried that tool before opening this thread, I just didn't realized it  anyways I tried it again)

So here's what I have done! 
First I got that CPK into "CRI middleware Toolpack v1.0 by Falo" Just to get information about it, like data alignment and such!
Here's the result : 

```
ContentOffset: 10240
ContentSize: 1552384
TocOffset: 2048
TocSize: 5320
ItocOffset: 8192
ItocSize: 928
EnabledPackedSize: 16253056
EnabledDataSize: 9569572
Files: 104
Groups: 0
Attrs: 0
Version: 7
Revision: 1
Align: 2048
Sorted: 1
EID: 1
CpkMode: 2
Tvers: CPKMC2.30.07, DLL3.00.07
Codec: 0
DpkItoc: 0

```


Note here that no matter what configurations I chose on the CRI tool you suggested the version "TVers" is always different
then that! But ignoring that I repacked with the following Settings :



- For the Data Align I chose 2048 because of the result of "Falo"'s tool
- I chose Filename for "File Mode" because I know that cpk contains the file names, so it's either "Filename" or 
"ID+Filename" ( I tried both with the same result)
- No Compression because of what you suggested
- And "Mask Headers" Selected because that CPK has the headers masked!

And this is the result cpk 

[https://www.mediafire.com/?99m57qxwm64wbm7](https://www.mediafire.com/?99m57qxwm64wbm7)

You can clearly see that the TOC,ITOC and ETOC tables are in the end of the file instead of the begining like the original cpk! But that shouldn't be a problem, I'm assuming, because the offsets are all specified on the initial header!

Now when I try to get this file in the game it just get's me to a black screen! No error nor loading nor nothing!
What do you think I'm doing wrong here? Do you have any suggestions??

I'm out of ideas, I also experimented with a good chunck of other settings and the result is always the same!
