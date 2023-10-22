## Post #1
- Username: Raik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2015 7:51 am
- Post datetime: 2016-10-11T21:44:43+00:00
- Post Title: swf ram adpcm Codename Gordon

Hello

I need some help with some swf adpcm files i found in the game "Codename Gordon" Most adpcm tracks can be decoded with the converter adpcm_swf2raw:
[https://github.com/alexgirao/adpcm_swf](https://github.com/alexgirao/adpcm_swf)

But the bigger adpcm files are not working. I get an error: 

adpcm_swf2raw.c:302: input size=1075828
adpcm_swf2raw.c:303: first byte=0xfffffffc
adpcm_swf2raw.c:327: adpcm_code_size=3
adpcm_swf2raw.c:337: bits_per_code=5
adpcm_swf2raw.c:1181: wip

the problem inside the adpcm_swf2raw.c:

					 if (in >= last) break;
					 int i2 = *(unsigned char*)in++;
					 int s3 = ((i1 & 1) << 4) | (i2 >> 4);
					*outputp++ = adpcm_decode5bit(s3, state);
					 count++;
					 sample_number++;
					if (count == 4095) {
						DEBUG("wip"); exit(1);
						break;

I am not sure why. I have uploaded a few samples: [https://www.sendspace.com/file/znizx9](https://www.sendspace.com/file/znizx9)

Would be great to have a working converter or a workaround code for adpcm_swf2raw. There are many flash games out which using this adpcm variant as codec and it would be great if we could decode all versions of this codec.

thx for any help
