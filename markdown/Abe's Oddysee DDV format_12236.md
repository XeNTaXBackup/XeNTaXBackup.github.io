## Post #1
- Username: klightspeed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 15, 2014 1:29 pm
- Post datetime: 2014-11-15T07:56:32+00:00
- Post Title: Abe's Oddysee DDV format

Some of the information on the [Oddworld Abes Oddysee DDV](http://wiki.xentax.com/index.php?title=Oddworld Abes Oddysee DDV) wiki page is incorrect.

The file format is slightly modified from the PSX STR format.

The Endian Order of the DDV files is little-endian.

The DDV files are made up of 2336 byte (CD Mode2) sectors.
150 sectors are processed per second (2x CD speed).

The two sector types found in the DDV files are MOIR sectors and VALE sectors.
Every 8th sector is generally a VALE sector.
Video frames are generally scheduled such that a constant framerate of 15fps is maintained, by having three frames of 9 sectors followed by one frame of 8 sectors.

MOIR sectors contain video data, while VALE sectors contain audio data.

Sector header:

```
0004  uint32 {4}     Sector number within file (zero-based)

```


Each MOIR sector contains a 32 byte header and 2016 bytes of data.
The only difference between this header and the PSX STR video header is the 'AKIK' magic.

```
0004  uint16 {2}     Sector number within frame (zero-based)
0006  uint16 {2}     Number of sectors in frame
0008  uint32 {4}     Frame number within file (one-based)
000C  uint32 {4}     Frame data length
0010  uint16 {2}     Video Width
0012  uint16 {2}     Video Height
0014  uint16 {2}     Number of MDEC codes divided by two, and rounded up to a multiple of 32
0016  uint16 {2}     Always 0x3800
0018  uint16 {2}     Quantization level of the video frame
001A  uint16 {2}     Version of the video frame (always 2)
001C  uint32 {4}     Always 0x00000000

```


Each frame of video data starts with an 8-byte header:

```
0002  uint16 {2}     Always 0x3800
0004  uint16 {2}     Quantization level of the video frame
0006  uint16 {2}     Version of the video frame (always 2)

```


The video is encoded using the same encoding as used by the PSX STR format.

Each VALE sector contains 18 groups of 128 bytes of audio data encoded using the same 37.8kHz 4-bit stereo CDXA ADPCM as the PSX STR format.

The following python will convert a Abe's Oddysee DDV file into a PSX STR file (with 2352 byte sectors and a RIFF header) that can be converted using ffmpeg:

```
#
# Feel free to use, improve, integrate or convert this code.
# No attribution is required, and no warranty is given.

import sys
import os.path
import struct

def bcd(v):
    return (((v) % 10) | (((v) / 10) << 4))

if __name__ == '__main__':
    if len(sys.argv) != 3:
        print "Usage: ddv2str input.ddv output.str"
        sys.exit(1)

    if os.path.exists(sys.argv[2]):
        print "Output file already exists"
        sys.exit(1)

    with open(sys.argv[1], 'rb') as input:
        with open(sys.argv[2], 'wb') as output:
            riffhdr = struct.pack('<4sL4s4sLL4sLL4sL',
                'RIFF', 0, 'CDXA', 
                'fmt ', 16, 0, '=UXA', 1, 0, 
                'data', 0)
            output.write(riffhdr)

            for ddvdata in iter(lambda: input.read(2336), ''):
                secttype, sectnum, sectdata = struct.unpack('<4sL2328s', ddvdata)
                cdframenr = sectnum % 75
                cdsecond = (sectnum / 75) % 60
                cdminute = (sectnum / (75 * 60)) % 100
                cdxaflags = 0x40 | (0x02 if secttype == "MOIR" else 0x24)
                
                if secttype == 'MOIR':
                    sectdata = struct.pack('<L2324s', 0x80010160, 
                        struct.unpack('<L2324s', sectdata)[1])

                cdxadata = struct.pack('<24B2328s',
                    0x00, 0xFF, 0xFF, 0xFF,
                    0xFF, 0xFF, 0xFF, 0xFF,
                    0xFF, 0xFF, 0xFF, 0x00,
                    bcd(cdminute), bcd(cdsecond), bcd(cdframenr), 2,
                    1, 1, cdxaflags, 1,
                    1, 1, cdxaflags, 1,
                    sectdata
                    )

                output.write(cdxadata)

```


The following python will convert from PSX STR (with 2352 byte sectors and a RIFF header) to Abe's Oddysee DDV:

```
#
# Feel free to use, improve, integrate or convert this code.
# No attribution is required, and no warranty is given.

import sys
import os.path
import struct

if __name__ == '__main__':
    if len(sys.argv) != 3:
        print "Usage: str2ddv input.str output.ddv"
        sys.exit(1)

    if os.path.exists(sys.argv[2]):
        print "Output file already exists"
        sys.exit(1)

    with open(sys.argv[1], 'rb') as input:
        with open(sys.argv[2], 'wb') as output:
            sectnum = 0
            riffhdr = input.read(44)
            riff, flen, ftype = unpack('<4sL4s', riffhdr)
            
            if riff != 'RIFF':
                input.seek(0, 0)

            for strdata in iter(lambda: input.read(2352), ''):
                hdr, flags, xa, data = struct.unpack('<18sB5s2328s', strdata)

                if flags & 0x02:
                    secttype = 'MOIR'
                    data = struct.pack('<4s2324s', 'AKIK',
                        struct.unpack('<L2324s', data)[1])
                else:
                    secttype = 'VALE'

                ddvdata = struct.pack('<4sL2328s',
                    secttype,
                    sectnum,
                    data
                    )

                output.write(ddvdata)
                sectnum += 1

```
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-03-07T20:13:57+00:00
- Post Title: Abe's Oddysee DDV format

Nice! Have you done any research on the DDV format used in the PC version of Metal Gear Solid? I know you can play the files back in Masher but I would like to be able to play them in FFMpeg, for instance.
