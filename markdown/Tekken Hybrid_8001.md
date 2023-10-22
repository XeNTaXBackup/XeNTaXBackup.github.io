## Post #1
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-06T17:53:27+00:00
- Post Title: Tekken Hybrid

EDIT: This thread has transformed from Tekken 3 to Tekken Hybrid, which has the Tekken 3 models, just hi-res, but still the same design.

So skip all these pointless posts and start reading from the 4th post counting from the bottom of this page.

---------------------------------------
ORIGINAL POST:

Hi guys, so basically I just read the Definitive guide to exploring file formats, and watched Rheini's flash tutorial. I have some programming knowledge, but yeah I'm brand spanking new to file format exploring.

I'm going to explore a file format in this topic and hopefully get some help when I get stuck. I don't want someone to do the work for me though, I want to gain some experience myself, because there doesn't seem to be any other tutorial out there so this is the only way to learn more. But any hints and tips are welcome, as well as any help when I ask for it (I feel like I will a lot).

For my first ever format I choose Tekken 3's *.BIN iso format. because that's my favorite game when I was a kid 
Please tell me if it's a bad idea. From what I know each PSX game has it's own iso (bin) format. If I'm wrong let me know and I'll try another format.

Here is a 4 MB slice from the beginning of the file, if anyone will want to help out: 
[http://www.2shared.com/file/WxY0_vLF/tekken3-part.html](http://www.2shared.com/file/WxY0_vLF/tekken3-part.html)

Again, note that I'm completely new, so I'm terrible at this. Instead of telling how terrible I am please help me improve. Thanks.

-------------------------------------------------------


EDIT: OK I feel like Im getting somewhere, looks like this structure repeats in all of the file.
That's probably not padding, but file data including padding, though it was all zeros in the first few "entries".
## Post #2
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-07T07:44:37+00:00
- Post Title: Tekken Hybrid

OK, this is as far as I could go for my first try:

```

    byte {12}   header
    
    uint {4}    unknown
    
    uint {4}    size of data following, usually power of two
    
    uint {4}    size of data following, repeated
    
    byte {size} sometimes nulls, but not always
    
    byte {280}  useful data which i don't get
```


Need tips now.
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-01-07T09:01:17+00:00
- Post Title: Tekken Hybrid

If you're talking about the .bin files that you load on an emu, they're already documented, and all you had to do is to load them on a virtual disk drive utility.
## Post #4
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-07T10:02:38+00:00
- Post Title: Tekken Hybrid

d'oh.

Nice start I guess. Well than I'll try the files inside it.

> they're already documented
where?
I created a virtual drive with daemon tools, but I can't read most of the files. "Invalid ms dos functions" when trying to copy most files. Maybe PSX ISO/BIN is not the same as your standard one. I haven't seen any PSX specific iso tool though, I've only seen BIN extractors for specific games, hence why I thought each game uses it's own format.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-07T21:31:57+00:00
- Post Title: Tekken Hybrid

The disk might be protected such that normal image readers can't load it up.
I don't remember what people use to dump the data though.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-07T22:20:23+00:00
- Post Title: Tekken Hybrid

How about trying to rip models from Tekken Hybrid? I would help out on that one. Most people around here don't look at games from older systems. Hybrid should be a good challenge .
## Post #7
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-07T22:38:55+00:00
- Post Title: Tekken Hybrid

I thought of older games because I assumed newer ones are more complex, more likely to contain custom stuff, like encryption, etc. And this is my first try, so...
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-07T22:56:50+00:00
- Post Title: Tekken Hybrid

oh no, that's not the case at all! some modern games are extremely easy! some games encrypt their data, some use funky custom compression schemes, and some use funky formats, but that is only a mild percentage of all games. for your first time, if you have a jailbroken ps3 or a regular xbox360, rip one of your games to pc. look for obvious vertex and index buffers. if you can't find them, try another game. if you can, give it a go.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T00:40:48+00:00
- Post Title: Tekken Hybrid

I imagine older games, with their rather restrictive space constraints, would employ all sorts of crazy techniques to try to squeeze as much data as they can into it.
## Post #10
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-08T07:06:08+00:00
- Post Title: Tekken Hybrid

Well you have to think both ways: over the last 10 years more complex compression and encryption algorithms were probably created. And also I think as game budgets rise the developers become more likely to reinvent the wheel by creating custom encryption/compression, or add extra protection.
But the main difficulty I see that more video/audio encodings exist now and more things exist in 3d files, like all sorts of normal maps, other maps like glow maps, you have "binormals", shader materials and other stuff which I might not even know about.

Of course if you don't mind working with a newbie and answering my newbie questions, I'd love to work with you guys.

PS. Still interested what can be used to extract PSX ISOs.

EDIT: OK, I checked out Tekken Hybrid and I think it would make more sense as the models and scene backgrounds from TTT1 are just highpoly versions of the T3 ones, audio is probably the same too (but higher quality).

I wonder if the two games included use the same formats, or TT1 just got it's sourcecode ported to PS3 SDK and file formats are the same.
Anyway, should we work on the PS3 or X360 version?
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-09T00:32:37+00:00
- Post Title: Tekken Hybrid

Games are projects that need to be developed on time and within budget. That is software engineering 101. Most games don't implement hardcore encryption or hardcore compression schemes because it costs extra money and extra time to hire someone who specializes in these fields. Unless, of course, they get lucky and hire a nerdy game programmer who knows everything. I think obfuscating a file format is just as effective as using encryption in protecting game assets.

Ps3. Tekken hybrid might be hard. U ready lol? What language u want to use?
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-09T01:54:16+00:00
- Post Title: Tekken Hybrid

Starting with the remake of Tekken Tag Tournament HD.

Step #1: Identify Model Files

The character models appear to be the CHR files in the USRDIR\data\asset\dai3\mdl directory. How do I know? Well, filenames are also character names and I think I found obvious vertex and index buffers in the CHR files  (see pics of Nina Williams first file). Also, after the index buffer, appears to be a list of headerless textures. With a little experience, you will be able to recognize these patterns just by looking at the hexadecimal as well. There also appears to be other important data in the KMD and NGI files, but for now, let's just focus on the CHR files and later on we'll try to figure out what are in the KMD and NGI files. 


Obvious vertex buffer.


Obvious index buffer.


Obvious headerless texture.

Step #2: See If Rich Has Already Done It

Before starting to code anything, we should take a look to see if Rich has already done it. In general, I try not to step on something somebody else is working on or has already done. Tekken is a AAA-game and I tend to leave these alone since usually other guys tend to pick them up before I can even save up enough money to buy the game! I tried loading the CHR files in Noesis and it was a no go so I think we're good here.

Step #3: Identify Vertex Buffer and Vertex Format(s)

We are going to hard-code a model rip using Nina Williams, for which can be found in the character model directory as nina1u.chr. Then, when we know it's possible to rip vertices and faces, we'll worry about how to get to the vertex and index data in a more general way. It's stupid to waste a week or more trying to figure out how to get to the data only to find out that the vertex data is obfuscated or encrypted or whatever.

Let's find the vertex data now. Open nina1u.chr in HXD and start scrolling down. We see nothing but junk until about offset 0x14FC. Look at the picture below and you will see the pattern. The pattern on data 0x40 bytes long. However, this is not the vertex data... it's something else because well... I tried it and it wasn't that interesting.



So keep scrolling down 0x40 bytes at a time until you no longer see those repetitious 0xFFFF7F3F and 0x0000803F values at the end of the pattern. You will come to offset 0x2F3C. However, this time, the pattern is not 0x40 bytes, it's 0x20 bytes instead (see picture below).



Now, I'll tell you why I think 0x2F3C is the position of the vertex buffer... scroll all the way up to the top back to the beginning of the file. What do you see in the picture below? That's right, that's 0x2F3C in little endian and that is the position of our vertex buffer. We now officially have a way to get to our vertex buffer by reading an offset from the beginning of the file.



Now we have to determine how much data is in the vertex buffer. Go back to offset 0x2F3C and keep scrolling down until you see an obvious break in the pattern. This occurs at offset 0x2A03C.



So scroll back up to the top and look around... find this special number 0x2A03C anywhere? Yep yep yep, right after the position of the vertex buffer! This offset not only marks the end of the vertex buffer, but it also marks the beginning of the index buffer, which we'll talk about later.



It is now time to write some python code. We are going to open the file, read the two offsets, starting at position 0x14, and then try to read the vertex data located between those two offsets. Since (0x2A03C - 0x2F3C)/0x20 = 0x1388, we are going to have 5,000 total vertices. When there is a pattern in the vertex data, such as the 0x20 byte pattern in this one, the vertex data is probably interleaved. Vertex data can be interleaved or non-interleaved, but usually, it is interleaved with positions, normals and uvs all mixed together.

Run the following code. It opens the file, moves to the vertex buffer, and then tries to read the vertex data in groups of 0x20 bytes. It initially assumes that all data in the vertex buffer are 4-byte floats. Assuming all 4-byte floats is usually a good place to start. However, looking at the output of the code, you will see that the floats are waaaaaayyyyyy off! 2.945423288093901e+17? No way!

```

#
# open file 
#
ifile = open('nina1u.chr', 'rb');

#
# read vertex buffer and index buffer offsets
#
ifile.seek(0x14);
vbuffer_offset = struct.unpack('<I', ifile.read(4))[0];
ibuffer_offset = struct.unpack('<I', ifile.read(4))[0];
print('vbuffer_offset = ', vbuffer_offset);
print('ibuffer_offset = ', ibuffer_offset);

#
# calculate vertex buffer properties
#
vbuffer_size = ibuffer_offset - vbuffer_offset;
vertices = int(vbuffer_size/0x20);
print('size of vertex buffer in bytes = ', vbuffer_size);
print('number of vertices = ', vertices);
print('');

#
# move file pointer to vertex buffer
#
ifile.seek(vbuffer_offset);

#
# try reading vertices in groups of 0x20 (32) bytes
#
for i in range(vertices):
    print(struct.unpack('f', ifile.read(4))[0]); #  4 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); #  8 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); # 12 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); # 16 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); # 20 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); # 24 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); # 28 bytes total
    print(struct.unpack('f', ifile.read(4))[0]); # 32 bytes total
    print('');

ifile.close()

```


```
vbuffer_offset =  12092
ibuffer_offset =  172092
size of vertex buffer in bytes =  160000
number of vertices =  5000

2.945423288093901e+17
2.986167027476185e-41
0.00010737865522969514
2.0891958804618698e-41
1.5222401117398476e-09
1.401298464324817e-45
2.152394441202919e-41
0.0

2.6888498445706854e+17
3.0179765026163585e-41
5.48811221960932e-05
2.103489124797983e-41
2.5642337142528504e-09
1.401298464324817e-45
2.152394441202919e-41
0.0

2.5557927885327565e+17
2.98812884532624e-41
4.00543212890625e-05
2.1092344485017147e-41
2.971773938043043e-09
1.401298464324817e-45
2.152394441202919e-41
0.0

1.4344176297364685e+17
3.035632863266851e-41
0.0001317995775025338
2.0777052330544063e-41
1.0722761345505205e-08
1.7455932931140317e-39
3.513446247805328e-14
1.5209693531781564e-41

```


So in other words, this game doesn't use 4-byte floats to store vertex data. It must using something else. If 4-byte floats fail, the next thing to try is 2-byte floats, which are known as half-floats. Python doesn't support half-floats so you will have to code your own algorithm. Half-floats are encoded as 2-byte unsigned integers and are then converted to 4-byte floats using a special algorithm. So let's write a function in python that reads an unsigned short (a half-float) and converts it into a normal 4-byte float. We will also call this function, read_half_float, in our little read loop instead and see what we get. Remember that because we are reading only 2 bytes at a time now we have to read 16 half-floats per vertex. When your run the following program below, you will see very nice numbers now! Look at the first three numbers per group; those are our vertices! The second group of three numbers are obviously the per-vertex normal and the next group of two numbers is the UV. This is too easy!

```
import math
import array

def read_half_float(ifile):

    # read unsigned short
    value = struct.unpack('H', ifile.read(2))[0]; # read unsigned short

    # parse unsigned short into floating-point components
    temp = array.array('H', [0, 0, 0])
    temp[0] = (value & 0x8000);       # sign
    temp[1] = (value & 0x7C00) >> 10; # exponent
    temp[2] = (value & 0x03FF);       # mantissa

    # set sign constant
    sgn = 0.0;
    if temp[0] == 0:
       sgn = +1.0
    else:
       sgn = -1.0

    # if exponent is 0
    if temp[1] == 0:
       if temp[2] == 0:
          return 0.0
       else:
          return sgn*(math.pow(2.0, -14.0)*(temp[2]/1024.0));

    # if exponent is less than 32
    if temp[1] < 32:
       return sgn*math.pow(2.0, temp[1] - 15.0)*(1.0 + (temp[2]/1024.0));

    # half-float is invalid
    if temp[2] == 0:
       return math.NaN;

    # half-float is invalid
    return math.NaN;

#
# open file 
#
ifile = open('nina1u.chr', 'rb');

#
# read vertex buffer and index buffer offsets
#
ifile.seek(0x14);
vbuffer_offset = struct.unpack('<I', ifile.read(4))[0];
ibuffer_offset = struct.unpack('<I', ifile.read(4))[0];
print('vbuffer_offset = ', vbuffer_offset);
print('ibuffer_offset = ', ibuffer_offset);

#
# calculate vertex buffer properties
#
vbuffer_size = ibuffer_offset - vbuffer_offset;
vertices = int(vbuffer_size/0x20);
print('size of vertex buffer in bytes = ', vbuffer_size);
print('number of vertices = ', vertices);
print('');

#
# move file pointer to vertex buffer
#
ifile.seek(vbuffer_offset);

#
# try reading vertices in groups of 0x20 (32) bytes
#
for i in range(vertices):
    print(read_half_float(ifile)); # 2 bytes total
    print(read_half_float(ifile)); # 4 bytes total
    print(read_half_float(ifile)); # 6 bytes total
    print(read_half_float(ifile)); # 8 bytes total
    print(read_half_float(ifile)); # 10 bytes total
    print(read_half_float(ifile)); # 12 bytes total
    print(read_half_float(ifile)); # 14 bytes total
    print(read_half_float(ifile)); # 16 bytes total
    print(read_half_float(ifile)); # 18 bytes total
    print(read_half_float(ifile)); # 20 bytes total
    print(read_half_float(ifile)); # 22 bytes total
    print(read_half_float(ifile)); # 24 bytes total
    print(read_half_float(ifile)); # 26 bytes total
    print(read_half_float(ifile)); # 28 bytes total
    print(read_half_float(ifile)); # 30 bytes total
    print(read_half_float(ifile)); # 32 bytes total
    print('');

#
# close file
#
ifile.close()

```


```
vbuffer_offset =  12092
ibuffer_offset =  172092
size of vertex buffer in bytes =  160000
number of vertices =  5000

-22.34375
288.5
57.9375
0.0
0.139892578125
0.60986328125
0.77978515625
0.0
0.44140625
0.1505126953125
5.960464477539063e-08
0.0
1.0
0.0
0.0
0.0

-42.9375
283.5
66.0625
0.0
0.1298828125
0.5498046875
0.82958984375
0.0
0.40478515625
0.162109375
5.960464477539063e-08
0.0
1.0
0.0
0.0
0.0

0.0
280.75
58.375
0.0
0.0
0.51953125
0.849609375
0.0
0.5
0.16552734375
5.960464477539063e-08
0.0
1.0
0.0
0.0
0.0

```


Now let's write some code to write all this data to an OBJ file. Look at Wikipedia for the OBJ file format; it is really easy.

```
import math
import array

def read_half_float(ifile):

    # read unsigned short
    value = struct.unpack('H', ifile.read(2))[0]; # read unsigned short

    # parse unsigned short into floating-point components
    temp = array.array('H', [0, 0, 0])
    temp[0] = (value & 0x8000);       # sign
    temp[1] = (value & 0x7C00) >> 10; # exponent
    temp[2] = (value & 0x03FF);       # mantissa

    # set sign constant
    sgn = 0.0;
    if temp[0] == 0:
       sgn = +1.0
    else:
       sgn = -1.0

    # if exponent is 0
    if temp[1] == 0:
       if temp[2] == 0:
          return 0.0
       else:
          return sgn*(math.pow(2.0, -14.0)*(temp[2]/1024.0));

    # if exponent is less than 32
    if temp[1] < 32:
       return sgn*math.pow(2.0, temp[1] - 15.0)*(1.0 + (temp[2]/1024.0));

    # half-float is invalid
    if temp[2] == 0:
       return math.NaN;

    # half-float is invalid
    return math.NaN;

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# open output file
#
ofile = open('nina1u.obj', 'wt');

#
# save OBJ header
#
ofile.write('o nina1u.obj\n');
ofile.write('\n');

#
# read vertex buffer and index buffer offsets
#
ifile.seek(0x14);
vbuffer_offset = struct.unpack('<I', ifile.read(4))[0];
ibuffer_offset = struct.unpack('<I', ifile.read(4))[0];
print('vbuffer_offset = ', vbuffer_offset);
print('ibuffer_offset = ', ibuffer_offset);

#
# calculate vertex buffer properties
#
vbuffer_size = ibuffer_offset - vbuffer_offset;
vertices = int(vbuffer_size/0x20);
print('size of vertex buffer in bytes = ', vbuffer_size);
print('number of vertices = ', vertices);
print('');

#
# move file pointer to vertex buffer
#
ifile.seek(vbuffer_offset);

#
# try reading vertices in groups of 0x20 (32) bytes
#
for i in range(vertices):
    # read half floats
    vx = read_half_float(ifile); #  2 bytes total
    vy = read_half_float(ifile); #  4 bytes total
    vz = read_half_float(ifile); #  6 bytes total
    u1 = read_half_float(ifile); #  8 bytes total
    nx = read_half_float(ifile); # 10 bytes total
    ny = read_half_float(ifile); # 12 bytes total
    nz = read_half_float(ifile); # 14 bytes total
    u2 = read_half_float(ifile); # 16 bytes total
    tu = read_half_float(ifile); # 18 bytes total
    tv = read_half_float(ifile); # 20 bytes total
    u3 = read_half_float(ifile); # 22 bytes total
    u4 = read_half_float(ifile); # 24 bytes total
    u5 = read_half_float(ifile); # 26 bytes total
    u6 = read_half_float(ifile); # 28 bytes total
    u7 = read_half_float(ifile); # 30 bytes total
    u8 = read_half_float(ifile); # 32 bytes total

    # save vertex
    strlist = []
    strlist.append('v ');
    strlist.append(str(vx));
    strlist.append(' ');
    strlist.append(str(vy));
    strlist.append(' ');
    strlist.append(str(vz));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # save normal
    strlist = []
    strlist.append('vn ');
    strlist.append(str(nx));
    strlist.append(' ');
    strlist.append(str(ny));
    strlist.append(' ');
    strlist.append(str(nz));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # save UV
    strlist = []
    strlist.append('vt ');
    strlist.append(str(tu));
    strlist.append(' ');
    strlist.append(str(tv));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # extra newline
    ofile.write('\n');

#
# close file
#
ifile.close()

```


And now what do we got? We got BOOBIES!


Onto the next step!

Step #4: Reading the Index Buffer

Go back up to the top of the file to where we read those two offsets. The first offset we read was the start of the vertex data, 0x2F3C. The next offset, 0x02A03C, was the end of vertex data and the beginning of the index buffer data. The next offset after that (see image below), 0x030A38, is the end of the index buffer data and the beginning of the texture data.



Since each index is only two bytes each, an unsigned short, we can compute the number of indices by subtracting the last two offsets and dividing by 2. Replace the section of code that we had above with this one, which adds reading the texture offset.

```
# read vertex buffer and index buffer offsets
#
ifile.seek(0x14);
vbuffer_offset = struct.unpack('<I', ifile.read(4))[0];
ibuffer_offset = struct.unpack('<I', ifile.read(4))[0];
tbuffer_offset = struct.unpack('<I', ifile.read(4))[0]; # texture data offset
print('vbuffer_offset = ', vbuffer_offset);
print('ibuffer_offset = ', ibuffer_offset);
print('tbuffer_offset = ', tbuffer_offset); # texture data offset

```


Then let's compute size of the index buffer and the number of indices to read.

```
# calculate index buffer properties
#
ibuffer_size = tbuffer_offset - ibuffer_offset;
indices = int(ibuffer_size/0x2);
print('size of index buffer in bytes = ', ibuffer_size);
print('number of indices = ', indices);
print('');

```


You will get the following output now:

```
vbuffer_offset =  12092
ibuffer_offset =  172092
tbuffer_offset =  199224

size of vertex buffer in bytes =  160000
number of vertices =  5000

size of index buffer in bytes =  27132
number of indices =  13566

```


Since the number of indices is divisible by 3, 13566/3 = 4522, I'm guessing that this index buffer uses triangle lists. Also, looking at the index buffer data in the hex editor, there are no 0xFFFFs or anything like that which usually indicate triangle strips with strip-cut indices. So I don't think this index buffer uses triangle strips. So let's try triangles first. In our python code, after you have read all the vertices, we are automatically at the beginning of the index data since the data is packed. All we have to do is loop through the number of triangles, which is (number of indices/3), reading three points at a time and saving them to the OBJ file. Here's how to do this:

```
import math
import array

def read_half_float(ifile):

    # read unsigned short
    value = struct.unpack('H', ifile.read(2))[0]; # read unsigned short

    # parse unsigned short into floating-point components
    temp = array.array('H', [0, 0, 0])
    temp[0] = (value & 0x8000);       # sign
    temp[1] = (value & 0x7C00) >> 10; # exponent
    temp[2] = (value & 0x03FF);       # mantissa

    # set sign constant
    sgn = 0.0;
    if temp[0] == 0:
       sgn = +1.0
    else:
       sgn = -1.0

    # if exponent is 0
    if temp[1] == 0:
       if temp[2] == 0:
          return 0.0
       else:
          return sgn*(math.pow(2.0, -14.0)*(temp[2]/1024.0));

    # if exponent is less than 32
    if temp[1] < 32:
       return sgn*math.pow(2.0, temp[1] - 15.0)*(1.0 + (temp[2]/1024.0));

    # half-float is invalid
    if temp[2] == 0:
       return math.NaN;

    # half-float is invalid
    return math.NaN;

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# open output file
#
ofile = open('nina1u.obj', 'wt');

#
# save OBJ header
#
ofile.write('o nina1u.obj\n');
ofile.write('\n');

#
# read vertex buffer and index buffer offsets
#
ifile.seek(0x14);
vbuffer_offset = struct.unpack('<I', ifile.read(4))[0];
ibuffer_offset = struct.unpack('<I', ifile.read(4))[0];
tbuffer_offset = struct.unpack('<I', ifile.read(4))[0]; # texture data offset
print('vbuffer_offset = ', vbuffer_offset);
print('ibuffer_offset = ', ibuffer_offset);
print('tbuffer_offset = ', tbuffer_offset); # texture data offset
print('');

#
# calculate vertex buffer properties
#
vbuffer_size = ibuffer_offset - vbuffer_offset;
vertices = int(vbuffer_size/0x20);
print('size of vertex buffer in bytes = ', vbuffer_size);
print('number of vertices = ', vertices);
print('');

#
# calculate index buffer properties
#
ibuffer_size = tbuffer_offset - ibuffer_offset;
indices = int(ibuffer_size/0x2);
triangles = int(indices/3);
print('size of index buffer in bytes = ', ibuffer_size);
print('number of indices = ', indices);
print('number of triangles = ', triangles);
print('');

#
# move file pointer to vertex buffer
#
ifile.seek(vbuffer_offset);

#
# try reading vertices in groups of 0x20 (32) bytes
#
for i in range(vertices):
    # read half floats
    vx = read_half_float(ifile); #  2 bytes total
    vy = read_half_float(ifile); #  4 bytes total
    vz = read_half_float(ifile); #  6 bytes total
    u1 = read_half_float(ifile); #  8 bytes total
    nx = read_half_float(ifile); # 10 bytes total
    ny = read_half_float(ifile); # 12 bytes total
    nz = read_half_float(ifile); # 14 bytes total
    u2 = read_half_float(ifile); # 16 bytes total
    tu = read_half_float(ifile); # 18 bytes total
    tv = read_half_float(ifile); # 20 bytes total
    u3 = read_half_float(ifile); # 22 bytes total
    u4 = read_half_float(ifile); # 24 bytes total
    u5 = read_half_float(ifile); # 26 bytes total
    u6 = read_half_float(ifile); # 28 bytes total
    u7 = read_half_float(ifile); # 30 bytes total
    u8 = read_half_float(ifile); # 32 bytes total

    # save vertex
    strlist = []
    strlist.append('v ');
    strlist.append(str(vx));
    strlist.append(' ');
    strlist.append(str(vy));
    strlist.append(' ');
    strlist.append(str(vz));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # save normal
    strlist = []
    strlist.append('vn ');
    strlist.append(str(nx));
    strlist.append(' ');
    strlist.append(str(ny));
    strlist.append(' ');
    strlist.append(str(nz));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # save UV
    strlist = []
    strlist.append('vt ');
    strlist.append(str(tu));
    strlist.append(' ');
    strlist.append(str(tv));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # extra newline
    ofile.write('\n');

#
# read triangles (2 bytes per index)
#
for i in range(triangles):
    # read three points of a triangle
    a = struct.unpack('<H', ifile.read(2))[0];
    b = struct.unpack('<H', ifile.read(2))[0];
    c = struct.unpack('<H', ifile.read(2))[0];

    # OBJ uses 1-based indices
    a = a + 1;
    b = b + 1;
    c = c + 1;

    # save points to OBJ file
    strlist = []
    strlist.append('f ');
    strlist.append(str(a));
    strlist.append('/');
    strlist.append(str(a));
    strlist.append('/');
    strlist.append(str(a));
    strlist.append(' ');
    strlist.append(str(b));
    strlist.append('/');
    strlist.append(str(b));
    strlist.append('/');
    strlist.append(str(b));
    strlist.append(' ');
    strlist.append(str(c));
    strlist.append('/');
    strlist.append(str(c));
    strlist.append('/');
    strlist.append(str(c));
    strlist.append(' ');
    strlist.append('\n');
    ofile.write(''.join(strlist));    

#
# close file
#
ifile.close()

```


Run the python code and open the OBJ file. What do you see? LOL this!



The reason why it's messed up is because I guessed wrong about the triangle lists. When you see only half the expected polygons there or so, or you see a bunch of holes in the model, it probably uses triangle strips instead. So instead of the number of triangles being the number of indices divided by three, the number of triangles is going to be the number of indices minus two. The algorithm for reading triangle strips is also a little different as well. Here is the code that tries triangle strips instead:

```
import math
import array

def read_half_float(ifile):

    # read unsigned short
    value = struct.unpack('H', ifile.read(2))[0]; # read unsigned short

    # parse unsigned short into floating-point components
    temp = array.array('H', [0, 0, 0])
    temp[0] = (value & 0x8000);       # sign
    temp[1] = (value & 0x7C00) >> 10; # exponent
    temp[2] = (value & 0x03FF);       # mantissa

    # set sign constant
    sgn = 0.0;
    if temp[0] == 0:
       sgn = +1.0
    else:
       sgn = -1.0

    # if exponent is 0
    if temp[1] == 0:
       if temp[2] == 0:
          return 0.0
       else:
          return sgn*(math.pow(2.0, -14.0)*(temp[2]/1024.0));

    # if exponent is less than 32
    if temp[1] < 32:
       return sgn*math.pow(2.0, temp[1] - 15.0)*(1.0 + (temp[2]/1024.0));

    # half-float is invalid
    if temp[2] == 0:
       return math.NaN;

    # half-float is invalid
    return math.NaN;

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# open output file
#
ofile = open('nina1u.obj', 'wt');

#
# save OBJ header
#
ofile.write('o nina1u.obj\n');
ofile.write('\n');

#
# read vertex buffer and index buffer offsets
#
ifile.seek(0x14);
vbuffer_offset = struct.unpack('<I', ifile.read(4))[0];
ibuffer_offset = struct.unpack('<I', ifile.read(4))[0];
tbuffer_offset = struct.unpack('<I', ifile.read(4))[0]; # texture data offset
print('vbuffer_offset = ', vbuffer_offset);
print('ibuffer_offset = ', ibuffer_offset);
print('tbuffer_offset = ', tbuffer_offset); # texture data offset
print('');

#
# calculate vertex buffer properties
#
vbuffer_size = ibuffer_offset - vbuffer_offset;
vertices = int(vbuffer_size/0x20);
print('size of vertex buffer in bytes = ', vbuffer_size);
print('number of vertices = ', vertices);
print('');

#
# calculate index buffer properties
#
ibuffer_size = tbuffer_offset - ibuffer_offset;
indices = int(ibuffer_size/0x2);
print('size of index buffer in bytes = ', ibuffer_size);
print('number of indices = ', indices);
print('');

#
# calculate number of triangles
#
triangles = indices - 2;
print('number of triangles = ', triangles);
print('');

#
# move file pointer to vertex buffer
#
ifile.seek(vbuffer_offset);

#
# try reading vertices in groups of 0x20 (32) bytes
#
for i in range(vertices):
    # read half floats
    vx = read_half_float(ifile); #  2 bytes total
    vy = read_half_float(ifile); #  4 bytes total
    vz = read_half_float(ifile); #  6 bytes total
    u1 = read_half_float(ifile); #  8 bytes total
    nx = read_half_float(ifile); # 10 bytes total
    ny = read_half_float(ifile); # 12 bytes total
    nz = read_half_float(ifile); # 14 bytes total
    u2 = read_half_float(ifile); # 16 bytes total
    tu = read_half_float(ifile); # 18 bytes total
    tv = read_half_float(ifile); # 20 bytes total
    u3 = read_half_float(ifile); # 22 bytes total
    u4 = read_half_float(ifile); # 24 bytes total
    u5 = read_half_float(ifile); # 26 bytes total
    u6 = read_half_float(ifile); # 28 bytes total
    u7 = read_half_float(ifile); # 30 bytes total
    u8 = read_half_float(ifile); # 32 bytes total

    # save vertex
    strlist = []
    strlist.append('v ');
    strlist.append(str(vx));
    strlist.append(' ');
    strlist.append(str(vy));
    strlist.append(' ');
    strlist.append(str(vz));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # save normal
    strlist = []
    strlist.append('vn ');
    strlist.append(str(nx));
    strlist.append(' ');
    strlist.append(str(ny));
    strlist.append(' ');
    strlist.append(str(nz));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # save UV
    strlist = []
    strlist.append('vt ');
    strlist.append(str(tu));
    strlist.append(' ');
    strlist.append(str(tv));
    strlist.append('\n');
    ofile.write(''.join(strlist));

    # extra newline
    ofile.write('\n');

#
# read first triangle in triangle strip
#
a = struct.unpack('<H', ifile.read(2))[0] + 1;
b = struct.unpack('<H', ifile.read(2))[0] + 1;
c = struct.unpack('<H', ifile.read(2))[0] + 1;

# save points to OBJ file
strlist = []
strlist.append('f ');
strlist.append(str(a));
strlist.append('/');
strlist.append(str(a));
strlist.append('/');
strlist.append(str(a));
strlist.append(' ');
strlist.append(str(b));
strlist.append('/');
strlist.append(str(b));
strlist.append('/');
strlist.append(str(b));
strlist.append(' ');
strlist.append(str(c));
strlist.append('/');
strlist.append(str(c));
strlist.append('/');
strlist.append(str(c));
strlist.append(' ');
strlist.append('\n');
ofile.write(''.join(strlist));

#
# read triangles (2 bytes per index)
#
for i in range(1, triangles):
    # read one more point
    a = b;
    b = c;
    c = struct.unpack('<H', ifile.read(2))[0] + 1;

    # save points to OBJ file
    if i % 2 == 0:
       strlist = []
       strlist.append('f ');
       strlist.append(str(a));
       strlist.append('/');
       strlist.append(str(a));
       strlist.append('/');
       strlist.append(str(a));
       strlist.append(' ');
       strlist.append(str(b));
       strlist.append('/');
       strlist.append(str(b));
       strlist.append('/');
       strlist.append(str(b));
       strlist.append(' ');
       strlist.append(str(c));
       strlist.append('/');
       strlist.append(str(c));
       strlist.append('/');
       strlist.append(str(c));
       strlist.append(' ');
       strlist.append('\n');
       ofile.write(''.join(strlist));
    else:
       strlist = []
       strlist.append('f ');
       strlist.append(str(a));
       strlist.append('/');
       strlist.append(str(a));
       strlist.append('/');
       strlist.append(str(a));
       strlist.append(' ');
       strlist.append(str(c));
       strlist.append('/');
       strlist.append(str(c));
       strlist.append('/');
       strlist.append(str(c));
       strlist.append(' ');
       strlist.append(str(b));
       strlist.append('/');
       strlist.append(str(b));
       strlist.append('/');
       strlist.append(str(b));
       strlist.append(' ');
       strlist.append('\n');
       ofile.write(''.join(strlist));
#
# close file
#
ifile.close()

```
 

And of course, even though it looks better, it still doesn't look right! This is more than likely because the model is not just made up of a single triangle strip, but rather multiple ones. The next step is going to be how to figure out how the model is divided up into surfaces. This data is hidden somewhere in the data above the vertex buffer data and now we have to go hunt for it.



Step #5: Dividing the Model Into Surfaces

So now we have to figure out how the model is divided into surfaces. But before we do this, I'm going to write a little python code in another file to ease the pain of all those silly struct.unpack calls. Create a file called xentax.py and add the following code to it.

```
import math
import array

#
# READING LITTLE ENDIAN
#

def LE_read_sint08(ifile):
    return struct.unpack('<b', ifile.read(1))[0];
	
def LE_read_uint08(ifile):
    return struct.unpack('<B', ifile.read(1))[0];
	
def LE_read_sint16(ifile):
    return struct.unpack('<h', ifile.read(2))[0];
	
def LE_read_uint16(ifile):
    return struct.unpack('<H', ifile.read(2))[0];

def LE_read_sint32(ifile):
    return struct.unpack('<i', ifile.read(4))[0];
	
def LE_read_uint32(ifile):
    return struct.unpack('<I', ifile.read(4))[0];
	
def LE_read_sint64(ifile):
    return struct.unpack('<q', ifile.read(8))[0];
	
def LE_read_uint64(ifile):
    return struct.unpack('<Q', ifile.read(8))[0];

def LE_read_float16(ifile):

    # read unsigned short
    value = struct.unpack('<H', ifile.read(2))[0]; # read unsigned short

    # parse unsigned short into floating-point components
    temp = array.array('H', [0, 0, 0])
    temp[0] = (value & 0x8000);       # sign
    temp[1] = (value & 0x7C00) >> 10; # exponent
    temp[2] = (value & 0x03FF);       # mantissa

    # set sign constant
    sgn = 0.0;
    if temp[0] == 0:
       sgn = +1.0
    else:
       sgn = -1.0

    # if exponent is 0
    if temp[1] == 0:
       if temp[2] == 0:
          return 0.0
       else:
          return sgn*(math.pow(2.0, -14.0)*(temp[2]/1024.0));

    # if exponent is less than 32
    if temp[1] < 32:
       return sgn*math.pow(2.0, temp[1] - 15.0)*(1.0 + (temp[2]/1024.0));

    # half-float is invalid
    if temp[2] == 0:
       return math.NaN;

    # half-float is invalid
    return math.NaN;

def LE_read_float32(ifile):
    return struct.unpack('<f', ifile.read(4))[0];
	
def LE_read_float64(ifile):
    return struct.unpack('<d', ifile.read(8))[0];

```


Now, going back to tekken.py, let's forget about the triangle code for a bit and start from scratch. Open Nina's file in your python code and move the file pointer to 0x40. This appears to be where the data actually starts (the 0xFFFFFFFF appears to be a marker to let you know the header is finished). Look at the following highlighted 0x1C bytes. There is also a similar pattern starting at offset 0x104. Let's read the data.



```

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# move to 0x40 and read some data
#
ifile.seek(0x40);
param01 = xentax.LE_read_uint32(ifile);
param02 = xentax.LE_read_uint32(ifile);
param03 = xentax.LE_read_uint32(ifile);
param04 = xentax.LE_read_uint32(ifile);
param05 = xentax.LE_read_uint32(ifile);
param06 = xentax.LE_read_uint32(ifile);
param07 = xentax.LE_read_uint32(ifile);
print(param01);
print(param02);
print(param03);
print(param04);
print(param05);
print(param06);
print(param07);

#
# close file
#
ifile.close()

```


```
0
0
67305985
555753246
908403490
976828471
1715354683

```


Definitely not 32-bit unsigned integers. After a little experimenting, you'll see that once again Tekken uses half-floats and that the following structure of the data is:

```

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# move to 0x40 and read some data
#
ifile.seek(0x40);
param01 = xentax.LE_read_uint32(ifile);
param02 = xentax.LE_read_uint32(ifile);
param03 = xentax.LE_read_uint16(ifile);
param04 = xentax.LE_read_uint16(ifile);
param05 = xentax.LE_read_float16(ifile);
param06 = xentax.LE_read_float16(ifile);
param07 = xentax.LE_read_float16(ifile);
param08 = xentax.LE_read_float16(ifile);
param09 = xentax.LE_read_float16(ifile);
param10 = xentax.LE_read_float16(ifile);
param11 = xentax.LE_read_float16(ifile);
param12 = xentax.LE_read_float16(ifile);
print(param01);
print(param02);
print(param03);
print(param04);
print(param05);
print(param06);
print(param07);
print(param08);
print(param09);
print(param10);
print(param11);
print(param12);

#
# close file
#
ifile.close()

```


```
0
0
513
1027
0.00695037841796875
0.010009765625
0.0139312744140625
0.384033203125
0.52685546875
0.77783203125
1.0576171875
1598.0

```


So what is this data? Probably some kind of bounding box + miscellaneous crap that's not too important. For now let's ignore it and move on to the next piece of data. From where we left of at offset 0x5C, highlight the next 0x38 bytes until the next 0x01. This is some kind of pattern. How do I know? Well, look at the 0x44 in the highlighted code. Then, select that and move to the next 0x44 that you see. Then select that until the next 0x44 that you see. You'll see that each 0x44 is 0x38 bytes away from each other. Let's try reading these 0x38 bytes as unsigned 32-bit integers first.



```
# read next 0x38 bytes of data
#
d01 = xentax.LE_read_uint32(ifile); # 0x04 bytes
d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
d04 = xentax.LE_read_uint32(ifile); # 0x10 bytes
d05 = xentax.LE_read_uint32(ifile); # 0x14 bytes
d06 = xentax.LE_read_uint32(ifile); # 0x18 bytes
d07 = xentax.LE_read_uint32(ifile); # 0x1C bytes
d08 = xentax.LE_read_uint32(ifile); # 0x20 bytes
d09 = xentax.LE_read_uint32(ifile); # 0x24 bytes
d10 = xentax.LE_read_uint32(ifile); # 0x28 bytes
d11 = xentax.LE_read_uint32(ifile); # 0x2C bytes
d12 = xentax.LE_read_uint32(ifile); # 0x30 bytes
d13 = xentax.LE_read_uint32(ifile); # 0x34 bytes
d14 = xentax.LE_read_uint32(ifile); # 0x38 bytes
print(d01);
print(d02);
print(d03);
print(d04);
print(d05);
print(d06);
print(d07);
print(d08);
print(d09);
print(d10);
print(d11);
print(d12);
print(d13);
print(d14);
print('');

```


```
0
0
1784414276
3
0
0
0
0
2
0
65537
0
878

```


I highly doubt that 1784414276 is a uint32. Let's separate it into two uint16 values instead.

```
# read next 0x38 bytes of data
#
d01 = xentax.LE_read_uint32(ifile); # 0x04 bytes
d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
d04 = xentax.LE_read_uint16(ifile); # 0x0E bytes
d05 = xentax.LE_read_uint16(ifile); # 0x10 bytes
d06 = xentax.LE_read_uint32(ifile); # 0x14 bytes
d07 = xentax.LE_read_uint32(ifile); # 0x18 bytes
d08 = xentax.LE_read_uint32(ifile); # 0x1C bytes
d09 = xentax.LE_read_uint32(ifile); # 0x20 bytes
d10 = xentax.LE_read_uint32(ifile); # 0x24 bytes
d11 = xentax.LE_read_uint32(ifile); # 0x28 bytes
d12 = xentax.LE_read_uint32(ifile); # 0x2C bytes
d13 = xentax.LE_read_uint32(ifile); # 0x30 bytes
d14 = xentax.LE_read_uint32(ifile); # 0x34 bytes
d15 = xentax.LE_read_uint32(ifile); # 0x38 bytes 
print(d01);
print(d02);
print(d03);
print(d04);
print(d05);
print(d06);
print(d07);
print(d08);
print(d09);
print(d10);
print(d11);
print(d12);
print(d13);
print(d14);
print(d15);
print('');

```


```
0
0
68
27228
3
0
0
0
0
2
0
65537
0
878

```


Now it's looking good. Now go back to the file and read the next 0x38 bytes. In fact, do it in a loop for 3 three times. If you look at the data after the third time the next piece of data is another one of those bounding box things that we read.

```
    d01 = xentax.LE_read_uint32(ifile); # 0x04 bytes
    d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
    d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
    d04 = xentax.LE_read_uint16(ifile); # 0x0E bytes
    d05 = xentax.LE_read_uint16(ifile); # 0x10 bytes
    d06 = xentax.LE_read_uint32(ifile); # 0x14 bytes
    d07 = xentax.LE_read_uint32(ifile); # 0x18 bytes
    d08 = xentax.LE_read_uint32(ifile); # 0x1C bytes
    d09 = xentax.LE_read_uint32(ifile); # 0x20 bytes
    d10 = xentax.LE_read_uint32(ifile); # 0x24 bytes
    d11 = xentax.LE_read_uint32(ifile); # 0x28 bytes
    d12 = xentax.LE_read_uint32(ifile); # 0x2C bytes
    d13 = xentax.LE_read_uint32(ifile); # 0x30 bytes
    d14 = xentax.LE_read_uint32(ifile); # 0x34 bytes
    d15 = xentax.LE_read_uint32(ifile); # 0x38 bytes 
    print(d01);
    print(d02);
    print(d03);
    print(d04);
    print(d05);
    print(d06);
    print(d07);
    print(d08);
    print(d09);
    print(d10);
    print(d11);
    print(d12);
    print(d13);
    print(d14);
    print(d15);
    print('');

```


```
0
0
68
27228
3
0
0
0
0
2
0
65537
0
878

1
0
0
68
0
0
0
0
0
0
2
1
0
878
1266

1
1
1
68
27228
0
0
0
0
0
2
2
65536
2144
878

```


Now notice something about the last two numbers of each set. (0 + 878) = 878. (878 + 1266) = 2144. (2144 + 878) = ??? You can probably guess what the next set is going to begin with. Because of this, it is my guess that these values are the number of indices to read per surface. Don't know for sure yet until we read all the surface data, but let's check now.

Remember when we loaded the bounding box? What was the first number? What was param01? It was 0. For these surface entries, what is the first number of the three entries we just loaded? 1. Let's write a loop to test to see if we can read this data in a loop.

```

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# move to 0x40
#
ifile.seek(0x40);

#
# read bounding box and surface entries
#
while True:

    type = xentax.LE_read_uint32(ifile);

    if type == 0:
       print('BOUNDING BOX');
       param02 = xentax.LE_read_uint32(ifile);
       param03 = xentax.LE_read_uint16(ifile);
       param04 = xentax.LE_read_uint16(ifile);
       param05 = xentax.LE_read_float16(ifile);
       param06 = xentax.LE_read_float16(ifile);
       param07 = xentax.LE_read_float16(ifile);
       param08 = xentax.LE_read_float16(ifile);
       param09 = xentax.LE_read_float16(ifile);
       param10 = xentax.LE_read_float16(ifile);
       param11 = xentax.LE_read_float16(ifile);
       param12 = xentax.LE_read_float16(ifile);
       print(param02);
       print(param03);
       print(param04);
       print(param05);
       print(param06);
       print(param07);
       print(param08);
       print(param09);
       print(param10);
       print(param11);
       print(param12);
       print('');
    elif type == 1:
       print('SURFACE ENTRY');
       d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
       d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
       d04 = xentax.LE_read_uint16(ifile); # 0x0E bytes
       d05 = xentax.LE_read_uint16(ifile); # 0x10 bytes
       d06 = xentax.LE_read_uint32(ifile); # 0x14 bytes
       d07 = xentax.LE_read_uint32(ifile); # 0x18 bytes
       d08 = xentax.LE_read_uint32(ifile); # 0x1C bytes
       d09 = xentax.LE_read_uint32(ifile); # 0x20 bytes
       d10 = xentax.LE_read_uint32(ifile); # 0x24 bytes
       d11 = xentax.LE_read_uint32(ifile); # 0x28 bytes
       d12 = xentax.LE_read_uint32(ifile); # 0x2C bytes
       d13 = xentax.LE_read_uint32(ifile); # 0x30 bytes
       d14 = xentax.LE_read_uint32(ifile); # 0x34 bytes
       d15 = xentax.LE_read_uint32(ifile); # 0x38 bytes 
       print(d02);
       print(d03);
       print(d04);
       print(d05);
       print(d06);
       print(d07);
       print(d08);
       print(d09);
       print(d10);
       print(d11);
       print(d12);
       print(d13);
       print(d14);
       print(d15);
       print('');
    else:
       print('UNKNOWN ENTRY TYPE:');
       print(type);
       print(ifile.tell());
       break;

#
# close file
#
ifile.close()

```


Oh hell yeah! The data is too long to display here but it works and works well. Very consistent data. Only problem is at the end it terminates with:

```
2
2588

```


Let's go to offset 2588 (0xA1C) and see what's going on. Since the type had to be read, let's actually move to offset 0xA18 instead. As you can see from the picture below, if the first value we read is 2, then we only need to read 0x10 bytes per entry. Wonder what is in store for 2? Let's add it to the code. We'll treat all 0x10 bytes at 4 32-bit uint32 values.

```

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# move to 0x40
#
ifile.seek(0x40);

#
# read bounding box and surface entries
#
while True:

    type = xentax.LE_read_uint32(ifile);

    if type == 0:
       print('BOUNDING BOX');
       param02 = xentax.LE_read_uint32(ifile);
       param03 = xentax.LE_read_uint16(ifile);
       param04 = xentax.LE_read_uint16(ifile);
       param05 = xentax.LE_read_float16(ifile);
       param06 = xentax.LE_read_float16(ifile);
       param07 = xentax.LE_read_float16(ifile);
       param08 = xentax.LE_read_float16(ifile);
       param09 = xentax.LE_read_float16(ifile);
       param10 = xentax.LE_read_float16(ifile);
       param11 = xentax.LE_read_float16(ifile);
       param12 = xentax.LE_read_float16(ifile);
       print(param02);
       print(param03);
       print(param04);
       print(param05);
       print(param06);
       print(param07);
       print(param08);
       print(param09);
       print(param10);
       print(param11);
       print(param12);
       print('');
    elif type == 1:
       print('SURFACE ENTRY');
       d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
       d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
       d04 = xentax.LE_read_uint16(ifile); # 0x0E bytes
       d05 = xentax.LE_read_uint16(ifile); # 0x10 bytes
       d06 = xentax.LE_read_uint32(ifile); # 0x14 bytes
       d07 = xentax.LE_read_uint32(ifile); # 0x18 bytes
       d08 = xentax.LE_read_uint32(ifile); # 0x1C bytes
       d09 = xentax.LE_read_uint32(ifile); # 0x20 bytes
       d10 = xentax.LE_read_uint32(ifile); # 0x24 bytes
       d11 = xentax.LE_read_uint32(ifile); # 0x28 bytes
       d12 = xentax.LE_read_uint32(ifile); # 0x2C bytes
       d13 = xentax.LE_read_uint32(ifile); # 0x30 bytes
       d14 = xentax.LE_read_uint32(ifile); # 0x34 bytes
       d15 = xentax.LE_read_uint32(ifile); # 0x38 bytes 
       print(d02);
       print(d03);
       print(d04);
       print(d05);
       print(d06);
       print(d07);
       print(d08);
       print(d09);
       print(d10);
       print(d11);
       print(d12);
       print(d13);
       print(d14);
       print(d15);
       print('');
    elif type == 2:
       print('WHAT IS THIS?');
       u02 = xentax.LE_read_uint32(ifile);
       u03 = xentax.LE_read_uint32(ifile);
       u04 = xentax.LE_read_uint32(ifile);
       u05 = xentax.LE_read_uint32(ifile);
       print(u02);
       print(u03);
       print(u04);
       print(u05);
       print('');
    else:
       print('UNKNOWN ENTRY TYPE:');
       print(type);
       print(ifile.tell());
       break;

#
# close file
#
ifile.close()

```


```
0
0
68
0
0
0
0
0
0
2
19
0
10966
26

WHAT IS THIS?
20
65536
10992
33

WHAT IS THIS?
19
0
11025
5

WHAT IS THIS?
20
65536
11030
41

WHAT IS THIS?
19
0
11071
36

```


Excellent! Appears to work. Once again, too much data to display, but it appears that this is also a surface entry as well. Once again the last two numbers add up to the first number in the next entry. This might be a special surface or something... we won't know until we load the model later. Notice that the code above still ends in an error.

```
4294967295
4884

```


Let's go to offset 4884 (0x1314). See the 0xFFFFFFFF? That means we hit the end of the surface data and we are finished.



However, notice that after the 0xFFFFFFFF there looks like there are more surfaces to read! I see more 0x44's around. Since the first uint32 after the 0xFFFFFFFF is a 0, the next entry is a bounding box. Let's ignore the 0xFFFFFFFF and continue processing surfaces. Here's the code:

```

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# move to 0x40
#
ifile.seek(0x40);

#
# read bounding box and surface entries
#
while True:

    type = xentax.LE_read_uint32(ifile);

    if type == 0:
       print('BOUNDING BOX');
       param02 = xentax.LE_read_uint32(ifile);
       param03 = xentax.LE_read_uint16(ifile);
       param04 = xentax.LE_read_uint16(ifile);
       param05 = xentax.LE_read_float16(ifile);
       param06 = xentax.LE_read_float16(ifile);
       param07 = xentax.LE_read_float16(ifile);
       param08 = xentax.LE_read_float16(ifile);
       param09 = xentax.LE_read_float16(ifile);
       param10 = xentax.LE_read_float16(ifile);
       param11 = xentax.LE_read_float16(ifile);
       param12 = xentax.LE_read_float16(ifile);
       print(param02);
       print(param03);
       print(param04);
       print(param05);
       print(param06);
       print(param07);
       print(param08);
       print(param09);
       print(param10);
       print(param11);
       print(param12);
       print('');
    elif type == 1:
       print('SURFACE ENTRY TYPE 1');
       d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
       d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
       d04 = xentax.LE_read_uint16(ifile); # 0x0E bytes
       d05 = xentax.LE_read_uint16(ifile); # 0x10 bytes
       d06 = xentax.LE_read_uint32(ifile); # 0x14 bytes
       d07 = xentax.LE_read_uint32(ifile); # 0x18 bytes
       d08 = xentax.LE_read_uint32(ifile); # 0x1C bytes
       d09 = xentax.LE_read_uint32(ifile); # 0x20 bytes
       d10 = xentax.LE_read_uint32(ifile); # 0x24 bytes
       d11 = xentax.LE_read_uint32(ifile); # 0x28 bytes
       d12 = xentax.LE_read_uint32(ifile); # 0x2C bytes
       d13 = xentax.LE_read_uint32(ifile); # 0x30 bytes
       d14 = xentax.LE_read_uint32(ifile); # 0x34 bytes
       d15 = xentax.LE_read_uint32(ifile); # 0x38 bytes 
       print(d02);
       print(d03);
       print(d04);
       print(d05);
       print(d06);
       print(d07);
       print(d08);
       print(d09);
       print(d10);
       print(d11);
       print(d12);
       print(d13);
       print(d14);
       print(d15);
       print('');
    elif type == 2:
       print('SURFACE ENTRY TYPE 2');
       u02 = xentax.LE_read_uint32(ifile);
       u03 = xentax.LE_read_uint32(ifile);
       u04 = xentax.LE_read_uint32(ifile);
       u05 = xentax.LE_read_uint32(ifile);
       print(u02);
       print(u03);
       print(u04);
       print(u05);
       print('');
    elif type == 0xFFFFFFFF:
       print('SECTION ENDING 0XFFFFFFFF');
       print('');
    else:
       print('UNKNOWN ENTRY TYPE:');
       print(type);
       print(ifile.tell());
       break;

#
# close file
#
ifile.close()

```


```
1065353215
5312

```


Of course, we still get an error when it comes to the end of the surface data, at offset 5312 (0x14C0). Can we detect the end of the surface entries? Yes. Look up at the top of the file and look at the highlighted uint32. The data at 0x20 marks the end of the surface entries. So when we read a 0xFFFFFFFF type, we can check to see if we have reached the end of the surface entries. If so, we can terminate the loop without worrying about errors. Once finished, let's also sum up the last number on each surface entry and see what they add up to. Here is the code:



```

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# read header offsets
#
ifile.seek(0x10);
offset01 = xentax.LE_read_uint32(ifile);
offset02 = xentax.LE_read_uint32(ifile);
offset03 = xentax.LE_read_uint32(ifile);
offset04 = xentax.LE_read_uint32(ifile);
offset05 = xentax.LE_read_uint32(ifile); # offset to bone data
offset06 = xentax.LE_read_uint32(ifile);
offset07 = xentax.LE_read_uint32(ifile);
offset08 = xentax.LE_read_uint32(ifile);
offset09 = xentax.LE_read_uint32(ifile);
offset10 = xentax.LE_read_uint32(ifile);
offset11 = xentax.LE_read_uint32(ifile);

#
# move to 0x40
#
ifile.seek(0x40);

#
# sum of surface entries
#
surface_sum = 0;

#
# read bounding box and surface entries
#
while True:

    type = xentax.LE_read_uint32(ifile);

    if type == 0:
       print('BOUNDING BOX');
       param02 = xentax.LE_read_uint32(ifile);
       param03 = xentax.LE_read_uint16(ifile);
       param04 = xentax.LE_read_uint16(ifile);
       param05 = xentax.LE_read_float16(ifile);
       param06 = xentax.LE_read_float16(ifile);
       param07 = xentax.LE_read_float16(ifile);
       param08 = xentax.LE_read_float16(ifile);
       param09 = xentax.LE_read_float16(ifile);
       param10 = xentax.LE_read_float16(ifile);
       param11 = xentax.LE_read_float16(ifile);
       param12 = xentax.LE_read_float16(ifile);
       print(param02);
       print(param03);
       print(param04);
       print(param05);
       print(param06);
       print(param07);
       print(param08);
       print(param09);
       print(param10);
       print(param11);
       print(param12);
       print('');
    elif type == 1:
       print('SURFACE ENTRY TYPE 1');
       d02 = xentax.LE_read_uint32(ifile); # 0x08 bytes
       d03 = xentax.LE_read_uint32(ifile); # 0x0C bytes
       d04 = xentax.LE_read_uint16(ifile); # 0x0E bytes
       d05 = xentax.LE_read_uint16(ifile); # 0x10 bytes
       d06 = xentax.LE_read_uint32(ifile); # 0x14 bytes
       d07 = xentax.LE_read_uint32(ifile); # 0x18 bytes
       d08 = xentax.LE_read_uint32(ifile); # 0x1C bytes
       d09 = xentax.LE_read_uint32(ifile); # 0x20 bytes
       d10 = xentax.LE_read_uint32(ifile); # 0x24 bytes
       d11 = xentax.LE_read_uint32(ifile); # 0x28 bytes
       d12 = xentax.LE_read_uint32(ifile); # 0x2C bytes
       d13 = xentax.LE_read_uint32(ifile); # 0x30 bytes
       d14 = xentax.LE_read_uint32(ifile); # 0x34 bytes
       d15 = xentax.LE_read_uint32(ifile); # 0x38 bytes 
       print(d02);
       print(d03);
       print(d04);
       print(d05);
       print(d06);
       print(d07);
       print(d08);
       print(d09);
       print(d10);
       print(d11);
       print(d12);
       print(d13);
       print(d14);
       print(d15);
       surface_sum += d15;
       print('');
    elif type == 2:
       print('SURFACE ENTRY TYPE 2');
       u02 = xentax.LE_read_uint32(ifile);
       u03 = xentax.LE_read_uint32(ifile);
       u04 = xentax.LE_read_uint32(ifile);
       u05 = xentax.LE_read_uint32(ifile);
       print(u02);
       print(u03);
       print(u04);
       print(u05);
       surface_sum += u05;
       print('');
    elif type == 0xFFFFFFFF:
       print('SECTION ENDING 0XFFFFFFFF');
       print('');
       if ifile.tell() == offset05:
          break;
    else:
       print('UNKNOWN ENTRY TYPE:');
       print(type);
       print(ifile.tell());
       break;

print('The number of surface values summed up = ');
print(surface_sum);
	   
#
# close file
#
ifile.close()

```


```
13566

```


What do you know? 13,566 is exactly the number of indices that we have (see previous steps where we loaded the geometry). We now have our surfaces and we can insert them into an array. The following code loads all surface data and displays it.

```

class SurfaceInfo:
    def __init__(self, si, sl):
        self.startIndex = si;
        self.stripLength = sl;

#
# open input file 
#
ifile = open('nina1u.chr', 'rb');

#
# read header offsets
#
ifile.seek(0x10);
offset01 = xentax.LE_read_uint32(ifile);
offset02 = xentax.LE_read_uint32(ifile);
offset03 = xentax.LE_read_uint32(ifile);
offset04 = xentax.LE_read_uint32(ifile);
offset05 = xentax.LE_read_uint32(ifile); # offset to bone data
offset06 = xentax.LE_read_uint32(ifile);
offset07 = xentax.LE_read_uint32(ifile);
offset08 = xentax.LE_read_uint32(ifile);
offset09 = xentax.LE_read_uint32(ifile);
offset10 = xentax.LE_read_uint32(ifile);
offset11 = xentax.LE_read_uint32(ifile);

#
# READ SURFACE DATA
#
surface_array = [];
ifile.seek(0x40);
while True:
    type = xentax.LE_read_uint32(ifile);
    if type == 0:
       param02 = xentax.LE_read_uint32(ifile);
       param03 = xentax.LE_read_uint16(ifile);
       param04 = xentax.LE_read_uint16(ifile);
       param05 = xentax.LE_read_float16(ifile);
       param06 = xentax.LE_read_float16(ifile);
       param07 = xentax.LE_read_float16(ifile);
       param08 = xentax.LE_read_float16(ifile);
       param09 = xentax.LE_read_float16(ifile);
       param10 = xentax.LE_read_float16(ifile);
       param11 = xentax.LE_read_float16(ifile);
       param12 = xentax.LE_read_float16(ifile);
    elif type == 1:
       d02 = xentax.LE_read_uint32(ifile);
       d03 = xentax.LE_read_uint32(ifile);
       d04 = xentax.LE_read_uint16(ifile);
       d05 = xentax.LE_read_uint16(ifile);
       d06 = xentax.LE_read_uint32(ifile);
       d07 = xentax.LE_read_uint32(ifile);
       d08 = xentax.LE_read_uint32(ifile);
       d09 = xentax.LE_read_uint32(ifile);
       d10 = xentax.LE_read_uint32(ifile);
       d11 = xentax.LE_read_uint32(ifile);
       d12 = xentax.LE_read_uint32(ifile);
       d13 = xentax.LE_read_uint32(ifile);
       d14 = xentax.LE_read_uint32(ifile);
       d15 = xentax.LE_read_uint32(ifile); 
       surface_array.append(SurfaceInfo(d14, d15));
    elif type == 2:
       u02 = xentax.LE_read_uint32(ifile);
       u03 = xentax.LE_read_uint32(ifile);
       u04 = xentax.LE_read_uint32(ifile);
       u05 = xentax.LE_read_uint32(ifile);
       surface_array.append(SurfaceInfo(u04, u05));
    elif type == 0xFFFFFFFF:
       if ifile.tell() == offset05:
          break;
    else:
       print('UNKNOWN ENTRY TYPE:');
       print(type);
       print(ifile.tell());
       break;

#
# LIST SURFACES
#
print('SURFACE INDICES');
for item in surface_array:
    print(item.stripLength);
 
#
# close file
#
ifile.close()

```


```
SURFACE INDICES
878
1266
878
577
88
95
31
126
41
577
96
99
115
178
116
743
12
21
154
34
18
14
102
72
26
1251
98
743
110
113
271
162
173
30
186
60
212
1064
34
102
26
33
5
41
36
12
12
28
28
28
28
18
23
38
38
34
30
22
22
317
8
164
20
94
15
36
17
36
16
16
30
4
27
8
40
11
22
9
20
25
28
8
16
14
30
6
40
33
76
8
58
302
186
18
122
18
200

```


Well now, here comes the hard part... putting stuff from this tutorial section and the previous tutorial section all together! All we have to do is loop through the surface information and save tristrips of specific lengths determined by the data we saved in SurfaceInfo.stripLength. Here is the code to load nina1u.chr by individual surfaces. Of course, even though we divided the tristrips into surfaces, the geometry is still messed up! See the picture after the code.

```

```
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-09T04:26:21+00:00
- Post Title: Tekken Hybrid

Use noesis.



Models + textures plz.

Whenever I think console games, I imagine complicated and awkward data structures.

But that tekken game doesn't seem too bad. Do a lot of PS3 games look like that?
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-09T06:35:09+00:00
- Post Title: Tekken Hybrid

No not all ps3 games look this easy. Take for instance ni no kuni. Dat file contains zarc files. Zarc files contain hpk files. Hpk files contain pkchr files. Pkchr files contain all kinds of other files. These other files contain crazy vertex and image formats. It would probably take me a full month to figure out how to rip stuff from that game so I just move on.
## Post #15
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-09T06:37:13+00:00
- Post Title: Tekken Hybrid

> Reply from howfie
>
> Step #2: See If Rich Has Already Done It

First thing to do is to see if Rich has already done it. In general, I try not to step on something somebody else is working on or has already done. Tekken is a AAA-game and I tend to leave these alone since usually other guys tend to pick them up before I can even save up enough money to buy the game! I tried loading the CHR files in Noesis and it was a no go so I think we're good here.
Haha. Tekken 6 is the only Tekken I've looked at, and it was mostly because it happened to use a format very similar to Soul Calibur 4. While I haven't looked, I'd bet money that anything Tekken 5 or earlier has no real resemblance.

> Reply from gjinka
>
> Well you have to think both ways: over the last 10 years more complex compression and encryption algorithms were probably created. And also I think as game budgets rise the developers become more likely to reinvent the wheel by creating custom encryption/compression, or add extra protection.
The real reason a lot of games don't use serious compression/encryption now is the same reason they didn't back then - it still imposes a totally unnecessary load time (and possibly memory) overhead. The trend of console vendors offering compression/encryption libraries to developers has been on the rise, but in that case, it tends to be very universal and we only need to figure out how to crack it once. It's otherwise pretty hard as a game developer to justify the runtime overhead of rolling your own compression/encryption scheme, and at most competent developers will typically take the minimal approach there. (FF13-2 being a recent example, they encrypted their file table but didn't bother encrypting actual data probably because of the rather large overhead you would have if you wanted to AES128-decrypt all of your data on load)

