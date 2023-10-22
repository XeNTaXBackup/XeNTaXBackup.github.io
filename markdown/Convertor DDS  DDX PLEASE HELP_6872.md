## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-29T17:49:51+00:00
- Post Title: Convertor DDS >> DDX *PLEASE HELP*

Hello all,

I'm trying to mod game Fallout NV and X360 contains files DDX instead of DDS. I would like to convert DDS to DDX, can anyone have a look on the format please an might do some convertor for it ?? It would be great 

Downloads

```
http://loadfiles.in/k7prbidj4gg4/DDX_DDS.rar
```


I was able to only find the python script from DDX to DDS:

```

try:
    import psyco
    psyco.full()
except ImportError:
    pass

def main(fn):

    ddx = file(fn[0], 'rb')
    trash = ddx.read(8)
    sheader = ddx.read(128)
    header = ''

    for x in range(1,33):
        theader = sheader[(x*4-4):(x*4)]
        header = header + theader[::-1]

    length = int(binascii.hexlify(ddx.read(4)), 16)

    dds1c = ddx.read(length)
    dds2c = ddx.read()
    dds1d = zlib.decompressobj().decompress(dds1c)
    dds2d = zlib.decompressobj().decompress(dds2c)

    header2 = header
    hheader = binascii.hexlify(header)
    
    a1 = hheader[24:26]
    a2 = hheader[26:28]
    b1 = hheader[32:34]
    b2 = hheader[34:36]
    
    a = hex(int(a2 + a1, 16)/2)[2:].zfill(4)
    a = a[2:] + a[:2]
    b = hex(int(b2 + b1, 16)/2)[2:].zfill(4)
    b = b[2:] + b[:2]

    header1 = binascii.unhexlify(hheader[:24] + a + hheader[28:32] + b + hheader[36:])
    dds1 = header1 + dds1d
    dds2 = header + dds2d

    name = fn[0].split('\\')[-1:][0][:-1] + 's'
    file(name.split('.')[0] + 'SM.' + name.split('.')[1], 'wb').write(dds1)
    file(name.split('.')[0] + 'LG.' + name.split('.')[1], 'wb').write(dds2)



if __name__=='__main__':
    sys.exit(main(sys.argv[1:]))
```


HERE is format comments from other source :

> Right!
>
> 
>
> So, as far as I can tell, all DDX files are two DDS files sharing the same header that are compressed separately (sans header) using something similar to ZLIB and then concatenated into one file.
>
> 
>
> Great, huh?
>
> 
>
> There are basically two copies of the same DDS in each file. The first is simply half the size of the second (they always seem to be in that order). So molerat.ddx has two dds files compressed inside it. The first is 512x512 and the second is 1024x1024. Please remember that they are different sizes, but only have one header. That comes into play later and complicates things a little bit. Update: I'm now not entirely certain about this part. See Post #4
>
> 
>
> If you open up any DDX file you will see a 136 bytes worth of header. NOW: I have to admit that I'm not sure what role the first 8bytes fill. So what? Neither do you! Stop judging me! We're moving on to the next 128 bytes before my embarrassment and shame prevent me from completing this post. In fact, if you have a DDX open in a hex editor right now, just go ahead and delete the first 8 bytes. We don't want em right now anyway.
>
> 
>
> The next 128 bytes are your standard DDS header, except that they appear to be big-endian (or in other words: bass ackwards). To get a standard little-endian header you could reverse the order of every 4 bytes manually, or you could just select that section (and ONLY that section, thank you) in a hex editor and byte flip the whole thing (treated as 32bit unsigned long). If you did it right, the first for bytes should be 44 44 53 20 (or DDS followed by a single space, eg. "DDS ")
>
> 
>
> If you happen to have a hex editor open and are following along, then you will now have a DDX file that is 8 bytes smaller and has a usable DDS header taking up the first 128 bytes. Great, huh? You like having that header? Want to explore it a little bit?
>
> 
>
> Too bad for you!
>
> 
>
> Cut those 128 bytes out and paste them in a new file, leaving your DDX without a header. Well... Almost with out a header. I think you could call the next 4 bytes a header, but its not the file's header. They represent the length (starting with the byte immediately following) of the first compressed DDS. Immedietly following that block (again, starting with the very next byte) is the second compressed DDS. As far as I can tell the second block runs right to the end of the file. The last byte of the block is the last byte of the file. Unless your BSA extractor is having trouble and is adding 20 or so extra bytes onto the end of the file. I've seen that a lot...
>
> 
>
> You might see something like this at the end of your DDX:
>
> Code:
>
> 
>
> J..Zj.......%........a..9$textures\clutter\food\molemeat_n.d
>
> 
>
> If so, just remove "textures\clutter\food\molemeat_n.d" PLUS the one byte before it (which is "$" in this case)
>
> 
>
> So now what you have what look like two compressed DDS files. They are compressed individually, so you need to find out where the first block ends (by checking the 4 byte header) and splitting the blocks into two separate files (and go ahead and remove the last 4 bytes of header while you are at it). Run each of these files through using the zlib library, but with a tool that will ignore errors! Whatever method is used to compress these doesn't actually create a fully valid zlib stream. In fact, I couldn't decompress the files in python at first. I was using the top-level decompress() included in zlib. I had to use the decompressobj().decompress() because it (apparently) ignores the lack of end_stream in the file.
>
> 
>
> Once you have the decompressed DDS files, you can add the 128 byte header that you removed earlier back to the top of the file. The larger DDS should open fine, but the smaller one will wither fail to load or look a tiny bit crazy. Its easily fixable though...

Thx a bunch
