## Post #1
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-07-26T02:45:25+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

I've got a script written for Python 2.6 that supposedly converts Pepakura (.PBO) models to Metasequoia (.MQO) models. The problem is I can't get the script to run without getting a bunch of syntax errors! I did not write this script and I have no python programing knowledge.
I hope someone who knows Python scripting can fix the errors.
I'd love to see how well this script works. Any and all help would be much appreciated!

```
# by MrPotatoHead using python 2.6

# You must specify the imput file with the full directory
# You must also specify the output directory AND filename (no extension)
# Also remember to change the scale

# I couldn't be bothered to invert the face orientation
# Just select all the faces in your cad program and invert them

import struct
import zlib
import codecs
from array import array
import sys
#saveout = sys.stdout
#outfile = open('C:/output.txt', 'w')
#sys.stdout = outfile

h1=codecs.decode('424d','hex')
h2=codecs.decode('000000003600000028000000','hex')
h3=codecs.decode('010018000000000000000000120B0000120B00000000000000000000','hex')
h4=codecs.decode('0000','hex')

#***** Change the Scale here *****
scale = 1
#*********************************


f = open("C:/testfile.pdo", "rb")
outputname = "testfile"
outputdirectory = "C:/temp/"


metafile = outputdirectory+outputname
of = open(metafile+".mqo", 'w')

of.write("Metasequoia Document\n")
of.write("Format Text Ver 1.0\n")
of.write("\n")
of.write("Scene {\n")
of.write("pos -30.5374 -301.0406 878.7299\n")
of.write("lookat 0.0000 0.0000 0.0000\n")
of.write("head -6.8400\n")
of.write("pich 0.1908\n")
of.write("ortho 0\n")
of.write("zoom2 10.0094\n")
of.write("amb 0.490 0.490 0.490\n")
of.write("}\n")



try:
   dump = f.read(148)
   print ("dump")
   nobj = f.read(4)
   numobj = struct.unpack("i", nobj)
   kk1 = numobj[0]
   print ("number of objects =" ,kk1)
   if kk1 > 10000: kk1=1
   #loop number of objects
   for i in range(0,kk1):
      dump = f.read(4)
      namelen = struct.unpack("i", dump)
      dump = f.read(namelen[0])
      dump = f.read(1)
      dump = f.read(4)
      numvert = struct.unpack("i", dump)
      kk2 = numvert[0]
      if kk2 > 10000: kk2 = 0
      #loop number of vertices
      for j in range(0, kk2):
         x = f.read(8)
         y = f.read(8)

         z = f.read(8)
      dump = f.read(4)
      numfaces = struct.unpack("i", dump)
      kk3 = numfaces[0]
      if kk3 > 10000: kk3 = 0
      #loop number of faces
      for j in range(0, kk3):
         dump = f.read(40)
         nvif = f.read(4)
         numvif = struct.unpack("i", nvif)
         kk4 = numvif[0]
         if kk4 > 10: kk4 = 0
         #loop number of verticies in face
         for k in range(0, kk4):
            vnum = f.read(4)
            vnumber = struct.unpack("i", vnum)
            dump = f.read(8)
            dump = f.read(8)
            u1 = f.read(8)
            uu = struct.unpack("d", u1)
            v1 = f.read(8)
            vv = struct.unpack("d", v1)
            dump = f.read(49)
      dump = f.read(4)
      numlines = struct.unpack("i", dump)
      kk5 = numlines[0]
      print ("number of lines", kk5)
      if kk5 > 20000: kk5 = 0
      for l in range(0, kk5):
         dump = f.read(22)
      position = f.tell();

   #now get materials
   print ("position")
   dump = f.read(4)
   numtx = struct.unpack("i", dump)

   numtex = numtx[0]
   tstr1 = ("Material"+str(numtex)+" {\n")
   of.write(tstr1)
   for m in range(0, numtex):
      print ("processing material", m+1, "of", numtex)
      tstr1 = "\"mat"+str(m+1)+"\" shader(3) col("
      of.write(tstr1)
      dump = f.read(4)
      nameln = struct.unpack("i", dump)
      namelen = nameln[0]
      dump = f.read(namelen)
      dump = f.read(4)
      rrrr = struct.unpack("f", dump)
      dump = f.read(4)
      gggg = struct.unpack("f", dump)
      dump = f.read(4)
      bbbb = struct.unpack("f", dump)
      dump = f.read(4)
      aaaa = struct.unpack("f", dump)
      tstr1 = ("%.3f" % rrrr)+" "+("%.3f" % gggg)+" "+("%.3f" % bbbb)+" "+("%.3f" % aaaa)
      tstr1 += ") dif(0.800) amb(0.600) emi(0.160) spc(0.000) power(5.00)"
      of.write(tstr1)
      dump = f.read(64)
      dump = f.read(1)
      d2 = struct.unpack("B", dump[0])
      print ("d2[0]")
      if d2[0] == 1:
         tstr1 = "text(\""+outputname+str(m)+"tex.bmp\")"
         of.write(tstr1)
         print ("texture found")
         dump = f.read(4)
         bmpw = struct.unpack("i", dump)
         bmpwidth = bmpw[0]
         dump = f.read(4)
         bmph = struct.unpack("i", dump)


         bmpheight = bmph[0]
         dump = f.read(4)
         zlibl = struct.unpack("i", dump)
         zliblen = zlib[0]
         numpixels = bmpwidth*bmpheight
         print ("numpixels")
         #decompress zlib data
         dump = f.read(zliblen)
      of.write("\n")



except EOFError:
   print ("oops")

finally:
   f.seek(0,0);


#just to make sure
f.seek(0,0);
of.write("}\n")
out_str = ""
try:
   dump = f.read(148)
   nobj - f.read(4)
   numobj = struct.unpack("i", nobj)
   #print numobj[0]
   kk1 = numobj[0]
   if kk1 > 10000: kk1 = 1
   for i in range(0, kk1):
      dump = f.read(4)
      namelen = struct.unpack("i", dump)
      dump = f.read(namelen[0])
      dump = f.read(1)
      print ("processing object", i+1)
      name = "obj"+str(i+1)
      of.write("Object \""+name+"\" {\n")

      of.write(" depth 0\n")
      of.write(" folding 0\n")
      of.write(" scale 1.000000 1.000000 1.000000\n")
      of.write(" rotation 0.000000 0.000000 0.000000\n")
      of.write(" translation 0.000000 0.000000 0.000000\n")
      of.write(" visible 15\n")
      of.write(" locking 0\n")
      of.write(" shading 1\n")
      of.write(" facet 59.5\n")
      of.write(" color 0.000 0.000 0.000\n")
      of.write(" color_type 0\n")
      of.write(" verex ")
      dump = f.read(4)
      numvert = struct.unpack("i", dump)
      of.write(str(numvert[0])),
      of.write("{\n")
      kk2 = numvert[0]
      if kk2 > 10000: kk2 = 0
      for j in range(0, kk2):
         x = f.read(8)
         y = f.read(8)
         z = f.read(8)
         outx = struct.unpack("d",x)
         outy = struct.unpack("d",y)
         outz = struct.unpack("d",z)
         ox = outx[0] * scale
         oy = outy[0] * scale
         oz = outz[0] * scale
         tmpstr = "\t"+("%.4f" % ox)+" "+("%.4f" % oy)+" "+("%.4f" % oz)
         of.write(tmpstr+"\n")
      of.write(" }\n")
      dump = f.read(4)
      numfaces = struct.unpack("i", dump)
      tmpstr = "\t face"+" "+str(numfaces[0])+" {\n"
      of.write(tmpstr)
      kk3 = numfaces[0]

      if kk3 > 10000: kk3 = 0
      for j in range(0, kk3):
         mtid = f.read(4)
         matid = struct.unpack("i", mtid)
         matid2 = matid[0]
         matstr = ""
         if matid2 != -1:
            matstr = "M("+str(matid2)+")"
         dump = f.read(36)
         nvif = f.read(4)
         numvif = struct.unpack("i", nvif)
         tmpstr = str(numvif[0])+" V("
         of.write(tmpstr)
         kk4 = numvif[0]
         if kk4 > 10: kk4 = 0
         #redo this to reverse the faces: either 3 or 4
         for k in range(0, kk4):
            vnum = f.read(4)
            vnumber = struct.unpack("i", vnum)
            of.write(str(vnumber[0])+" "),
            dump = f.read(8)
            dump = f.read(8)
            u1 = f.read(8)
            uu = struct.unpack("d", u1)
            out_str += ("%.5f" % uu[0])
            out_str += " "
            v1 = f.read(8)
            vv = struct.unpack("d", v1)
            out_str += ("%.5f" % vv[0])
            out_str += " "
            dump = f.read(49)
         of.write(")"+matstr+" UV( "+out_str+" )\n")
         out_str = ""
      of.write("}\n")
      of.write("}\n")
      dump = f.read(4)

      numlines = struct.unpack("i", dump)
      kk5 = numlines[0]
      if kk5 > 20000: kk5 = 0
      for l in range(0, kk5):
         dump = f.read(22)
      position = f.tell();
   of.write("Eof\n")
   of.close()
   #read number of materials
   dump = f.read(4)
   numtx = struct.unpack("i", dump)
   numtex = numtx[0]
   #for k = 1 to numtex do
   for m in range(0, numtex):
      print ("processing materials",m)
      dump = f.read(4)
      nameln = struct.unpack("i", dump)
      namelen = nameln[0]
      dump = f.read(nameln)
      dump = f.read(80)
      dump = f.read(1)
      d2 = struct.unpack("B", dump[0])
      print ("d2[0]")
      if d2[0] == 1:
         print ("doing bitmap")
         dump = f.read(4)
         bmpw = struct.unpack("i", dump)
         bmpwidth = bmpw[0]
         dump = f.read(4)
         bmph = struct.unpack("i", dump)
         bmpheight = bmph[0]
         dump = f.read(4)
         zlibl = struct.unpack("i", dump)
         zliblen = zlib[0]
         numpixels = bmpwidth*bmpheight
         print ("numpixels")

         #decompress zlib data
         dump = f.read(zliblen)
         out = zlib.decompress(dump)
         out = out[::-1]
         out2 = ""
         for n in range(0, bmpheight):
            pstart = int(n*bmpwidth*3)
            pend = int((pstart)+(bmpwidth*3))
            tout = out[pstart:pend]
            outk = ""
            for knn in range(0, bmpwidth):
               myoutk = ""
               kstart = (knn*3)
               kend = (knn*3)+3
               myoutk = tout[kstart:kend]
               outk += myoutk[::-1]
            out2 += outk[::-1]
         print ("n")
         #write bitmap image to file
         of2name = metafile+str(m)+"tex.bmp"
         of2 = open(of2name, 'wb')
         of2.write(h1)
         bmpfilesize = "%08x" % ((bmpwidth*bmpheight*3)+56)
         print ("bmpfilesize, bmpwidth, bmpheight")
         bmpfs = codecs.decode(bmpfilesize,'hex')
         bmpfs = bmpfs[::-1]
         of2.write(bmpfs)
         of2.write(h2)
         bmpws = "%08x" % (bmpwidth)
         bmpws2 = codecs.decode(bmpws,'hex')
         bmpws2 = bmpws2[::-1]
         of2.write(str(bmpws2))
         bmphs = "%08x" % (bmpheight)
         bmphs2 = codecs.decode(bmphs,'hex')
         bmphs2 = bmphs2[::-1]
         of2.write(str(bmphs2))

         of2.write(h3)
         of2.write(out2)
         of2.write(h4)
         of2.close()

except EOFError:
   print ("oops")

finally:
   f.close()

print ("finished")

```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T03:00:05+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Upload some samples to test against.

