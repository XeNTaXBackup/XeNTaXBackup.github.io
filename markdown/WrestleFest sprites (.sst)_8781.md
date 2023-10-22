## Post #1
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2012-04-17T02:41:06+00:00
- Post Title: WrestleFest sprites (.sst?)

wrestler.rar
(96.91 KiB) Downloaded 38 times



I've done extensive google searching and tried many of programs but cannot seem to get WrestleFest's wrestler sprite files (I think that's what they are) to open. Modding wrestlers would be the best thing to do with this game. Wrestlers are stored in a file called wrestler.zip, and inside are the .sst animations for everything. Can someone take a look at these? I've attached the files for the Atomic Drop in the archive. Thanks.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T18:03:42+00:00
- Post Title: WrestleFest sprites (.sst?)

looks like a standard 8-bit format; there is probably a separate color table though... the color table itself uses indices. i'll check to see if i can get a bitmap view of one of your files right now.

look like format is:

4-bytes magic
2-bytes version?
2-bytes color table type?
4-bytes width
4-bytes height
2-bytes ??
2-bytes ??
color table indices
image data
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T18:32:41+00:00
- Post Title: WrestleFest sprites (.sst?)

This is what I got out of it. Don't know what the color index trick is... would have to have a lossless screen capture sample in full color of the image below (if you own the game, send it via PM to those who are interested as we have new rules regarding posting samples to copyrighted game data).


```
{
 using namespace std;
 ifstream ifile("atomicdrop.sst", ios::binary);

 auto p01 = LE_read_uint32(ifile);
 auto p02 = LE_read_uint16(ifile);
 auto p03 = LE_read_uint16(ifile);
 auto p04 = LE_read_uint32(ifile);
 auto p05 = LE_read_uint32(ifile);
 auto p06 = LE_read_uint16(ifile);
 auto p07 = LE_read_uint16(ifile);

 boost::shared_array<uint08> table(new uint08[256]);
 ifile.read((char*)table.get(), 256);

 uint32 size = p04*p05;
 boost::shared_array<uint08> data(new uint08[size]);
 ifile.read((char*)data.get(), size);

 uint32 dx = p04;
 uint32 dy = p05;
 uint32 bpp = 8;
 uint32 pitch_bytes = ((bpp*dx + 31) & ~(31))/8;
 uint32 total_bytes = pitch_bytes*dy;

 boost::shared_array<uint08> bmpdata(new uint08[total_bytes]);
 for(uint32 y = 0; y < dy; y++)
    {
     for(uint32 x = 0; x < dx; x++)
        {
         uint32 src_index = y*dx + x;
         uint32 dst_index = y*pitch_bytes + x;
         bmpdata[dst_index] = data[src_index];
        }
    }

 BITMAPFILEHEADER fh;
 fh.bfType = 0x4D42;
 fh.bfSize = 0;
 fh.bfReserved1 = 0;
 fh.bfReserved2 = 0;
 fh.bfOffBits = 0;

 BITMAPINFOHEADER ih;
 ih.biSize = sizeof(BITMAPINFOHEADER);
 ih.biWidth = p04;
 ih.biHeight = p05;
 ih.biPlanes = 1;
 ih.biBitCount = (WORD)8;
 ih.biCompression = BI_RGB;
 ih.biSizeImage = 0;
 ih.biXPelsPerMeter = 0;
 ih.biYPelsPerMeter = 0;
 ih.biClrUsed = 0;
 ih.biClrImportant = 0;

 ofstream ofile("output.bmp", ios::binary);
 ofile.write((char*)&fh, sizeof(fh));
 ofile.write((char*)&ih, sizeof(ih));

 for(uint32 i = 0; i < 256; i++) {
     ofile.write((char*)&table[i], 1);
     ofile.write((char*)&table[i], 1);
     ofile.write((char*)&table[i], 1);
     char alpha = 0;
     ofile.write((char*)&alpha, 1);
    }

 ofile.write((char*)bmpdata.get(), total_bytes);
}

```
## Post #4
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2012-04-17T20:43:19+00:00
- Post Title: WrestleFest sprites (.sst?)

Great work so far. I've sent you a PM, hopefully we'll get to the bottom of this.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-19T01:34:47+00:00
- Post Title: WrestleFest sprites (.sst?)

Well, since I don't have an iphone, and the game isn't available on android yet, I probably can't do much from here. All you gotta do though is just figure out how the color table is encoded (i have a feeling they are hardcoded).
## Post #6
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2012-04-19T23:52:23+00:00
- Post Title: WrestleFest sprites (.sst?)

Oh that's alright. I guess you can try once it's out on Android and PC. I can wait, although if anyone else wants to try...they can
## Post #7
- Username: NBAPJ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 17, 2021 10:31 pm
- Post datetime: 2021-04-17T14:34:10+00:00
- Post Title: WrestleFest sprites (.sst?)

Hi did anyone ever figure out how to get the sprites from this game?