On the whole, older games are usually way more difficult to figure out. Especially games that came around before everyone was developing for fixed function graphics pipelines, because they could store and render data in pretty much any form that they wanted, and some even went so far as doing crazy shit like directly scanline-rendering basic primitive types and patches. We're going to be moving back toward that in another generation or 2, but for now it's smooth sailing and we can pretty much always expect to find runtime data in the form of raw triangles and vertices. You also generally don't even need to know about anything particularly next-gen to figure out next-gen data. It helps if you can recognize a tangent vector/matrix when you see one, for example, but you really don't need to know what it is if all you're looking to do is get the raw triangle/vertex data out for whatever your purposes may be. If you want to actually create an exporter *to* that format, though, then that's a lot different and you'll need to have a pretty good idea of what every piece of data in the file actually is.
## Post #16
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-09T07:19:22+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

OK, convinced   

(why do you think it will become more complicated in the future though? More shader programming? I don't see anything revolutionary new in the new DirectXs and OpenGLs)

Anyway, we should post a new topic in the 3D section. I could change the topic title, but there is no archive format to figure out. There are tools out there to extract PKGs.

And I'm a proud Python user. I usually use my game engine for testing, but I can use the old Blender too. I don't know anything about Noesis python library. I couldn't find any docs.
## Post #17
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-09T07:31:43+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

> Reply from gjinka
>
> (why do you think it will become more complicated in the future though? More shader programming? I don't see anything revolutionary new in the new DirectXs and OpenGLs)
It's already possible to use custom data types/sets (to some extent, it isn't exactly practical yet) with the programmable shader pipelines we have today, but it will become far more practical and desirable as our data sets continue to grow and dedicated graphics hardware becomes more versatile. Eventually, it's just going to be a lot more reasonable to scanline/raytrace directly through your data set instead of having to convert it to fixed triangles before you feed it to the GPU.

> Reply from gjinka
>
> And I'm a proud Python user. I usually use my game engine for testing, but I can use the old Blender too. I don't know anything about Noesis python library. I couldn't find any docs.
Noesis documentation is pretty minimal, it's still on my todo list to make a real set of documents and examples. For now, there's a __NPReadMe.txt file that comes with Noesis containing all of the functions and constants with brief descriptions and parameter definitions, as well as a plethora of example scripts, and chrrox has posted some very useful tutorials in the tutorials section here on Xentax.
## Post #18
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-09T08:11:15+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

If you use docstrings, you can just use doxygen to generate a html documentation.

EDIT:
@howfie: are you sure that's an obvious index buffer? Looks like ASCII character codes in nice order.

I got the obvious stuff:

```

85 A8 A4 2D - header
char[8]     - file name?
uint[4]     - always 64?
```


Can I ask a friendly mod to cut this topic from the part we talk about tekken Hybrid and move it to the 3d section?
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-09T09:44:24+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

It sure is. That ASCII looking table is the first thing I look for. It says, "Index Buffer, and I'm probably going to be easy to rip." If it's not there in the model file, I usually give up right away. There's one game company that purposely obfuscates their index buffer (was it TTARCH files I don't remember) and as far as I know, no one has ripped models from those games yet.

BTW, python it is then ha ha ha. It's been several years since I've messed with it (using Panda errrr I mean Crap3D), but I'll get used to it again.
## Post #20
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-09T09:46:06+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

Doxygen isn't useful, as the necessary information and basic examples (outside of their contextual uses in actual scripts) simply don't exist. The Noesis Python API is defined in C, and the above-mentioned .txt file contains all of the info you would otherwise glean from a custom parsing of the source code. As a side note, I hate how cluttered the internet has become with people who just blindly run doxygen over their codebases and call it "documentation", despite the fact that it's completely devoid of meaningful or useful content - I'd rather it didn't exist in the first place, to save me looking through it for something useful. Seems to happen every time I google for documentation on an opensource library these days.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-09T12:27:58+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

> Reply from gjinka
>
> 
And I'm a proud Python user. I usually use my game engine for testing, but I can use the old Blender too. I don't know anything about Noesis python library. I couldn't find any docs.

I find myself using only like 5-6 functions in noesis to get most of the stuff done.
Mainly cause I don't know what to do with the rest of the data, but I don't really need to use too many things for simple things like exporting geometry.

But ya, 5-6 functions is enough to get geometry out. Maybe another 2-3 functions would get bones and weights, and maybe another 2-3 to get animations.

You can use this template that I wrote. It provides a simple model loading function based on the example provided and should get most stuff done. Once you realize you need more functions to render more stuff you should be familiar with the library enough.

[http://xtsukihime.webs.com/Noesis%20Plu ... emplate.py](http://xtsukihime.webs.com/Noesis%20Plugins/Template/rapi_model_template.py)

This is assuming you're using the rapi function calls. .

You can look at how repetitive the plugins end up being, especially if you start splitting up everything into different functions:

[http://xtsukihime.webs.com/noesisplugins.htm](http://xtsukihime.webs.com/noesisplugins.htm)

Note: the model template up there is not tested. I don't actually use that one, because it forces me to remember API functions like getting the input name, getting the directory path of the input, etc. It was just me taking the template I use, removing all references to the custom object, and copying the constructor over.

I use this one: [http://xtsukihime.webs.com/Noesis%20Plu ... e_sanae.py](http://xtsukihime.webs.com/Noesis%20Plugins/Template/rapi_model_template_sanae.py)
Which requires the package in my sig. It's pretty much the same thing except I can add stuff that tailor to my own preferences also in an attempt to write readable code (eg: self.filename vs rapi.getLocalFileName(rapi.getInputName())
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-09T21:04:16+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

Updated post on first page with some python code. I'll be gone for a couple days and if anyone wants to add stuff gooooooo right ahead. I think the data before the vertex data is the skeleton data. Each 0x40 byte entry contains 3 floats and then some other data... Probably a half-float matrix maybe I dunno. The surface stuff is probably near the top of the file. Sucks it doesn't look like they are given names like hair, head, body, knifepouch, etc.
## Post #23
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T07:21:53+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

Good job and thanks.
I'll ask the mods again to cut this topic from howfie's first post and move it to 3d section, or move the whole topic and I'll edit my first post explaining what happened.

@howfie thanks again.
I'll make a dumb student guess. We are reading the whole vertex buffer at once. The models are probably split into multiple meshes, each mesh entry probably mentions the size, offset and type of the vertex and index buffer subpart. There are probably two types: triangle and triangle strip index buffer. As to where these 'entries' are, I don't know. Anyway, just a guess from what I learned in the DOAU topic.
## Post #24
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-10T08:56:33+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

we can move it ourselves once we're finished.

yes, vertex buffer is one big chunk of data in the file and can be read all at once. and yep, there are more than likely multiple meshes. even though the index buffer is also one big chunk of data in the file too, it is probably divided into parts, typically called surfaces or groups or whatever you want to call them.

so say there are 10,000 indices in the index buffer. the first 1,000 could be for the face. the next 4,000 could be for the body, the next 1,000 for the hair, etc. etc. at the beginning of each group you have to stop the currently running triangle strip. i have a feeling it's at the beginning of the file but I am far from my dev machine on a crappy laptop at the moment he he he. did the python code work for you?
## Post #25
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T10:51:08+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

Yes very likely in the beginning of the file.
Good job on the Python OBJ script.

Sad that the struct module doesnt support half floats. Maybe we could contact the Python devs to add it to the module.

Anyway, yeah, I'm right behind you
## Post #26
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-01-10T17:51:31+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

doesn't tekken 3 use tmd?
## Post #27
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-10T19:57:29+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

People haven't even told me how you get files out of PSX ISOs. Even if I would do that the files are in archives. If we could figure out the archive format and the files are really tmd (I have no idea about this format) then maybe we could get them in Milkshape.
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T20:04:42+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

> Reply from gjinka
>
> Yes very likely in the beginning of the file.
Good job on the Python OBJ script.

Sad that the struct module doesnt support half floats. Maybe we could contact the Python devs to add it to the module.

Anyway, yeah, I'm right behind you

Noesis supports half-floats [viewtopic.php?p=64094#p64094](http://forum.xentax.com/viewtopic.php?p=64094#p64094)
## Post #29
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-11T23:57:40+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

> Reply from viperzerofsx
>
> doesn't tekken 3 use tmd?

I don't think he knows how to properly rip PSX games. I think there was a PS2 version of the game too. LOL I don't know how to rip from PSX games either. Don't have a PSOne.

BTW, can somebody upload nina1u.chr sample. I am far from home for another day or two and in order to work on it I need the file. And did anyone check the preview part hybrid? That one is going to be hard to rip from.
## Post #30
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T01:17:49+00:00
- Post Title: Re: my first attempt at file format exploring (Tekken 3 form

Most PSX games just use a plain old ISO 9960 filesystem, so you can pop them into any CD-ROM drive and copy the files right off.

Just like PS2 games, however, some PSX games will store custom filesystem structures on the disc at a given offset, and when that happens it's usually a completely proprietary filesystem that you have to figure out yourself. In that case, I'll typically just rip a direct binary image of the entire disc and sift through that for a filesystem header. This practice is actually more common in PS2 games than it is in PSX games, though, from what I've witnessed.

It's also true that rather than actually looking into the CD-ROM filesystem, lots of PSX games will actually hardcode sector offsets and sizes for each file. Usually in the program binary itself. Which means that even if you modify the filesystem and reburn the disc, the game will still be looking for the data in the same sectors, and will probably fail because of your modification to the disc contents without modifying its internal sector table. Just something to be aware of, doubtful you'll run into issues there unless you want to actually mod games. It's theoretically possible for the CD-ROM filesystem to give you invalid offsets to the files you see on a disc, but I've never seen this actually happen.
## Post #31
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-12T07:58:26+00:00
- Post Title: Re: Tekken Hybrid

So I was right. Thats why Daemon failed.

@howfie: [http://www.2shared.com/file/QReIYGqm/nina1u.html](http://www.2shared.com/file/QReIYGqm/nina1u.html)
## Post #32
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T21:10:21+00:00
- Post Title: Re: Tekken Hybrid

> Reply from gjinka
>
> So I was right. Thats why Daemon failed.
Quite the contrary, actually. Daemon Tools or any other virtual disc image software should work fine and for most PSX games and will allow you to copy data files straight out of the image. If it's failing then you probably have a screwed up disc image, although it's also possible you've stumbled upon an unusual game without a standard filesystem.
## Post #33
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T23:57:24+00:00
- Post Title: Re: Tekken Hybrid

So I got a copy of tekken 3, mounted it, saw some files, but can only look at two of them (SCES_012.37, TEKKEN3.BNS)
The rest are the same situation.
## Post #34
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-13T11:10:20+00:00
- Post Title: Re: Tekken Hybrid

> Reply from MrAdults
>
> 
Quite the contrary, actually ... If it's failing then you probably have a screwed up disc image. filesystem.
It's probably not a screwed up disk because I tried two and finale00 tried himself, 

> although it's also possible you've stumbled upon an unusual game without a standard filesystem.
And that's what I assumed, doesn't that make my assumption right?

Anyway, it seems somewhat similar to the standard ISO because few small file can be read.
You can have a look at a 4mb slice of the file I posted in the first post if you want. I'm not sure if it's worth it, though, Tekken Hybrid contains Tekken Tag Tournment HD, which has the same models from Tekken 3 (same design), only highpoly.
## Post #35
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-13T12:23:00+00:00
- Post Title: Re: Tekken Hybrid

Almost there... I figured out how the model is divided into surfaces... however... the tristrip format is really strange. For example, nina has the following surface indices:

```
number of vertices = 5000

size of index buffer in bytes = 27132
number of indices = 13566

sum of surface indices = 13566
indices = 13566
leftover = 0

surface indices = 878
surface indices = 1266
surface indices = 878
surface indices = 577
surface indices = 88
surface indices = 95
surface indices = 31
surface indices = 126
surface indices = 41
surface indices = 577
surface indices = 96
surface indices = 99
surface indices = 115
surface indices = 178
surface indices = 116
surface indices = 743
surface indices = 12
surface indices = 21
surface indices = 154
surface indices = 34
surface indices = 18
surface indices = 14
surface indices = 102
surface indices = 72
surface indices = 26
surface indices = 1251
surface indices = 98
surface indices = 743
surface indices = 110
surface indices = 113
surface indices = 271
surface indices = 162
surface indices = 173
surface indices = 30
surface indices = 186
surface indices = 60
surface indices = 212
surface indices = 1064
surface indices = 34
surface indices = 102
surface indices = 26
surface indices = 33
surface indices = 5
surface indices = 41
surface indices = 36
surface indices = 12
surface indices = 12
surface indices = 28
surface indices = 28
surface indices = 28
surface indices = 28
surface indices = 18
surface indices = 23
surface indices = 38
surface indices = 38
surface indices = 34
surface indices = 30
surface indices = 22
surface indices = 22
surface indices = 317
surface indices = 8
surface indices = 164
surface indices = 20
surface indices = 94
surface indices = 15
surface indices = 36
surface indices = 17
surface indices = 36
surface indices = 16
surface indices = 16
surface indices = 30
surface indices = 4
surface indices = 27
surface indices = 8
surface indices = 40
surface indices = 11
surface indices = 22
surface indices = 9
surface indices = 20
surface indices = 25
surface indices = 28
surface indices = 8
surface indices = 16
surface indices = 14
surface indices = 30
surface indices = 6
surface indices = 40
surface indices = 33
surface indices = 76
surface indices = 8
surface indices = 58
surface indices = 302
surface indices = 186
surface indices = 18
surface indices = 122
surface indices = 18
surface indices = 200

```


Now this is where things get strange... the first surface, which are her breasts and upper back triangles, says there are 878 indices used, which means 876 triangles total. When rendered as a typical tristrip, all the triangles are there and are perfect, however, it appears that after a degenerate triangle occurs in the tristrip (which is quite common), the winding tends to, but not always, reverses itself, resulting in the following model (degenerate triangles have been removed).



Of course, if I render this as double sided, you see this:



It's really weird... there also appears to be duplicate surfaces... if I take one of them and flip it it seems to generate the right model. Ha ha ha, what a weird, wasteful way of doing this.
## Post #36
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-13T16:02:53+00:00
- Post Title: Re: Tekken Hybrid

Got textures now too... simply just uncompressed headerless DDS. still can't figure out the tri-strip problem however...
## Post #37
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-13T17:03:12+00:00
- Post Title: Re: Tekken Hybrid

Can you remind me what degenerate triangles are? You say they appear normal when filpped, which sounds like a normals issue.

Good job. Is there anything left in the file. Please post where stuff are (like a wiki) when you get the time.
## Post #38
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-13T21:08:10+00:00
- Post Title: Re: Tekken Hybrid

> Reply from gjinka
>
> And that's what I assumed, doesn't that make my assumption right?
Nope. That has nothing to do with whether Daemon Tools can successfully mount it. If you can't mount it then you've found quite a rarity amongst PSX games or you have a bad rip. If you can mount it but don't see files representing all of the data, then you simply have a case where the game is accessing additional data from extra-filesystem sectors.

> Reply from gjinka
>
> You can have a look at a 4mb slice of the file I posted in the first post if you want. I'm not sure if it's worth it, though, Tekken Hybrid contains Tekken Tag Tournment HD, which has the same models from Tekken 3 (same design), only highpoly.
From what I read, all you posted was the first 4MB of the actual disc image, which isn't particularly useful. I also don't have the disc myself, I only have Tekken Tag Tournament for PS2, which exposes all of the data directly through the standard disc filesystem.
## Post #39
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-13T22:19:36+00:00
- Post Title: Re: Tekken Hybrid

> Reply from gjinka
>
> Can you remind me what degenerate triangles are? You say they appear normal when filpped, which sounds like a normals issue.
Good job. Is there anything left in the file. Please post where stuff are (like a wiki) when you get the time.

A degenerate triangle is a triangle that has lost one or more dimensions. A non-degenerate triangle can only be drawn on a plane and its area is never zero. So triangle indices 0-1-2 marks a full triangle. 2-2-3 marks a degenerate one because now you don't have a triangle, you have a line since only two points are used to define the triangle. 3-3-3 is also degenerate since it's  point. They commonly occur in tri-strips so they can change direction and skip over spaces. Degenerate triangles are also important in the optimization algorithm of Nelder and Mead.

Yes, I haven't processed the skeleton yet. That is easy too... it's a header section followed by 0x40 byte entries where the first 3 floats per entry are the joint locations and the rest of the data is some kind of matrix. It is the only thing left in the file. Animations are stored somewhere else. These parts comes last. I will update post when I fix the tri-strip problem.
## Post #40
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T22:45:57+00:00
- Post Title: Re: Tekken Hybrid

Oh, that's why I see a bunch of repeating indices all over the place.
Is there a common algorithm for processing those kinds of index buffers?

More over, you should add that to the wiki!
## Post #41
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-13T23:06:53+00:00
- Post Title: Re: Tekken Hybrid

here is an example loop in max its pretty easy to follow.

StartDirection = -1
f1 = (ReadBEword f)
f2 = (ReadBEword f) 
FaceDirection = StartDirection
while (ftell f) < (END) Do (
f3 = (ReadBEword f)
if (f3==0xFFFF) then (
f1 = (ReadBEword f)
f2 = (ReadBEword f)
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
if FaceDirection > 0 then append Face_array [(f1),(f2),(f3)]
else append Face_array [(f1),(f3),(f2)]
)
f1 = f2
f2 = f3
)  
)
## Post #42
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-14T07:42:57+00:00
- Post Title: Re: Tekken Hybrid

> Reply from MrAdults
>
> Nope. That has nothing to do with whether Daemon Tools can successfully mount it. If you can't mount it then you've found quite a rarity amongst PSX games or you have a bad rip.
What? You are saying the same thing as last time.
I can't add anything more to what I've said:

> MrAdults wrote:
>
> Quite the contrary, actually ... If it's failing then you probably have a screwed up disc image. filesystem.
>
> It's probably not a screwed up disk because I tried two and finale00 tried himself, 
>
> although it's also possible you've stumbled upon an unusual game without a standard filesystem. 
>
> And that's what I assumed, doesn't that make my assumption right?

> If you can mount it but don't see files representing all of the data, then you simply have a case where the game is accessing additional data from extra-filesystem sectors.
"Extra filesystem sector"?
## Post #43
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-14T22:42:06+00:00
- Post Title: Re: Tekken Hybrid

Ok just panning out some thoughts... this is what's going on... all of a sudden the tristrip draws flipped triangles. It's not clear what the reset condition is because sometimes it does this after degenerates, but sometimes not. In the example above, the strip flips after 4 degenerates. It looks like 3 in the picture but LightWave says there's 4 so . Here's the data:

```
03 00 04 00 05 00
06 00 07 00 08 00
09 00 0A 00 0B 00
0C 00 0D 00 0E 00
0F 00 10 00 11 00
12 00 13 00 14 00
15 00 16 00 17 00
18 00 19 00 1A 00
1B 00 1C 00 1D 00
1E 00 1F 00 20 00
21 00 21 00 22 00
22 00 23 00 02 00
24 00

degenerate: 20 00 21 00 21 00
degenerate: 21 00 21 00 22 00
degenerate: 21 00 22 00 22 00
degenerate: 22 00 22 00 23 00
strip flip: 22 00 23 00 02 00

```


Now let's move on to the next strip flip occurrence and see if something is in common. Well what do you know... it doesn't flip after a degenerate this time!



So what's the data look like? As you can see... four consecutive degenerates again, but this time, the strip doesn't flip.

```
40 00 40 00 41 00
41 00 42 00 43 00
44 00 45 00 46 00

degenerate: 3F 00 40 00 40 00
degenerate: 40 00 40 00 41 00
degenerate: 40 00 41 00 41 00
degenerate: 41 00 41 00 42 00
stip noflip: 41 00 41 00 42 00

```


So there's a dead end there. But as I mentioned before, the chest area geometry appears twice in surface #0 and in surface #2. Here is the surface data for those two things at the beginning of the file. Notice the duplicate 27228 values. That appears to be an identifier for the chest. Sometimes that identifier value is 0 which means that the surface doesn't appear more than once. This is the case for her arms.

```
0
0
68 (always 68)
27228 (chest identifier)
3
0
0
0
0
2
0 (texture identifier)
65537
0 (offset)
878 (number of indices in surface)

```


```
1
1
68 (always 68)
27228 (chest identifier)
0
0
0
0
0
2
2 (texture identifier)
65536
2144 (offset)
878 (number of indices in surface)

```


The only real difference between surface 0 and surface 2 is that they use different textures. The number 3 after the chest identifier probably indicates surface 0 is some type of effect surface since the texture appears to be some kind of lightmap or something? Not sure.

Surface 0 uses:


Surface 2 uses:


So we're back to square one... each surface should draw the geometry correctly without the problem with the strips. It's definitely not a front/back surface type of thing. So guess what? It is time to give up lol. I'm going to conclude that this game uses double-sided polygons and that the triangle strips are fine. However, modelers like lightwave and maya are going to only use the vertex normals from the OBJ export for lighting and not for polygon direction. So in other words, when you load the model into a modeler you are going to see crap if using OBJ.
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-15T01:29:48+00:00
- Post Title: Re: Tekken Hybrid

Fixed! Had to write a function that flips triangles if computed normals do not match up with the average of the vertex normals. Almost ready for release.
## Post #45
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T01:34:06+00:00
- Post Title: Re: Tekken Hybrid

Nice.

What complicated face parsing
## Post #46
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-01-15T08:39:40+00:00
- Post Title: Re: Tekken Hybrid

Excuse me if this is considered spamming on here, but I just joined to let you Mr Howfie know what a hero you are.
I've been waiting almost 12 years for what you're currently working on. THANK YOU!!!   This sounds very dramatic because it is   
I'm so looking forward to seeing this released,... obviously
## Post #47
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-15T09:14:59+00:00
- Post Title: Re: Tekken Hybrid

no it's not spamming. i'm amazed at how many people actually want to see classic models. however, take note, this is not the classic tekken models. these models are from tekken tag tournament 2 HD from Tekken Hybrid, which was released a few months ago. the semi-final release will be in a couple days. I have to make sure that the code works for all models.
## Post #48
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-01-15T11:07:37+00:00
- Post Title: Re: Tekken Hybrid

> Reply from howfie
>
> however, take note, this is not the classic tekken models. these models are from tekken tag tournament 2 HD from Tekken Hybrid

The images you posted are from tekken tag (1), moreover from the HD rerelease of the original title, which has me even more excited.

The pictures of the Nina model you posted, I've been looking for that particular model for all these years. You can't possibly imagine the look on my face when I stumbled over this thread and your posts in particular. 

> Reply from howfie
>
> i'm amazed at how many people actually want to see classic models.

I've seen a lot of people asking for the tekken tag models. I'm not the only one you're making extremely happy with this!

Still can't believe someone finally found a way to extract these models...
Can't wait to see more updates from you!!!
## Post #49
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-15T13:11:50+00:00
- Post Title: Re: Tekken Hybrid

Python scripts are ready for beta testing. Download attached file.

Open up tekken.py and change the filename from 'nina1u' to some other filename to load another model (look at line 32 and edit that).
Run python on tekken.py.
xentax.py must be located in same place as tekken.py.
Load OBJ file in maya or max.

Note: There is duplicate geometry that uses different textures. Alternate outfits or effects? Not sure but it's easy to get rid of.


[tekken.7z](https://xentaxbackup.github.io/file/4988_tekken.7z)
## Post #50
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-15T13:54:55+00:00
- Post Title: Re: Tekken Hybrid

I'm thinking about removing the vertex normals from the OBJ file so your modeler can compute them instead. Tekken's normals are screwy.
## Post #51
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-15T14:08:37+00:00
- Post Title: Re: Tekken Hybrid

Maybe the normals are stored differently, I don't know, maybe not as vectors but radians or eulear or some other crazy way.

Anyway, most 3d modellers will recompute the normals anyway, during import and modelling.

Thanks a lot. I'll study this format with your script, will make a Blender importer and will add the format to the wiki
## Post #52
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-15T14:15:59+00:00
- Post Title: Re: Tekken Hybrid

Actually the normals are pretty good. I use them to flip the reversed faces and it worked out great. In LightWave, the models I load look pretty good; but when loaded into Maya the lighting is somewhat off, somewhat strange. I displayed the vertex normals in Maya and they look good... but for some reason, I don't know what Maya's doing or if it's my graphics card, but I might try a version with normals removed to see if they look better in Maya.
## Post #53
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T17:33:29+00:00
- Post Title: Re: Tekken Hybrid

Ugh half-floats everywhere, complicated faces all over the place.
Is it as (or more efficient) computation-wise than just using triangle lists and single-precision floats?

Let's see how to write a noesis plugin for this...

I wonder if there's something in noesis that will make this face thing easier to do cause my parse_faces function is like 5x larger than any other function to do that "is face flipped" computation and all lol

EDIT: decided to try something short and simple

```
	stripLength = faceArray[i][2]
	idxBuff = self.inFile.readBytes(stripLength * 2)
	
	rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, stripLength, noesis.RPGEO_TRIANGLE_STRIP, 1) 

```


But it didn't work lol.
Maybe it's not just stripLength * 2?
[tekken.JPG](https://xentaxbackup.github.io/file/4989_tekken.JPG)
## Post #54
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-15T22:51:01+00:00
- Post Title: Re: Tekken Hybrid

You can't avoid it you will have to flip the faces. Flip the faces and then convert to triangle list and then send it to noesis.
## Post #55
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-16T00:06:02+00:00
- Post Title: Re: Tekken Hybrid

That's interesting. It's a PS3 game, right? My first guess is that you may be missing a flag regarding the initial winding order of the strip. It's also possible that said flag could affect only the winding order of subsequent triangles in the strip. (so the first 3 indices form a front-facing triangle, but then the winding doesn't flip as per usual and/or the flipping is dictated by a flag which is likely present in the strip/mesh header)

It's also possible that they simply don't use face culling in the game, but that seems unlikely (especially on PS3) due to the fill waste.
## Post #56
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-16T05:49:49+00:00
- Post Title: Re: Tekken Hybrid

PS3, but the models are the same from the PS2 version of the game. There is a trick to it, but I just don't have the time to figure out what that trick is. It only took 20 minutes to cook up the flipping scheme based on the vertex normals and it was done ha ha ha. For the people who just want their model rips I don't think it makes any difference .
## Post #57
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-16T06:33:28+00:00
- Post Title: Re: Tekken Hybrid

If the model data is really identical between the PS2 and PS3 games, then I suppose that explains it. Lots of PS2 games would store flags to affect the strip winding in the actual index or vertex data, or in the strip headers that would typically be checked when churning through the data in VU code. I've run into that in quite a few PS2 games and I think I recall revelation saying he ran into it in MGS2 (or maybe it was 3) as well. Not culling faces was also a lot more common in the PS2 days, though.

Most of those PS2 games seem store flags in the W component of the vertex position, and if a certain bit is set (usually it's 0x8000) then you need to reset the strip when you come upon that vertex.
## Post #58
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-16T06:39:32+00:00
- Post Title: Re: Tekken Hybrid

Hmmm... ok let me check the data really quick... see what I can find in the w part of the vertex position. The first few I saw were always 0, but I didn't look at all of them.
## Post #59
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-01-18T15:56:29+00:00
- Post Title: Re: Tekken Hybrid

Ok, I'm well aware of just how noobish this must sound but I can't seem to find a way to make this file work.

When I try to open tekken.py a command window opens for a second, but it immediately disappears.
Opening tekken.py via cmd I get: "[Errno 2] No such file or directory: 'law1u.chr' "
Running the file in IDLE got me the same error.

What am I doing wrong?

(stating the obvious: I'm totally new to python)
## Post #60
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-18T18:30:03+00:00
- Post Title: Re: Tekken Hybrid

Don't feel bad, I hate python with a passion too lol. Edit tekken.py in notepad. Then, place tekken.py and xentax.py and model file in python directory. Then go to command prompt. Cd to python directory. Type in python tekken.py at prompt and it should go. On Friday when I come back home I'll translate the code to c+ + and make an exe that parses everything in just one click. I still have to work on the bones too.
## Post #61
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-01-18T20:21:37+00:00
- Post Title: Re: Tekken Hybrid

Thanks Mr howfie.
tekken.py and xentax.py, OK! But which model file are you talking about?  ...sorry for spamming your thread  lol
## Post #62
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-18T21:36:16+00:00
- Post Title: Re: Tekken Hybrid

The chr files from the tekken disc. We cannot post all the files here. I believe the nina1u.chr sample was posted somewhere on page two. This is jjust a tools web site so I only post the tools to extract, not the actual models. To get models you can do one of two things. 
#1 the legal but against EULA way - jailbreak your ps3
#2 the illegal but bad way - download game

I won't tell you how to do either. You have to make the choice. #1 or #2.
## Post #63
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-01-19T09:29:24+00:00
- Post Title: Re: Tekken Hybrid

Oh well, now it does all make sense.     Thanks again Mr.!
Works like a charm. You really did an amazing job writing that script!     Thank you so much for enabling access to the models!!

Rather than doing #1 or #2 I'd prefer getting the files straight from the disk. I'll try that later.

Looking forward to Friday.
## Post #64
- Username: psycommando
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 26, 2012 11:21 am
- Post datetime: 2012-01-26T03:57:42+00:00
- Post Title: Re: Tekken Hybrid

Hi, I've tried your script but it crashes python(2.7) gives me the following output :

> Traceback (most recent call last):
>
>   File "C:\Users\Guill\Downloads\Tekken.Hybrid.PS3-DUPLEX\Extracted\INSTALL\USRDIR\data\asset\dai3\mdl\tekken.py", line 432, in <module>
>
>     xentax.WriteUncompressedDDSHeader(tfile, texture_info.p1, texture_info.p2, False, 0x00FF0000, 0x0000FF00, 0x000000FF, 0xFF000000);
>
>   File "C:\Users\Guill\Downloads\Tekken.Hybrid.PS3-DUPLEX\Extracted\INSTALL\USRDIR\data\asset\dai3\mdl\xentax.py", line 175, in WriteUncompressedDDSHeader
>
>     ofile.write(bytes('DDS ', 'ascii')); # DDS
>
> TypeError: str() takes at most 1 argument (2 given)

By the way, nice work  I wonder how you do to figure this all out !
## Post #65
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-26T04:42:58+00:00
- Post Title: Re: Tekken Hybrid

Try with 3.x
## Post #66
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-26T06:13:07+00:00
- Post Title: Re: Tekken Hybrid

Removing the second argument might work. I used 3.x. Sorry i had to temporarily give up on this one. The bone format was just strange. I may come back to it though after i finish up the easier ones.
## Post #67
- Username: psycommando
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 26, 2012 11:21 am
- Post datetime: 2012-01-26T22:49:04+00:00
- Post Title: Re: Tekken Hybrid

> Reply from howfie
>
> Removing the second argument might work.
Thanks, that fixed it
## Post #68
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-04-06T16:40:51+00:00
- Post Title: Re: Tekken Hybrid

hey howfie, look: [http://www.tombraiderforums.com/showpos ... ount=19913](http://www.tombraiderforums.com/showpost.php?p=6085895&postcount=19913)
people using your script to full effect. Looks like there are many more TTT models soon to be ported
## Post #69
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-06T22:23:44+00:00
- Post Title: Re: Tekken Hybrid

Lol yeah I keep dibs on the request thread from time to time to see what games have or have not been done. They don't have to credit me, you know, just have fun, learn how to model and rig, and if any lawyers comes asking, I didn't write the script .
## Post #70
- Username: Uninstall84
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 08, 2012 1:18 pm
- Post datetime: 2012-04-08T05:30:16+00:00
- Post Title: Re: Tekken Hybrid

howfie
Как извлечь текстуры?
How to extract textures?
## Post #71
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-04-29T13:19:06+00:00
- Post Title: Re: Tekken Hybrid

does the triangle count fall between 3000-6000? just something I was wondering about namco ps2 games
## Post #72
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2012-05-08T19:21:38+00:00
- Post Title: Re: Tekken Hybrid

> Reply from Uninstall84
>
> howfie
Как извлечь текстуры?
How to extract textures?
Скрипт сам извлекает и модели и текстуры - достаточно поместить файл персонажа в корневой каталог Noesis и прописать его имя в скрипте - и вуаля! автоматически генерируется модель в формате OBJ и текстуры в формате DDS
## Post #73
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2012-05-08T19:27:03+00:00
- Post Title: Re: Tekken Hybrid

One question: what about non characters models (firstly I'm interested in Dr. Boskonovitch model from Tekken Bowl stage) - any ideas where can I find it and how to extract it?!
P.S: No, I have a two questions, the second is - why all textures are being flipped?
## Post #74
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-08T19:42:53+00:00
- Post Title: Re: Tekken Hybrid

#1: I'll see what I can do. I didn't look at the stages. 
#2: horizontally or vertically? If vertically that's the way the textures are stored. If horizontally and model looks mirrored, that's a coordinate system problem caused by noesis using a rhcs and game using lhs.
## Post #75
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2012-05-09T10:54:21+00:00
- Post Title: Re: Tekken Hybrid

Oh, I'm beg your pardon - textures is OK (they are flipped only in Noesis, in 3DS MAX they are OK).

One more idea: is it possible to use the same trick with Tekken 5 (unpack PS3 version of this game (Tekken 5: Dark Resurrection), extract and convert 3D models)?
## Post #76
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-06-15T14:06:35+00:00
- Post Title: Re: Tekken Hybrid

Hey,
Someone tell me please, can this script work with models from Tekken Tag 2 Prologue which also included at Tekken Hybrid game disc? Or it's only for Tekken Tag 1 HD? Thanks!
## Post #77
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-15T14:43:59+00:00
- Post Title: Re: Tekken Hybrid

no it doesn't. two different games.
## Post #78
- Username: Higus
- Rank: advanced
- Number of posts: 78
- Joined date: Sat Jun 30, 2012 12:35 pm
- Post datetime: 2012-07-02T09:22:24+00:00
- Post Title: Re: Tekken Hybrid

Sorry for bumping but Can we get to the Tekken Tag Tournament 2 part of hybrid cracking? :3
## Post #79
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-02T10:33:18+00:00
- Post Title: Re: Tekken Hybrid

just wait for the 360 version to come out there is a 99% chance it will already work.
## Post #80
- Username: Higus
- Rank: advanced
- Number of posts: 78
- Joined date: Sat Jun 30, 2012 12:35 pm
- Post datetime: 2012-07-03T11:37:33+00:00
- Post Title: Re: Tekken Hybrid

I don't see it like that, You see I'm able to use the same methods to Xbox360 T6/SC5 extracting, with my PS3 discs of both games, therefore there is no difference to whether or not its PS3 or X360, so long as you get the Data BIN files, you're all good.
## Post #81
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-02T15:30:44+00:00
- Post Title: Re: Tekken Hybrid

any word on the model bones
