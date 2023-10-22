## Post #1
- Username: Kar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 25, 2010 8:02 am
- Post datetime: 2010-06-25T21:58:08+00:00
- Post Title: Request: Eternal Sonata models

Would it be possible for anyone to extract the 3D models and textures of the characters from the game Eternal Sonata? Any version of the game would be fine. The models I am specifically looking for are Frederic, Fugue, Waltz and Polka along with their weapons. I appreciate your time reading this. Thank you.
## Post #2
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-25T22:14:59+00:00
- Post Title: Request: Eternal Sonata models

I made an eternal sonata extractor a while back, will look for it tonight.
[http://forums.x-cult.org/topic/2942-hac ... bell-demo/](http://forums.x-cult.org/topic/2942-hacking-eternal-sonata-trusty-bell-demo/)
## Post #3
- Username: Kar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 25, 2010 8:02 am
- Post datetime: 2010-06-26T00:05:45+00:00
- Post Title: Request: Eternal Sonata models

> Reply from surix
>
> I made an eternal sonata extractor a while back, will look for it tonight.
http://forums.x-cult.org/topic/2942-hac ... bell-demo/
Thank you very much. =) Would you mind if I ask how exactly did you manage to get these models?
## Post #4
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-26T01:18:27+00:00
- Post Title: Request: Eternal Sonata models

I got those models from the demo, I'm still trying to find the source code, I have a box of harddrives from old computers, hoping its not on my old laptop, doubt that thing boots anymore.  it must be on one of 3 drives from the 2007 era.


the format was pretty streight forward but looks like they changed the compression on the release of the game. demo had either no compression or else a friend of mine decompressed it being i dont remember doing any decompressing.
## Post #5
- Username: Kar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 25, 2010 8:02 am
- Post datetime: 2010-06-26T03:48:42+00:00
- Post Title: Request: Eternal Sonata models

> Reply from surix
>
> I got those models from the demo, I'm still trying to find the source code, I have a box of harddrives from old computers, hoping its not on my old laptop, doubt that thing boots anymore.  it must be on one of 3 drives from the 2007 era.


the format was pretty streight forward but looks like they changed the compression on the release of the game. demo had either no compression or else a friend of mine decompressed it being i dont remember doing any decompressing.
Ah, probably why I wasn't able to do get anything... then again I'm new to this thing and I most likely had no idea what I was doing, haha. I hope you have luck in finding it!
## Post #6
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-27T20:32:04+00:00
- Post Title: Request: Eternal Sonata models

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-27T20:43:58+00:00
- Post Title: Request: Eternal Sonata models

can you post the source to your converter ill add tex coords if i can figure them out.
## Post #8
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-27T21:12:38+00:00
- Post Title: Request: Eternal Sonata models

yeah, grabbing the vertex is kind of a mess right now, thing is there are tons of different vertex formats, header.flag2 has bits which represent different configurations of vertex data

on the demo, the character models are in the file AppKeep.bmd

