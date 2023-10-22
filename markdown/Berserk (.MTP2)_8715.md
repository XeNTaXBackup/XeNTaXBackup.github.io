## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-08T03:35:11+00:00
- Post Title: Berserk (*.MTP2)

I'm trying to extract texture data from the mtp2 files, but I'm having a hard time extracting the individual texture data from the archive or texture package.
seems my offset and size calculations are wrong, and I don't know where to start on how to analyze the texture data


Here's are my structures
mtp_header { // 16bytes
byte[4] magic, "MTP2 "
byte[4] buffer offset
byte[4] buffer size
byte[2] unknown, always 1
byte[2] count
}

texture_entry { // 68bytes
byte[4] offset * 0x0100
byte[4] unknown, always 0x02
byte[2] compression??, usually 0x13 or 0x14
byte[2] unknown, usually 0x00
byte[4] unknown, value seems progressive
byte[12] padding? all 0's
byte[2] texture height
byte[2] texture width
byte[4] size * 0x0100
byte[16] padding? all 0's
string[16] texture name
}


In the samples I've included some textures dumped from the PS2 emu. may help to decipher the texture data


 ps2_mtp_files.zip
[PS2] Berserk MTP2 Samples (217.66 KiB) Downloaded 51 times
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-10T10:59:04+00:00
- Post Title: Berserk (*.MTP2)

I'm interested in converting mtp2&mpt3, too.
I searched forum but didn't find much.
Here's a sample mtp3 file from PS2 Soukou Kihei Votoms and Gundam Meisters.
[http://www.mediafire.com/?ou65odp8q6z5t47](http://www.mediafire.com/?ou65odp8q6z5t47)
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-12T03:59:12+00:00
- Post Title: Berserk (*.MTP2)

I was able to verify that my offset calculation works.. or well got lucky lol

I wrote 0's on the suppose of face texture... and indeed the models face turned black.

I then tried to write 0's to find out the bits per pixel, and to figure what sort of palette data I was dealing with.

I concluded that the format is on par with DXT, having a 8bpp size ratio. however I'm unable to determine palette...

for now I read the 8bits as my RGB, and converted it as is. I got a grey scale image, however it would seem to be swizzled....



my attempted sorta failed  but seems I'm close to figuring out the pixel order
