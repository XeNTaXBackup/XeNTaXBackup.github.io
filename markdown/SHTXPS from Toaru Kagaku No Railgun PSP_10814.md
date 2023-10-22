## Post #1
- Username: Bigpet
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 25, 2013 10:08 pm
- Post datetime: 2013-09-28T06:13:14+00:00
- Post Title: SHTXPS from Toaru Kagaku No Railgun PSP

I tried to find the 3D models and stumbled across the texture file format, which I'd also like to understand

I found out that the SHTXPS headered files are images, I also found some correspondences between textures and file areas. So what I've got on them is this:




```
    int8 r;
    int8 g;
    int8 b;
    int8 a;
};
struct image{
	char unknown[1|2]; //sometimes 1, sometimes 2 no idea why
	char magic[6]="SHTXPS"
	int16 colors;
	int16 unknown;//1 in most cases, probably animation or subimage or channel
	int16 width;
	int16 height;
	har unknown[6];
	color clrtable[colors];
};
```


This is followed by 2 weird bytes (the second seems to be some weird signed int8 x-offset). After that the 9th color from the index-color table is referenced with 0x09, still investigating how it's compressed after that.

Would be really nice if you could help me with the compression part, don't know how to decipher it.


edit: here:[https://mega.co.nz/#!gpAFgZZT!fu-tUWbDg ... PQWzmHKeuU](https://mega.co.nz/#!gpAFgZZT!fu-tUWbDguPYaQsSC77eg0tsp_ViSODQzPQWzmHKeuU) is the SHTXPS file including the 0x00 buffering at the end to align the size to 2kb.

And this is the resulting image copied with glIntercept:
## Post #2
- Username: Bigpet
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 25, 2013 10:08 pm
- Post datetime: 2013-10-01T00:00:15+00:00
- Post Title: SHTXPS from Toaru Kagaku No Railgun PSP

Almost done with the first layer of compression. It's a form of run-length-encoding. If someone knows if this system has a name I'd like to know it. Anyways it's basically like this:

```
|-------|----------|--------|---------------|-----------|
|effect | lookback | repeat | is 16 bit hdr | bytecount |

```


some examples would be

passthrough: 
```
03 AA BB CC ==> AA BB CC
```


long passthrough: 
```
23 AA BB CC DD .... ==> BB CC DD ... //(copies 0x3AA bytes starting with BB)
```
 

simple repeat: 
```
40 FF ==> FF FF FF //(there's a minimum of 3 repeats, magic number added)
```
 


more examples and hopefully the final format come tomorrow, gotta go catch some sleep for now
## Post #3
- Username: Bigpet
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 25, 2013 10:08 pm
- Post datetime: 2014-09-06T23:42:54+00:00
- Post Title: SHTXPS from Toaru Kagaku No Railgun PSP

I forgot to do an end write-up of this, and there doesn't seem to be too much interest in this. But I guess I should just give you the unfinished work I did.

So this is what I made back then to decode the images

```
std::vector<char> MisakaArchive::decodeRLE(std::vector<char> buffer)
{
	const char BACK_FLAG = 0x80;
	const char REPEAT_FLAG = 0x40;
	const char LHDR_FLAG = 0x20;

	std::vector<char> result;

	int cur_src = 0;
	int cur_dst = 0;
	int cur_bck = 0;

	while (cur_src < buffer.size()){
		char src = buffer[cur_src++];
		int amt = 0;

		if (src & BACK_FLAG){
			amt = (src & 0x60) >> 5;
			amt += 4;
			cur_bck = (src & 0x1F) << 8 | reinterpret_cast<unsigned char &>(buffer[cur_src++]);
			assert(cur_bck>0);
			cur_bck = cur_dst - cur_bck;
			int subcopy = amt;
			while (cur_dst - cur_bck < subcopy){
				int subcopy_amt = (cur_dst - cur_bck);
				copy_data(result, result, cur_dst, cur_bck, subcopy_amt);
				subcopy -= subcopy_amt;
				cur_bck += subcopy_amt;
				cur_dst += subcopy_amt;
			}
			copy_data(result, result, cur_dst, cur_bck, subcopy);

			cur_bck += subcopy;
			cur_dst += subcopy;
		}
		else if ((src & 0xE0) == 0x60)
		{
			amt = src & 0x1F;
			amt += 4;
			assert(cur_dst > cur_bck);
			int subcopy = amt;
			while (cur_dst - cur_bck < subcopy){
				int subcopy_amt = (cur_dst - cur_bck);
				copy_data(result, result, cur_dst, cur_bck, subcopy_amt);
				subcopy -= subcopy_amt;
				cur_bck += subcopy_amt;
				cur_dst += subcopy_amt;
			}
			copy_data(result, result, cur_dst, cur_bck, subcopy);

			cur_bck += subcopy;
			cur_dst += subcopy;
		}
		else if (src & REPEAT_FLAG){
			amt = (src & 0x10) ? (src & 0x0F) << 8 | reinterpret_cast<unsigned char &>(buffer[cur_src++]) : src & 0x1F;
			amt += 4;
			result.insert(result.begin() + cur_dst, amt, buffer[cur_src++]);
			cur_dst += amt;
		}
		else if (src & LHDR_FLAG){
			amt = ((src & 0x1F) << 8) | reinterpret_cast<unsigned char &>(buffer[cur_src++]);
			copy_data(result, buffer, cur_dst, cur_src, amt);
			cur_src += amt;
			cur_dst += amt;
		}
		else if (src == 0x00){
			break;
		}
		else
		{
			amt = src & 0x1F;
			copy_data(result, buffer, cur_dst, cur_src, amt);
			cur_src += amt;
			cur_dst += amt;
		}

	}
	return result;
}

```


This has still some bugs in it but you can find this and the actually working hackishly direct MIPS ASM to C++ translation here: [https://github.com/Bigpet/KatagawaBinParser](https://github.com/Bigpet/KatagawaBinParser)