```
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using xxx.Rendering.Imaging.DirectDrawSurfaces;
using xxx.Rendering.Imaging.Bitmaps;

namespace xxx.Rendering.Converters.BOP
{
    public class BOPConverter : IModelConverter, IImageConverter
    {
        public string ConverterName { get { return "Eternal Sonata BOP Model Converter"; } }

        private string readString(BinaryReader br, int len)
        {
            return new System.Text.ASCIIEncoding().GetString(br.ReadBytes(len)).Trim(new[] { '\0' });
        }

        private short readShort(BinaryReader br)
        {
            byte[] buff = br.ReadBytes(2);
            byte[] flipbuff = new byte[2];
            flipbuff[0] = buff[1];
            flipbuff[1] = buff[0];
            return new BinaryReader(new MemoryStream(flipbuff)).ReadInt16();
        }

        private int readInt(BinaryReader br)
        {
            byte[] buff = br.ReadBytes(4);
            byte[] flipbuff = new byte[4];
            flipbuff[0] = buff[3];
            flipbuff[1] = buff[2];
            flipbuff[2] = buff[1];
            flipbuff[3] = buff[0];
            return new BinaryReader(new MemoryStream(flipbuff)).ReadInt32();
        }

        private float readSingle(BinaryReader br)
        {
            byte[] buff = br.ReadBytes(4);
            byte[] flipbuff = new byte[4];
            flipbuff[0] = buff[3];
            flipbuff[1] = buff[2];
            flipbuff[2] = buff[1];
            flipbuff[3] = buff[0];
            return new BinaryReader(new MemoryStream(flipbuff)).ReadSingle();
        }


        bool seekToString(BinaryReader br, string str)
        {
            long pos = br.BaseStream.Position;
            while (pos < br.BaseStream.Length - str.Length)
            {
                br.BaseStream.Position = pos;
                if (string.Equals(readString(br, str.Length), str))
                    return true;
                pos++;
            }
            return false;
        }

        public ImageConversionOutput LoadImages(ConversionInput input)
        {
            if (input == null)
                throw new ArgumentNullException("input");

            ImageConversionOutput output = new ImageConversionOutput { ConversionErrors = new List<string>(), Images = new List<Image>() };

            if (input.Content == null || input.Content.Length == 0)
            {
                output.ConversionErrors.Add("No input provided.");
            }

            BinaryReader br = new BinaryReader(input.Content);


            while (seekToString(br, "NTEX"))
            {
                int chunkSize = readInt(br);

                //only pull out dds
                if (readString(br, 4) != "DDS ")
                    continue;
                br.BaseStream.Position -= 4;

                var pixelBuffer = new byte[0, 0, 0];

                var header = xxx.Rendering.Imaging.DirectDrawSurfaces.DDS.Load(br.BaseStream, out pixelBuffer);

                int linebytes = BMP.line_bytes(header.dwWidth, 24);
                byte[] pixels = new byte[linebytes * header.dwHeight];
                for (int y = 0; y < header.dwHeight; y++)
                {
                    for (int x = 0; x < header.dwWidth; x++)
                    {
                        pixels[(x * 3) + ((header.dwHeight - (y + 1)) * linebytes) + 0] = pixelBuffer[0, x, y];
                        pixels[(x * 3) + ((header.dwHeight - (y + 1)) * linebytes) + 1] = pixelBuffer[1, x, y];
                        pixels[(x * 3) + ((header.dwHeight - (y + 1)) * linebytes) + 2] = pixelBuffer[2, x, y];
                    }
                }
                output.Images.Add(new Image { Bitmap = BMP.save_bmp(header.dwWidth, header.dwHeight, pixels), Name = "" });

            }

            return output;
        }

        private bool HasBit(int flag, int bit)
        {
            if ((flag & bit) == bit)
                return true;
            return false;
        }

        /// <summary>
        ///     Load Eternal Sonata model, (assumed file is decompressed)
        ///     In the demo, files were uncompressed in the image. 
        ///     but in the final release files are compressed with an unknown compression method
        /// </summary>
        public ModelConversionOutput LoadModels(ConversionInput input)
        {

            if (input == null)
                throw new ArgumentNullException("input");

            ModelConversionOutput output = new ModelConversionOutput { ConversionErrors = new List<string>(), Models = new List<Model>() };

            if (input.Content == null || input.Content.Length == 0)
            {
                output.ConversionErrors.Add("No input provided.");
            }

            BinaryReader br = new BinaryReader(input.Content);


            while (seekToString(br, "NSHP"))
            {
                int chunkLength = readInt(br);
                string modelName = readString(br, 16);
                
                //read manualy do to big endianess
                var header = new NSHPHeader();//IOHelper.ReadStruct<NSHPHeader>(br);
                header.Flags1 = readShort(br);
                header.NumVerts = readShort(br);
                header.Flags2 = readShort(br);
                header.NumIndexBuffers = readShort(br);


                if (HasBit(header.Flags2, 1024))
                {

                    //seek past rest of header and bone ref list
                    //really sloppy way to seek past but i cant figure out how to get the length
                    br.BaseStream.Position += 26;

                    //seek past bone ref list? 
                    short boneref = 1;
                    while (boneref > 0 && boneref < 1000)
                        boneref = readShort(br);

                    if (boneref != 0)
                        br.BaseStream.Position -= 2;
                }
                else
                {
                    br.BaseStream.Position += 24;
                }

                Model model = ModelHelper.NewModel(modelName);


                //read vertex buffer
                for (int dex = 0; dex < header.NumVerts; dex++)
                {
                    float x = readSingle(br);
                    float y = readSingle(br);
                    float z = readSingle(br);

                    float nx = 0;
                    float ny = 0;
                    float nz = 0;
                    
                    if (HasBit(header.Flags2, 8) && HasBit(header.Flags2, 16))
                    {
                        nx = readSingle(br);
                        ny = readSingle(br);
                        nz = readSingle(br);
                    }
                    else
                    {
                        readSingle(br);
                        readSingle(br);
                    }
                    if (HasBit(header.Flags2, 32))
                    {
                        readSingle(br);
                        if (HasBit(header.Flags2, 8))
                            readSingle(br);
                    }

                    if (HasBit(header.Flags2, 4))
                        readSingle(br);

                    if (HasBit(header.Flags2, 1024))
                    {
                        float u4 = readSingle(br);
                        float u5 = readSingle(br);
                        float u6 = readSingle(br);
                        float u7 = readSingle(br);
                    }
                    

                    model.Verticies.Add(new Vertex { X = x * 10f, Y = -z * 10f, Z = y * 10f });
                    model.Normals.Add(new Vertex { X = x, Y = z, Z = y });
                    model.UVs.Add(new Vertex { X = 0, Y = 0, Z = 0 });
                }

                //read index buffer headers
                List<IndexBufferHeader> indexHeaders = new List<IndexBufferHeader>();
                if (header.Flags1 != 0)
                {
                    for (int dex = 0; dex < header.NumIndexBuffers; dex++)
                    {
                        //read manualy do to big endianess
                        var ibHeader = new IndexBufferHeader();//IOHelper.ReadStruct<IndexBufferHeader>(br)
                        ibHeader.Unkown1 = readShort(br);
                        ibHeader.Unkown2 = readShort(br);
                        ibHeader.Unkown3 = readShort(br);
                        ibHeader.Unkown4 = readShort(br);
                        ibHeader.Unkown5 = readShort(br);
                        ibHeader.Unkown6 = readShort(br);
                        ibHeader.Unkown7 = readShort(br);

                        ibHeader.NumIndicies = readShort(br);

                        indexHeaders.Add(ibHeader);
                    }
                }

                //read index buffers
                for (int hdex = 0;hdex< header.NumIndexBuffers;hdex++)
                {
                    IndexBufferHeader indexHeader;
                    if (header.Flags1 == 0)
                    {
                        indexHeader = new IndexBufferHeader();
                        indexHeader.Unkown1 = readShort(br);
                        indexHeader.Unkown2 = readShort(br);
                        indexHeader.Unkown3 = readShort(br);
                        indexHeader.Unkown4 = readShort(br);
                        indexHeader.Unkown5 = readShort(br);
                        indexHeader.Unkown6 = readShort(br);
                        indexHeader.Unkown7 = readShort(br);

                        indexHeader.NumIndicies = readShort(br);
                    }
                    else
                        indexHeader = indexHeaders[hdex];

                    short[] poly = new short[3];
                    int polyDex = 0;
                    bool flipFace = false;
                    for (int dex = 0; dex < indexHeader.NumIndicies; dex++)
                    {
                        short s = readShort(br);
                        if (s == -1)
                        {
                            flipFace = false;
                            polyDex = 0;
                        }
                        else
                        {
                            poly[polyDex++] = s;
                            if (polyDex == 3)
                            {
                                if (flipFace)
                                {
                                    model.Faces.Add(new Polygon
                                    {
                                        A = poly[0],
                                        B = poly[1],
                                        C = poly[2]
                                    });
                                }
                                else
                                {
                                    model.Faces.Add(new Polygon
                                    {
                                        A = poly[2],
                                        B = poly[1],
                                        C = poly[0]
                                    });
                                }
                                poly[0] = poly[1];
                                poly[1] = poly[2];
                                polyDex = 2;
                                flipFace = !flipFace;
                            }
                        }
                    }
                }
                if (ModelHelper.Validate(model, output.ConversionErrors))
                    output.Models.Add(model);
            }


            return output;
        }

    }
}

```
## Post #9
- Username: Kar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 25, 2010 8:02 am
- Post datetime: 2010-06-27T22:05:03+00:00
- Post Title: Request: Eternal Sonata models