EDIT: I found this [http://www.tamasoft.co.jp/pepakura-en/d ... index.html](http://www.tamasoft.co.jp/pepakura-en/download/polygons/index.html)
Guess these are samples.

Though, I can't follow his code lol
## Post #3
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-07-26T07:40:12+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Here is a place to download some free models:
[http://www.swpm.tym.sk/index.files/alliance.htm](http://www.swpm.tym.sk/index.files/alliance.htm)
The web is full of free Pepakura models so finding some to test with shouldn't be too hard.
## Post #4
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-26T11:55:02+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

I tried running script.
error messaged "Invalid syntax @ line 158".
but i have no idea sorry 
[metaseq_script_test.jpg](https://xentaxbackup.github.io/file/4539_metaseq_script_test.jpg)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T12:51:04+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

I don't think you're supposed to run it through metaseq script editor.
Just run it through command-line, seeing how it's writing out mqo files.

Anyways I ran it through command-line and it was running into a bunch of odd errors that shouldn't occur in tested code

1: strings not ended properly (missing quotes, extra quotes)

```
         x = f.read(8)
         y = f.read(8)
         z = f.read(8)
         outx = struct.unpack("d", x")
         outy = struct.unpack("d", y")
         outz = struct.unpack("d", z")
         ox = outx[0] * scale
         oy = outy[0] * scale
         oz = outz[0] * scale

```


2: hardcoded input file (some people would probably have no idea what's wrong)

After making some attempt to fix it, it still doesn't work for the models I downloaded from the official site.
It tells me 0 objects were in the file and so everything fails.

Here's what I've made out of the version 3 binary format:

```

Char_10 idstring (Version 3\n)
dword unk1
dword null
dword unk2

dword charLen
charLen keyboard
dword charLen
charLen encoding

dword null
dword charLen
charLen hash

dword_8 ???
dword numMesh

numMesh mesh {
   dword charLen
   charLen meshName
   
   byte unkByte
   dword unkCount
   #skip unkCount * 24 bytes
   dword numVerts
   
   numVerts vertex {
       299 bytes or 384 bytes
   }
   dword numFaces
}

```


From what I've written here, the code doesn't even look like it's going to get the right values.
## Post #6
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-07-26T15:03:01+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Me too.
"Invalid syntax."
## Post #7
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-07-26T16:05:42+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Well after some further research I found this:
[http://uppit.com/psx3tn8va1b8/Pdo2mqo.zip](http://uppit.com/psx3tn8va1b8/Pdo2mqo.zip)
This is the original Python code. How it works is you must open the pdo2mqo.pdo file in Pepakura Viewer (NOT Pepakura Designer), and view the model's texture to read the code. You then have to manually type out the lines of code text yourself into Python and save the script. What a headache! From what I've seen of the original code it looks to be meant to work with 3D Studio Max 7. Thanks for all the continued help here guys!
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T16:30:08+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

We might as well just figure out the format, post it up, and then let people write the respective importers 
I looked around and it seemed some other members on other forums had some interest in the format for version 3, but couldn't figure it out.

I'm also have trouble just getting the faces section right (I can't find a solid pattern) and have no idea how the vertex is stored besides having 299 or 384 bytes depending on some unknown reason.

I believe the designer (or maybe the viewer) has an option to export to OBJ though.
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-07-26T18:01:54+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T18:39:10+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

It looks like the ones from the official site are different; they didn't have the "pepakura designer 3" in their header. That makes sense then.
## Post #11
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-07-26T21:09:21+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T21:42:37+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Post up the ones you are having trouble with.
## Post #13
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-07-27T08:53:57+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-07-27T18:18:48+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Szkaradek123 , you are great!!!
## Post #15
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-03-21T03:49:42+00:00
- Post Title: Pepakura .PBO to Metasequoia .MQO Conversion Script

Please help me.
This pdo file could not be converted
[http://www.mediafire.com/?dkdas8shmhckk26](http://www.mediafire.com/?dkdas8shmhckk26)
need someone to fix error on python script.
## Post #16
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-21T18:36:49+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

LOL - it's my old script.....

Anyway, the dump = f.read(148) line near the top isn't always correct.
For most western locales it's 148 bytes, guessing the file uses a different locale and/or font.
For the files you posted it needs f.read(149) to work.

Should really get around to fixing it at some point, can't find my format specs atm, from memory the locale and font name length is given, the names are plain ascii + value.
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-21T20:42:01+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

lol I was wondering why your BRS script looked familiar.

I don't have any pepakura models for that particular format (they have different versions), but the version I have gives string lengths.

Now that I look at it...it's a very simple format. I think last year I thought it was really complicated. Now it's just...cool, header + vertices + indices
Well, version 3 anyways. They probably have an option for compression though, based on what you had.

I'm sure when they moved from whatever version to version 3, they decided compression was silly...
## Post #18
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2012-03-22T00:57:58+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

Ahem, I've been doing pepakura, longer than just about anyone else on the web. Here's the thing, if you have the unlocked version of Pepakura Designer 3 you can export the pepakura model to a OBJ format which Metasequoia will open and you can either work with it in Metasequoia or you can export it from there in the MQO format. No coding needed. And I get a unlimited supply of codes from Tamasoft to give away at panels that I teach pepakura on.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-22T01:04:48+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

I guess whoever wants free licenses they know where to go lol.

I'm guessing pepakura allows obj importing (and maybe other formats)?
## Post #20
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-22T01:07:28+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

Yeah, did the script for the old version as well.
It is a simple format for the 3D model anyway, the locale strings in the header are simply masked, there isn't any compression except for the texures, which is where it gets silly, there's no checking for repeated textures - makes compressing them redundant......
Got a 32 byte MD5 key in the header, for security  - lol

I'll find my older versions and upload them.

@Nintendude, not if the file is locked, you'd need a cracked version of pepakura for that.
I don't see any problem ripping files from software that encourages the (mostly illegal) distribution of game content. 
You got any old tenkai versions? Think I got 1.5 somewhere.
## Post #21
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2012-03-22T02:39:19+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

I just use Pepakura Designer 3, Pepakura Designer allows for .3ds, .obj, .mqo, and a few others. It's not able to open everything out there and high-poly models in pepakura designer are not advisable. Pepakura Designer is pretty much a over glorified UV coordinate program it converts 3D to 2D so the 2D pattern can be created out of paper in 3D. 
Actually if a pepakura file is locked there's not really any possible way I know of to crack the file except for getting the password from the original artist. I've tried, although I have'nt tried everything.
Whenever I make a pepakura file I usually get it from someplace like here, Facepunch, Jedi Knight 3 Mods, before I'll try to get it from the game myself if I can't get it from the game there's usually someone like a person on here who can help with that, all my pepakura models come from sites like this and the ones I mentioned above, I've ripped a few models but about 75% comes from sources.
## Post #22
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-03-22T04:29:40+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

> Reply from finale00
>
> I guess whoever wants free licenses they know where to go lol.
That's not what I want.
This is just difference version of Pepakura, by the way.
## Post #23
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-23T01:10:40+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

Found lots of older version files, but better than that I found the older software zips and installers.
Got tenkai (old name) versions 123a and 140a, and pepakura designer versions 1.01, 2.01 and 2.17.
Zipped them up together if anyone wants them as a curiosity, pm me.
## Post #24
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-25T12:39:36+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

Available to convert PDO file ->PDO 00_.pdo, PDO 01_.pdo, PDO 02_.pdo, PDO 03_.pdo
Unable to convert PDO file ->PDO 00.pdo, PDO 01.pdo, PDO 02.pdo, PDO 03.pdo
[http://www.mediafire.com/?4my9bt4hg2uw8y6](http://www.mediafire.com/?4my9bt4hg2uw8y6)
There is a distinct difference between the two.	
But, i don't know exactly that.
## Post #25
- Username: Seventyseven
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 13, 2007 5:28 pm
- Post datetime: 2015-07-02T10:46:01+00:00
- Post Title: Re: Pepakura .PBO to Metasequoia .MQO Conversion Script

A bit late but had to fix the errors.

```
# by MrPotatoHead using python 2.6

# You must specify the imput file with the full directory
# You must also specify the output directory AND filename (no extension)
# Also remember to change the scale

# I couldn't be bothered to invert the face orientation
# Just select all the faces in your cad program and invert them

import struct
import zlib
import codecs
from array import array
import sys
#saveout = sys.stdout
#outfile = open('C:/output.txt', 'w')
#sys.stdout = outfile

h1=codecs.decode('424d','hex')
h2=codecs.decode('000000003600000028000000','hex')
h3=codecs.decode('010018000000000000000000120B0000120B00000000000000000000','hex')
h4=codecs.decode('0000','hex')

#***** Change the Scale here *****
scale = 1
#*********************************


f = open("C:/testfile.pdo", "rb")
outputname = "testfile"
outputdirectory = "C:/temp/"


metafile = outputdirectory+outputname
of = open(metafile+".mqo", 'w')

of.write("Metasequoia Document\n")
of.write("Format Text Ver 1.0\n")
of.write("\n")
of.write("Scene {\n")
of.write("pos -30.5374 -301.0406 878.7299\n")
of.write("lookat 0.0000 0.0000 0.0000\n")
of.write("head -6.8400\n")
of.write("pich 0.1908\n")
of.write("ortho 0\n")
of.write("zoom2 10.0094\n")
of.write("amb 0.490 0.490 0.490\n")
of.write("}\n")



try:
   dump = f.read(148)
   print ("dump")
   nobj = f.read(4)
   numobj = struct.unpack("i", nobj)
   kk1 = numobj[0]
   print ("number of objects =" ,kk1)
   if kk1 > 10000: kk1=1
   #loop number of objects
   for i in range(0,kk1):
      dump = f.read(4)
      namelen = struct.unpack("i", dump)
      dump = f.read(namelen[0])
      dump = f.read(1)
      dump = f.read(4)
      numvert = struct.unpack("i", dump)
      kk2 = numvert[0]
      if kk2 > 10000: kk2 = 0
      #loop number of vertices
      for j in range(0, kk2):
         x = f.read(8)
         y = f.read(8)

         z = f.read(8)
      dump = f.read(4)
      numfaces = struct.unpack("i", dump)
      kk3 = numfaces[0]
      if kk3 > 10000: kk3 = 0
      #loop number of faces
      for j in range(0, kk3):
         dump = f.read(40)
         nvif = f.read(4)
         numvif = struct.unpack("i", nvif)
         kk4 = numvif[0]
         if kk4 > 10: kk4 = 0
         #loop number of verticies in face
         for k in range(0, kk4):
            vnum = f.read(4)
            vnumber = struct.unpack("i", vnum)
            dump = f.read(8)
            dump = f.read(8)
            u1 = f.read(8)
            uu = struct.unpack("d", u1)
            v1 = f.read(8)
            vv = struct.unpack("d", v1)
            dump = f.read(49)
      dump = f.read(4)
      numlines = struct.unpack("i", dump)
      kk5 = numlines[0]
      print ("number of lines", kk5)
      if kk5 > 20000: kk5 = 0
      for l in range(0, kk5):
         dump = f.read(22)
      position = f.tell();

   #now get materials
   print ("position")
   dump = f.read(4)
   numtx = struct.unpack("i", dump)

   numtex = numtx[0]
   tstr1 = ("Material "+str(numtex)+" {\n") #error fixed - added space after Material
   of.write(tstr1)
   for m in range(0, numtex):
      print ("processing material", m+1, "of", numtex)
      tstr1 = "\"mat"+str(m+1)+"\" shader(3) col("
      of.write(tstr1)
      dump = f.read(4)
      nameln = struct.unpack("i", dump)
      namelen = nameln[0]
      dump = f.read(namelen)
      dump = f.read(4)
      rrrr = struct.unpack("f", dump)
      dump = f.read(4)
      gggg = struct.unpack("f", dump)
      dump = f.read(4)
      bbbb = struct.unpack("f", dump)
      dump = f.read(4)
      aaaa = struct.unpack("f", dump)
      tstr1 = ("%.3f" % rrrr)+" "+("%.3f" % gggg)+" "+("%.3f" % bbbb)+" "+("%.3f" % aaaa)
      tstr1 += ") dif(0.800) amb(0.600) emi(0.160) spc(0.000) power(5.00)"
      of.write(tstr1)
      dump = f.read(64)
      dump = f.read(1)
      d2 = struct.unpack("B", dump[0])
      print ("d2[0]")
      if d2[0] == 1:
         tstr1 = " tex(\""+outputname+str(m)+"tex.bmp\")" #error fixed - was text instead of tex and added space
         of.write(tstr1)
         print ("texture found")
         dump = f.read(4)
         bmpw = struct.unpack("i", dump)
         bmpwidth = bmpw[0]
         dump = f.read(4)
         bmph = struct.unpack("i", dump)


         bmpheight = bmph[0]
         dump = f.read(4)
         zlibl = struct.unpack("i", dump)
         zliblen = zlibl[0] # error fixed - was zlib
         numpixels = bmpwidth*bmpheight
         print ("numpixels")
         #decompress zlib data
         dump = f.read(zliblen)
      of.write("\n")



except EOFError:
   print ("oops")

finally:
   f.seek(0,0);


#just to make sure
f.seek(0,0);
of.write("}\n")
out_str = ""
try:
   dump = f.read(148)
   nobj = f.read(4) #error fixed - minus sign should be equals sign
   numobj = struct.unpack("i", nobj)
   #print numobj[0]
   kk1 = numobj[0]
   if kk1 > 10000: kk1 = 1
   for i in range(0, kk1):
      dump = f.read(4)
      namelen = struct.unpack("i", dump)
      dump = f.read(namelen[0])
      dump = f.read(1)
      print ("processing object", i+1)
      name = "obj"+str(i+1)
      of.write("Object \""+name+"\" {\n")

      of.write(" depth 0\n")
      of.write(" folding 0\n")
      of.write(" scale 1.000000 1.000000 1.000000\n")
      of.write(" rotation 0.000000 0.000000 0.000000\n")
      of.write(" translation 0.000000 0.000000 0.000000\n")
      of.write(" visible 15\n")
      of.write(" locking 0\n")
      of.write(" shading 1\n")
      of.write(" facet 59.5\n")
      of.write(" color 0.000 0.000 0.000\n")
      of.write(" color_type 0\n")
      of.write(" vertex ") #error fixed should be vertex
      dump = f.read(4)
      numvert = struct.unpack("i", dump)
      of.write(str(numvert[0])),
      of.write("{\n")
      kk2 = numvert[0]
      if kk2 > 10000: kk2 = 0
      for j in range(0, kk2):
         x = f.read(8)
         y = f.read(8)
         z = f.read(8)
         outx = struct.unpack("d",x)
         outy = struct.unpack("d",y)
         outz = struct.unpack("d",z)
         ox = outx[0] * scale
         oy = outy[0] * scale
         oz = outz[0] * scale
         tmpstr = "\t"+("%.4f" % ox)+" "+("%.4f" % oy)+" "+("%.4f" % oz)
         of.write(tmpstr+"\n")
      of.write(" }\n")
      dump = f.read(4)
      numfaces = struct.unpack("i", dump)
      tmpstr = "\t face"+" "+str(numfaces[0])+" {\n"
      of.write(tmpstr)
      kk3 = numfaces[0]

      if kk3 > 10000: kk3 = 0
      for j in range(0, kk3):
         mtid = f.read(4)
         matid = struct.unpack("i", mtid)
         matid2 = matid[0]
         matstr = ""
         if matid2 != -1:
            matstr = "M("+str(matid2)+")"
         dump = f.read(36)
         nvif = f.read(4)
         numvif = struct.unpack("i", nvif)
         tmpstr = str(numvif[0])+" V("
         of.write(tmpstr)
         kk4 = numvif[0]
         if kk4 > 10: kk4 = 0
         #redo this to reverse the faces: either 3 or 4
         for k in range(0, kk4):
            vnum = f.read(4)
            vnumber = struct.unpack("i", vnum)
            of.write(str(vnumber[0])+" "),
            dump = f.read(8)
            dump = f.read(8)
            u1 = f.read(8)
            uu = struct.unpack("d", u1)
            out_str += ("%.5f" % uu[0])
            out_str += " "
            v1 = f.read(8)
            vv = struct.unpack("d", v1)
            out_str += ("%.5f" % vv[0])
            out_str += " "
            dump = f.read(49)
         of.write(")"+matstr+" UV( "+out_str+" )\n")
         out_str = ""
      of.write("}\n")
      of.write("}\n")
      dump = f.read(4)

      numlines = struct.unpack("i", dump)
      kk5 = numlines[0]
      if kk5 > 20000: kk5 = 0
      for l in range(0, kk5):
         dump = f.read(22)
      position = f.tell();
   of.write("Eof\n")
   of.close()
   #read number of materials
   dump = f.read(4)
   numtx = struct.unpack("i", dump)
   numtex = numtx[0]
   #for k = 1 to numtex do
   for m in range(0, numtex):
      print ("processing materials",m)
      dump = f.read(4)
      nameln = struct.unpack("i", dump)
      namelen = nameln[0]
      dump = f.read(namelen)#error fixed was nameln instead of namelen
      dump = f.read(80)
      dump = f.read(1)
      d2 = struct.unpack("B", dump[0])
      print ("d2[0]")
      if d2[0] == 1:
         print ("doing bitmap")
         dump = f.read(4)
         bmpw = struct.unpack("i", dump)
         bmpwidth = bmpw[0]
         dump = f.read(4)
         bmph = struct.unpack("i", dump)
         bmpheight = bmph[0]
         dump = f.read(4)
         zlibl = struct.unpack("i", dump)
         zliblen = zlibl[0] #error fixed - was zlib instead of zlibl
         numpixels = bmpwidth*bmpheight
         print ("numpixels")

         #decompress zlib data
         dump = f.read(zliblen)
         out = zlib.decompress(dump)
         out = out[::-1]
         out2 = ""
         for n in range(0, bmpheight):
            pstart = int(n*bmpwidth*3)
            pend = int((pstart)+(bmpwidth*3))
            tout = out[pstart:pend]
            outk = ""
            for knn in range(0, bmpwidth):
               myoutk = ""
               kstart = (knn*3)
               kend = (knn*3)+3
               myoutk = tout[kstart:kend]
               outk += myoutk[::-1]
            out2 += outk[::-1]
         print ("n")
         #write bitmap image to file
         of2name = metafile+str(m)+"tex.bmp"
         of2 = open(of2name, 'wb')
         of2.write(h1)
         bmpfilesize = "%08x" % ((bmpwidth*bmpheight*3)+56)
         print ("bmpfilesize, bmpwidth, bmpheight")
         bmpfs = codecs.decode(bmpfilesize,'hex')
         bmpfs = bmpfs[::-1]
         of2.write(bmpfs)
         of2.write(h2)
         bmpws = "%08x" % (bmpwidth)
         bmpws2 = codecs.decode(bmpws,'hex')
         bmpws2 = bmpws2[::-1]
         of2.write(str(bmpws2))
         bmphs = "%08x" % (bmpheight)
         bmphs2 = codecs.decode(bmphs,'hex')
         bmphs2 = bmphs2[::-1]
         of2.write(str(bmphs2))

         of2.write(h3)
         of2.write(out2)
         of2.write(h4)
         of2.close()

except EOFError:
   print ("oops")

finally:
   f.close()

print ("finished")

```


Here is Python 2.7 code that can be used (imported) to provide a file dialog to get filename.

```

from tkFileDialog import askopenfilename as tkFileGet
import tkMessageBox
import os.path, sys


def openFile(filetype,extension):
    fn = tkFileGet(title='Select a file',
                   #initialdir=os.path.split(sys.argv[0])[0],
                   filetypes=[(filetype,'*.'+extension),('All Files','*.*')])
    if fn:
        if fn[-4:].lower() in ['.'+extension]:
            return fn
        else:
            print ('Error.','Not a '+extension+' file.')
            tkMessageBox.showinfo('Error.','Not a '+extension+' file')
            return  
    else:
        print ('No file selected.')
        return  

if __name__ =='__main__':
    openFile('filetype','ext')
```
