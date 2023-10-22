## Post #1
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2014-12-01T04:37:01+00:00
- Post Title: help with animation files

Hello, I need help with these files as import and export for 3dmax

look at the example I'll be wrong?



here sample
[https://mega.co.nz/#!hUMziKzJ!wNwesyB2M ... 3khkY6eWyg](https://mega.co.nz/#!hUMziKzJ!wNwesyB2MxECPIX8nWA3mcVMVVT866kug3khkY6eWyg)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-01T12:02:54+00:00
- Post Title: help with animation files

Hi wolfen,
long time no seen.  
Nice to see you starting to analyze.
Here's a short maxscript to log the IDs and bonenames:

```

function ReadModelFile fName =
(     
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"         -- Open the file for reading
    ID_ = readlong stream
    boneCount = readlong stream
    unkn = readlong stream

    for i = 1 to BoneCount Do (
        BoneID = readlong stream
        BParID = readlong stream
        addr = ftell stream
        boneName = readString stream        
        --print (i as string+". "+boneName)
        format " % % %\n" BoneID BParID boneName
        addr += 64; fseek stream addr #seek_set   
    )

    print ("@ 0x"+ bit.intAsHex(ftell stream) as string)		   
    fClose stream
)

-- entry point --

fname = getOpenFileName \
caption:" open Pko 3D Model" \
types:"3D Model (*.lab)|*.lab"
--historyCategory:"3D Model lab
format "fname: %\n" fname
   
ReadModelFile fname
```


Sadly I can't find valuable data here other than boneId, bone parent ID and bonename:



test_lab.JPG (88.32 KiB) Viewed 376 times



What about the PkoSDK?
Did you ever try to export a *.DAE file after loading a *.lab?
You could import the dae to your 3D app and look whether animations are contained.

(From this post [viewtopic.php?f=16&t=11533&p=94804#p94804](http://forum.xentax.com/viewtopic.php?f=16&t=11533&p=94804#p94804)
I can see I found some matrices but I won't restart fiddeling out what I did there.)
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-02T10:37:39+00:00
- Post Title: help with animation files

hi

fbx:

[http://www.mediafire.com/download/4d45c ... 2/test.zip](http://www.mediafire.com/download/4d45cu94bkvveh2/test.zip)

unpack and open in Noesis.

I used file research done by shakotay2 at [viewtopic.php?p=94811#p94811](http://forum.xentax.com/viewtopic.php?p=94811#p94811)

I think this format is from game  Tales of Pirates 2.

Lab format is container for animations

header:

int32 - unk
int32 - bone count
int32 - frame count 
int32 - animation count, if 0 than we have 1 animation
int32 - method:  1 for  matrices4x3 and  3 for quaternions and vectors
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-02T11:23:41+00:00
- Post Title: help with animation files

> Reply from Szkaradek123
>
> I think this format is from game  Tales of Pirates 2.Hi Szkaradek123,
awful animation!  
thank u very much!  

@wolfen: could you tell me which model is used (and maybe PM the *.lgo to me if you have it?) so that I could apply the mesh to the animation skeleton.

I remember me having made an .lgo to obj mesh exporter two years ago:
[http://www.uploadmb.com/dw.php?id=1417519307](http://www.uploadmb.com/dw.php?id=1417519307)

(more infos as a reminder for me:
Pko -> Pirate king online
MindPower engine

> Reply from fatduck
>
> It is the same format of "Zero of the World".
Use FatImporter
finale00: [viewtopic.php?f=16&t=6977&p=57694&hilit=pirates#p57694](http://forum.xentax.com/viewtopic.php?f=16&t=6977&p=57694&hilit=pirates#p57694)
)
## Post #5
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2014-12-03T04:52:17+00:00
- Post Title: help with animation files

these are the files that use
[https://mega.co.nz/#!Ydc0xSbY!DpmVGrgDr ... je4ozc4fT0](https://mega.co.nz/#!Ydc0xSbY!DpmVGrgDr_rowKKqTr6ry-NKaw8HJYodqje4ozc4fT0)
guided me with this information

```
{
    public class lwMatrix44
    {
        private float[] data;

        public lwMatrix44()
        {
            data = new float[16];
            for (int i = 0 ; i < 16 ; i++)
            {
                data[i] = 0.0f;
            }
        }

        public float this[int x, int y]
        {
            get
            {
                int _x = x - 1;
                int _y = y - 1;
                return (this.data[(_x * 4) + _y]);
            }
            set
            {
                int _x = x - 1;
                int _y = y - 1;
                this.data[(_x * 4) + _y] = value;
            }
        }

        public void ConvertFromLeftHanded()
        {
            lwMatrix44 tmp = new lwMatrix44();
            tmp[1,1] = this[1,1];
            tmp[1,2] = this[1,3];
            tmp[1,3] = this[1,2];
            tmp[1,4] = this[1,4];

            tmp[2,1] = this[3,1];
            tmp[2,2] = this[3,3];
            tmp[2,3] = this[3,2];
            tmp[2,4] = this[2,4];

            tmp[3,1] = this[2,1];
            tmp[3,2] = this[2,3];
            tmp[3,3] = this[2,2];
            tmp[3,4] = this[3,4];

            tmp[4,1] = this[4,1];
            tmp[4,2] = this[4,3];
            tmp[4,3] = this[4,2];
            tmp[4,4] = this[4,4];

            this.data = tmp.data;
        }

        public void ConvertFromMindPower()
        {
            lwMatrix44 tmp = new lwMatrix44();
            tmp[1, 1] = this[1, 1];
            tmp[1, 2] = -this[1, 3];
            tmp[1, 3] = this[1, 2];
            tmp[1, 4] = this[1, 4];

            tmp[2, 1] = -this[3, 1];
            tmp[2, 2] = this[3, 3];
            tmp[2, 3] = -this[3, 2];
            tmp[2, 4] = this[2, 4];

            tmp[3, 1] = this[2, 1];
            tmp[3, 2] = -this[2, 3];
            tmp[3, 3] = this[2, 2];
            tmp[3, 4] = this[3, 4];

            tmp[4, 1] = this[4, 1];
            tmp[4, 2] = -this[4, 3];
            tmp[4, 3] = this[4, 2];
            tmp[4, 4] = this[4, 4];

            this.data = tmp.data;
        }

        public lwMatrix44(D3DXQuaternion q, D3DXVector3 p) : this()
        {
            float wx, wy, wz, xx, yy, yz, xy, xz, zz, x2, y2, z2;

            q.normalize();
            
            // calculate coefficients
            x2 = q.x + q.x;
            y2 = q.y + q.y;
            z2 = q.z + q.z;

            xx = q.x * x2;
            xy = q.x * y2;
            xz = q.x * z2;

            yy = q.y * y2;
            yz = q.y * z2;
            zz = q.z * z2;

            wx = q.w * x2;
            wy = q.w * y2;
            wz = q.w * z2;


            this[1 ,1] = 1.0f - (yy + zz);
            this[1, 2] = xy + wz;
            this[1, 3] = xz - wy;
            this[1, 4] = 0;

            this[2, 1] = xy - wz;
            this[2, 2] = 1.0f - (xx + zz);
            this[2, 3] = yz + wx;
            this[2, 4] = 0;

            this[3, 1] = xz + wy;
            this[3, 2] = yz - wx;
            this[3, 3] = 1.0f - (xx + yy);
            this[3, 4] = 0;

            this[4, 1] = p.x;
            this[4, 2] = p.y;
            this[4, 3] = p.z;
            this[4, 4] = 1.0f;
        }

        public lwMatrix44(lwMatrix43 m) : this()
        {
            this[1, 1] = m[1,1];
            this[1, 2] = m[1,2];
            this[1, 3] = m[1,3];

            this[2, 1] = m[2,1];
            this[2, 2] = m[2,2];
            this[2, 3] = m[2, 3];

            this[3, 1] = m[3, 1];
            this[3, 2] = m[3, 2];
            this[3, 3] = m[3, 3];

            this[4, 1] = m[4, 1];
            this[4, 2] = m[4, 2];
            this[4, 3] = m[4, 3];

            this[1, 4] = 0;
            this[2, 4] = 0;
            this[3, 4] = 0;
            this[4, 4] = 1.0f;
        }
    }
    

    public class lwMatrix43
    {
       private float[] data;

        public lwMatrix43()
        {
            data = new float[12];
            for (int i = 0 ; i < 12 ; i++)
            {
                data[i] = 0.0f;
            }
        }

        public float this[int x, int y]
        {
            get
            {
                int _x = x - 1;
                int _y = y - 1;
                return (this.data[(_x * 3) + _y]);
            }
            set
            {
                int _x = x - 1;
                int _y = y - 1;
                this.data[(_x * 3) + _y] = value;
            }
        }

        public void ConvertFromLeftHanded()
        {
            lwMatrix43 tmp = new lwMatrix43();
            tmp[1, 1] = this[1, 1];
            tmp[1, 2] = this[1, 3];
            tmp[1, 3] = this[1, 2];
            tmp[1, 4] = this[1, 4];

            tmp[2, 1] = this[3, 1];
            tmp[2, 2] = this[3, 3];
            tmp[2, 3] = this[3, 2];
            tmp[2, 4] = this[2, 4];

            tmp[3, 1] = this[2, 1];
            tmp[3, 2] = this[2, 3];
            tmp[3, 3] = this[2, 2];
            tmp[3, 4] = this[3, 4];

            this.data = tmp.data;
        }

        public void ConvertFromMindPower()
        {
            lwMatrix43 tmp = new lwMatrix43();
            tmp[1, 1] = this[1, 1];
            tmp[1, 2] = -this[1, 3];
            tmp[1, 3] = this[1, 2];
            tmp[1, 4] = this[1, 4];

            tmp[2, 1] = -this[3, 1];
            tmp[2, 2] = this[3, 3];
            tmp[2, 3] = -this[3, 2];
            tmp[2, 4] = this[2, 4];

            tmp[3, 1] = this[2, 1];
            tmp[3, 2] = -this[2, 3];
            tmp[3, 3] = this[2, 2];
            tmp[3, 4] = this[3, 4];

            this.data = tmp.data;
        }
    }

    public struct D3DXVector3
    {
        public float x;
        public float y;
        public float z;

        public void ConvertFromLeftHanded()
        {
            float tmp = y;
            y = z;
            z = tmp;
        }

        public void ConvertFromMindpower()
        {
            float tmp = y;
            y = -z;
            z = tmp;
        }
    }

    public struct D3DXQuaternion
    {
        public float x;
        public float y;
        public float z;
        public float w;

        public void normalize()
        {
            float magnitude = (float)Math.Sqrt((x*x + y*y + z*z + w*w));
            w /= magnitude;
            x /= magnitude;
            y /= magnitude;
            z /= magnitude;
        }
    }

    struct lwBoneInfoHeader 
    {
        public UInt32 boneCount;
        public UInt32 frameCount;
        public UInt32 dummyCount;
        public UInt32 keyType;
    }

    struct lwBoneBaseInfo
    {
        public string name; // size = 64
        public UInt32 id;
        public Int32 parentId;
    }

    struct lwBoneDummyInfo
    {
        public UInt32 id;
        public Int32 parentBoneId;
        public lwMatrix44 mat;
    }


    class lwBoneKeyInfo
    {
        public List<lwMatrix44> mat44List;
        public List<D3DXVector3> positionList;
        public List<D3DXQuaternion> quaternionList;
    }

    class LabData
    {
        public lwBoneInfoHeader header;
        public List<lwBoneBaseInfo> boneBaseList;
        public List<lwBoneDummyInfo> boneDummyList;
        public List<lwBoneKeyInfo> boneKeyInfoList;
        public List<lwMatrix44> invMatList;
    }
}

```

fatimport script to use in 3dmax import work
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-03T12:04:03+00:00
- Post Title: help with animation files

thank you!  
Here's lance (again after 2 years  ):



lance.JPG (102.74 KiB) Viewed 335 times



Now I've to find the weights before I can apply the mesh to the animated skeleton.
Will take some time...
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-03T16:20:35+00:00
- Post Title: help with animation files

Hi 

Here is importer for models and animation from this format.
I tested it with files from Tales of Pirates 2,  ans samples send by wolfen.
It requires Blender version 249 and Python 26.


Steps:
-press alt+p and select lgo files - skinned meshes
-press alt+p and select lab files - animations

Sorry , but no export
[Blender249[MindPower][PC][lgo][lag][2014-12-03].zip](https://xentaxbackup.github.io/file/8188_Blender249[MindPower][PC][lgo][lag][2014-12-03].zip)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-03T17:05:46+00:00
- Post Title: help with animation files

thank you very much!  

On my hunt for the weights I was successful, meanwhile, just wondering why they used 2 weigths/ bones per vertex only.
0000010002.lgo

```
 1.000000 0.000000  00 00 00 00 00 00 00 00 01 02 00 00 
 1.000000 0.000000  00 00 00 00 00 00 00 00 01 02 00 00 
 1.000000 0.000000  00 00 00 00 00 00 00 00 03 00 00 00 
 0.870000 0.130000  00 00 00 00 00 00 00 00 03 00 00 00 
 0.870000 0.130000  00 00 00 00 00 00 00 00 03 00 00 00 
 0.540000 0.460000  00 00 00 00 00 00 00 00 03 00 00 00 
 0.540000 0.460000  00 00 00 00 00 00 00 00 04 03 00 00 
```


Think I'll try to finish building the skinned skeleton on my own before I try out your solution.

I updated my ToP MeshExtractor, so that the delta value isn't needed any more in most cases (hopefully).
Poorly tested, as always:
[http://www.uploadmb.com/dw.php?id=1417626661](http://www.uploadmb.com/dw.php?id=1417626661)

This is the aim to be achieved (skinned skeleton):



lance_ani.JPG (34.26 KiB) Viewed 290 times
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-28T17:43:58+00:00
- Post Title: help with animation files

looks like I've checked the "autoset" feature with too less files so there's weird FIs with 01010029.lgo for example.

The new version hopefully fixes this:


 ToP_MeshExtract.zip
(10.05 KiB) Downloaded 44 times
## Post #10
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-12-08T17:31:13+00:00
- Post Title: help with animation files

> Reply from shakotay2
>
> looks like I've checked the "autoset" feature with too less files so there's weird FIs with 01010029.lgo for example.

The new version hopefully fixes this:
ToP_MeshExtract.zip
 how i use your tool?
im very interesting in import and export lgo format
## Post #11
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-12-08T17:45:53+00:00
- Post Title: help with animation files

> Reply from Szkaradek123
>
> Hi 

Here is importer for models and animation from this format.
I tested it with files from Tales of Pirates 2,  ans samples send by wolfen.
It requires Blender version 249 and Python 26.


Steps:
-press alt+p and select lgo files - skinned meshes
-press alt+p and select lab files - animations

Sorry , but no export

I tried ur tool and got this error, maybe is python version?