Ah, much appreciated! But is there a way you could make these files supported in Blender? I don't have anything to open .max files at the moment unfortunately.
## Post #10
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-27T22:18:30+00:00
- Post Title: Request: Eternal Sonata models

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Kar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 25, 2010 8:02 am
- Post datetime: 2010-06-28T17:35:52+00:00
- Post Title: Request: Eternal Sonata models

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-28T18:18:28+00:00
- Post Title: Request: Eternal Sonata models

a blender import script should work.
[http://wiki.blender.org/index.php/Exten ... Import/FBX](http://wiki.blender.org/index.php/Extensions:2.4/Py/Scripts/Import/FBX)
## Post #13
- Username: Ryou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 07, 2010 10:50 pm
- Post datetime: 2010-07-07T18:49:08+00:00
- Post Title: Request: Eternal Sonata models

I managed to separate all models [http://rapidshare.com/files/405558013/t ... models.rar](http://rapidshare.com/files/405558013/trustybell_models.rar) 

anyone have the textures?
## Post #14
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-13T10:02:22+00:00
- Post Title: Request: Eternal Sonata models

It seems that all the links in this thread are expired >_<
I was searching for a method to extract the models of characters and maps from Eternal Sonata for X360!
Have someone found a method to extract both models and textures?
## Post #15
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-03-03T06:15:23+00:00
- Post Title: Request: Eternal Sonata models

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-03T17:17:41+00:00
- Post Title: Re: Request: Eternal Sonata models

i dont think the extractor you used for these models is completely correct this is the basic model structure in max script.
ill try to work on this when i can.

```
if (heapSize < 200000) then
   heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \
caption:"Eternal Sonata Model File" \
types:"Eternal Sonata Model File(*.nmdl)|*.nmdl" \
historyCategory:"Eternal Sonata ObjectPresets"
f = fopen fname "rb"

fn ReadBEShort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 2 1
b = (bit.get short 16)
for i = 17 to 32 do short = bit.set short i b
return short
)

fn PrintOffset Var =
(
   local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
   Var
)

fn floatSwap2 f =
(
   i = bit.floatAsInt f
   h = bit.intashex i
   while h.count < 8 do h = "0" + h
   
   s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
   bit.intAsFloat (bit.hexasint s)
)   

fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
)

   fn convertTo32 input16 = (
      inputAsInt = input16
      sign = bit.get inputAsInt 16
      exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
      fraction = bit.and inputAsInt (bit.hexasint "03FF")
      if sign==true then sign = 1 else sign = 0
      exponentF = exponent + 127
      --Ouput 32 bit integer representing a 32 bit float
      outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
      --Output Check   
      return bit.intasfloat outputasfloat
   )

fn ReadBEHalfFloat fstream = (
return convertTo32(ReadBEword fstream)
)

fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)

fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
)

fn ReadFixedString bstream fixedLen =
(
   local str = ""
   for i = 1 to fixedLen do
   (
      str += bit.intAsChar (ReadByte bstream #unsigned)
   )
   str
)

struct weight_data
(
   boneids,weights
)
struct Offset_data
(
   MyOff,Magic1Size
)
NMDL = ReadFixedString f 4
NMDLSize = ReadBElong f
unk000 = readbyte f#unsigned
unk001 = readbyte f#unsigned
fseek f 0x6#seek_cur
basename = ReadFixedString f 16
unk010 = ReadBEword f
unk011 = ReadBEword f
unk012 = ReadBEword f
unk013 = ReadBEword f
unk014 = ReadBEword f
unk015 = ReadBEword f
unk016 = ReadBEword f
unk017 = ReadBEword f
unk018 = ReadBEword f
unk019 = ReadBEword f
unk01A = ReadBEword f
unk01B = ReadBEword f
unk01C = ReadBEword f
unk01D = ReadBEword f
unk01E = ReadBEword f
unk01F = ReadBEword f

for a = 1 to unk011 Do (
FaceSecArr = #()
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
Counter_array = #()
NSHP = ReadFixedString f 4
NSHPSize = ReadBElong f
NSHPEnd = (ftell f) + (NSHPSize - 8)
mshname = ReadFixedString f 16
print mshname
unk020 = ReadBEword f
VertCount = ReadBEword f
unk022 = ReadBEword f
FaceSections = ReadBEword f
unk024 = readbyte f#unsigned
unk025 = readbyte f#unsigned
unk026 = ReadBEword f
unk027 = ReadBEword f
unk028 = ReadBEword f
unk029 = ReadBEword f
unk02A = ReadBEword f
fseek f 0xC#seek_cur
fseek f (0x2 * unk024)#seek_cur
test = ReadBEword f
if test != 0 do (
fseek f -2#seek_cur
)
for b = 1 to VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
fseek f 0x10#seek_cur
tu = ReadBEHalfFloat f * 2
tv = ReadBEHalfFloat f * -2
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
printoffset (ftell f)
totalface = 0
for b = 1 to FaceSections do (
unk030 = ReadBEword f
unk031 = ReadBEword f
unk032 = ReadBEword f
unk033 = ReadBEword f
unk034 = ReadBEword f
unk035 = ReadBEword f
unk036 = ReadBEword f
Fcount = ReadBEword f
append FaceSecArr unk031
totalface += Fcount
)
FaceEnd = ((ftell f) + (2 * totalface))
StartDirection = 1
Face_array2 = #()
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection
do (
f3 = ReadBEword f
if (f3==0xFFFF) then (
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
append Face_array2 [(f1),(f2),(f3)]
if FaceDirection > 0 then append Face_array [(f1),(f2),(f3)]
else append Face_array [(f1),(f3),(f2)]
)
f1 = f2
f2 = f3
)
)while (ftell f) < (FaceEnd)
printoffset (ftell f)

fseek f NSHPEnd#seek_set
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name = mshname
--msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

print Face_array.count
fpos = 1
for b = 1 to FaceSections do (
newMesh = meshop.detachFaces msh #{fpos..(fpos + (FaceSecArr[b]) - 1)} delete:false asMesh:true
emesh = Editable_mesh() --create an empty Editable_mesh
emesh.mesh = newMesh --assign the detached faces to the new mesh
emesh.name = mshname + "_" + (b as string)
update emesh --update the mesh
fpos += (FaceSecArr[b])
)
delete msh
)
fclose f


```
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-07T04:20:52+00:00
- Post Title: Re: Request: Eternal Sonata models

Thanks chrrox, but how to get nmdl files? From bop or bmd? And how to get textures?
## Post #18
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-03-07T05:46:25+00:00
- Post Title: Re: Request: Eternal Sonata models

It's in the 'root.files'
PS3version is not encrypted.
## Post #19
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-07T09:00:55+00:00
- Post Title: Re: Request: Eternal Sonata models

> Reply from daisuki
>
> It's in the 'root.files'
PS3version is not encrypted.
Ok, how i can unpack those *.files?
## Post #20
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-03-07T09:26:01+00:00
- Post Title: Re: Request: Eternal Sonata models

Sorry, I don't have a *.files bms script.
I used by the Winhex.
## Post #21
- Username: Rlewisrlou666
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 17, 2011 3:00 am
- Post datetime: 2011-03-16T19:10:47+00:00
- Post Title: Re: Request: Eternal Sonata models

Bump.

Hi guys i have been reading thru this and searching all over the net to find a way to extract the .ndml files from the root.files.
Or any other way to extract the models from Eternal Sonata.

I have got the PS3 and Xbox360 discs and i want to extract the models for reference. I've just been given a game to work on with an anime style.

I'm a Computer Games Design Student and want to look at how the models are built I have full use of 3Ds Max, Maya and a bunch of other 3d modelling programs.

Many thanks in advance guys any help will be great.

Ryan.
## Post #22
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T13:28:38+00:00
- Post Title: Re: Request: Eternal Sonata models

Anyone have succeed ripping the model ??
## Post #23
- Username: Rlewisrlou666
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 17, 2011 3:00 am
- Post datetime: 2011-03-17T18:25:04+00:00
- Post Title: Re: Request: Eternal Sonata models

If you use chrrox's Max script to import the PS3 nmdl files you can get a really nice Polka model but i dont think anyone has managed to get a system working to export models from it yet.
## Post #24
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-17T19:52:08+00:00
- Post Title: Re: Request: Eternal Sonata models

export, as in getting models back into the game?

yeah probably not
## Post #25
- Username: Rlewisrlou666
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 17, 2011 3:00 am
- Post datetime: 2011-03-19T13:09:29+00:00
- Post Title: Re: Request: Eternal Sonata models

Not getting them back into game just being able to view and edit them in a program like Maya, 3Ds Max.

Like i said its for research/reference only
## Post #26
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-19T21:01:52+00:00
- Post Title: Re: Request: Eternal Sonata models

lol, why do you keep stressing its for educational reasons? I don't think thats going to make anybody care any more or less about getting you the models
besides it sounds like you already had that polka model, from the previously posted sample. so why would you need anything more then that?
## Post #27
- Username: Rlewisrlou666
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 17, 2011 3:00 am
- Post datetime: 2011-03-22T13:59:12+00:00
- Post Title: Re: Request: Eternal Sonata models

Because I'm modeling Male characters, Polka is a great model to use as reference but i would like to be able to view Alegreto or Beat in a full 3d turn around,

As for me stressing the educational point, I don't know maybe to explain that i'm not just trying to rip the models to use for personal gain or just to copy them and put them in my own games.
I dont want anyone to give me the models i would like someone to explain a process for me to get the models myself to learn how its done.

Whats your reason for wanting them?
## Post #28
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-22T19:59:24+00:00
- Post Title: Re: Request: Eternal Sonata models

lol, you won't use them for personal gain.. dissecting them to increase your own knowledge is personal gain. your reasons are no more modest then the rest.
that's why I don't see the point of stressing your using them for education. like your more entitled to help then the rest?

as for me, I just collect.. but I'm a bit more humble about it. I do try to contribute back, with tutorials, tools, and giving out tips.
## Post #29
- Username: Rlewisrlou666
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 17, 2011 3:00 am
- Post datetime: 2011-03-22T20:35:41+00:00
- Post Title: Re: Request: Eternal Sonata models

@mariokart64n
Yeah sorry about that buddy, I looked at the stuff you have helped out with after i posted and realised that you weren't just trolling.

I'll remember in the future that my education status isn't needed.
I'm still really interested in learning how they managed to get the models from here i ripped the Kingdom Hearts 2 with the help from this site and prob yourself included.

This might be a really NooB question but what language is the script in page 1.
I keep getting errors when i run it in C++, MaxScript, MelScript and i'm going to try C#.

Thanks in advance guys.
## Post #30
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-09-08T21:37:20+00:00
- Post Title: Re: Request: Eternal Sonata models

> Reply from mariokart64n
>
> lol, you won't use them for personal gain.. dissecting them to increase your own knowledge is personal gain. your reasons are no more modest then the rest.
that's why I don't see the point of stressing your using them for education. like your more entitled to help then the rest?

as for me, I just collect.. but I'm a bit more humble about it. I do try to contribute back, with tutorials, tools, and giving out tips.

true that and later post them to their gallery and credit himself for modeling for whatnot. [http://j-century.deviantart.com/gallery ... &offset=72](http://j-century.deviantart.com/gallery/?catpath=/&offset=72). what really pisses me off is he only got the models from a certain site that mariokart64n pertained to on another thread, yet he credit himself and his "team" for the hardwork hehe.

sory about bring up this thread, but i'm getting sick of what the guy is doing because it is just WRONG.
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T23:41:52+00:00
- Post Title: Re: Request: Eternal Sonata models

The hardwork they're crediting themselves for is manually copy-pasting sections of hex from the files, running it through the exporter, getting them into XNAlara, and making poses.

Obviously that is a lot of work. Even if it's for one file, I'm not going to go through such harsh labor just to get one file. I'd rather write an unpacker or wait for someone to write one.

Of course, I only looked at this thread for educational purposes.
And didn't know chrrox wrote a script hidden in the 2nd post. Who would've known. Guess the quest for knowledge is quite useful.
## Post #32
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-02-14T00:48:18+00:00
- Post Title: Re: Request: Eternal Sonata models

What the hell!? He is twisting it so people relly think he did them!? kill him!

I just reported they guy. I like what he does with some pictures but he also claims that he made them, and that is just wrong. If he just where honest and said he only poses and render but no, he has to lie
## Post #33
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T04:04:38+00:00
- Post Title: Re: Request: Eternal Sonata models

Mariokart only mentioned it.
It's not like I credit xentax or MrAdults or chrrox or howfie or whoever in every noesis plugin I make.
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-02-14T18:23:50+00:00
- Post Title: Re: Request: Eternal Sonata models

but when people ask how can I do similar models and how long did it take to make he answers "I don't know, I never count, maybe some days". He does not say "hey, I'm sorry for the wrong impression, I am just rendering"
## Post #35
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T14:03:00+00:00
- Post Title: Re: Request: Eternal Sonata models

I'm sure he does more than just rendering. He still has to pose them and take a screenshot and credit himself
## Post #36
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-01-08T17:05:36+00:00
- Post Title: Re: Request: Eternal Sonata models

Massive necro-post here, but I figured its stupid to open a thread for the exact same files.

Does anyone know how to extract the .files files from the PS3 edition of the game? 

I can provide an example filecutter if anyones interested.
## Post #37
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-01-17T19:30:41+00:00
- Post Title: Re: Request: Eternal Sonata models

@lionheartuk
Here is my old tool for *.files from this game. 
I used chrrox's  script from [viewtopic.php?p=50276#p50276](http://forum.xentax.com/viewtopic.php?p=50276#p50276) .
It requires Blender 249 and Python 26.
It unpack *.files and import   *.p3obj, *.bob and *.e files. 
It is not good for all models.
There are problems with skinweighting and skeleton. 

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
- files for archives
- p3obj, bob, e for textured models
[Blender249[EternalSonata][PS3][files][p3obj][bob][e][2015-01-17].zip](https://xentaxbackup.github.io/file/8497_Blender249[EternalSonata][PS3][files][p3obj][bob][e][2015-01-17].zip)
## Post #38
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-01-18T13:03:58+00:00
- Post Title: Re: Request: Eternal Sonata models

> Reply from Szkaradek123
>
> @lionheartuk
Here is my old tool for *.files from this game. 
I used chrrox's  script from viewtopic.php?p=50276#p50276 .
It requires Blender 249 and Python 26.
It unpack *.files and import   *.p3obj, *.bob and *.e files. 
It is not good for all models.
There are problems with skinweighting and skeleton. 

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
- files for archives
- p3obj, bob, e for textured models

Awesome, thankyou! It doesn't seem to be able to grab environments though, even if they're .bob or .e files

Do you have any idea how to convert the p3tex files (I assume these are map textures, they're in maptex, but I suppose they COULD be text but it doesn't look like it).
