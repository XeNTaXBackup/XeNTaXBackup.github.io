## Post #1
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-12T21:05:44+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Hello!

I really could need your help.

I want to create the possibility to create new Tracks for Need for Speed Shift and this is only possible with the SGB Files. The problem is they are only binary.

3D SimEd can Open and Read them to Display the whole Track. (you can try this with the Demo on [http://www.sim-garage.co.uk](http://www.sim-garage.co.uk))

So I would be really happy if you help me my to "write" new SGB Files. Or help to Research them.

I Upload one Track from Shift as Sample. Hopefully this helps.

[http://ul.to/ai8fch](http://ul.to/ai8fch)
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-24T01:41:06+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Sorry if I stretch your nerves but can no one help there?

I got success converting Binary Material Files into Human Readable Code (XML) which can be used for modding because Shift reads them too. Almost all Shift Files are XML-Styled or Binary XML Files, expect Shaders, Textures, Models, Sounds, Motec/HUD-Files (if I have forgotten nothing):) I can convert the Material Files but only manually which is easy for relative little Material Files but the Track Files contains some thousands entries. (Depends on Track)

It would be really nice if someone could look into it.
## Post #3
- Username: crick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 23, 2010 3:17 am
- Post datetime: 2010-07-12T23:02:24+00:00
- Post Title: Need for Speed: Shift Track SGB Files

bump   
can some one look into this please
## Post #4
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-14T20:22:30+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Perhaps you could provide a new sample?
The file linked in the original post is no longer available.
## Post #5
- Username: crick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 23, 2010 3:17 am
- Post datetime: 2010-07-16T15:21:59+00:00
- Post Title: Need for Speed: Shift Track SGB Files

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-19T05:52:54+00:00
- Post Title: Need for Speed: Shift Track SGB Files

The file contains six sections: SGB, OCCL, NODE, FLAT, SUMM and END.
Following after END is strings, or nothing if there are no strings.

Each section start with:
32bit int section name
32bit int section length
32bit int number of blocks in section

SGB
Just a section header + 1 all zero byte.

OCCL
Each block is a 56 byte structure.
The first 8 bytes of each block are two 32bit integers containing string positions (some name, and a file path e.g. "OCCLUDER02", "Tracks\Alpental\OCCLUDER02.meb").
The rest so far unknown.

In NODE and SUMM each block starts with a 32bit int containing the block size.
There are repeated references (integers containing position in file) to other places in the section, which in turn references the strings (integers containing position in file).
These are mostly (always?) referencing the start of a 40 byte block starting by three ints containing string positions (OBJECT, some name, some file path e.g. "OBJECT", "Tyres2_LODA", "Tracks\Alpental\Tyres2_LODA.imb") followed by some values repeated from the containing block

FLAT: 
Always seems to consist of one block.

END: Just a section header

One funny thing, I've seen three files, one with big endian section names and two with little endian section names.
It seems the length of the SGB section is in the same endianness as the section names, all other lengths and data are in the opposite.
## Post #7
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-07-20T19:03:12+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Thank you very much for looking into them.

Hope we are able to convert them into XML-Based Files soon.

I think the first name could be the Instance Name - OCCLUDER02
Then follows the MeshName (meb are 3D Files of Shift) - Tracks\Alpental\OCCLUDER02.meb

Other unknown things could be CollTarget and HATTarget, ShadowReceiver.

I attach some Track-Files from GTR 2 and rFactor - they are really similar to Shift ones for sure. Only thing which is different (99% sure) - Shift Ones are XML-Based. (When converted oc)

rFactor: [http://pastebin.com/ekFHcW00](http://pastebin.com/ekFHcW00)
GTR 2: [http://pastebin.com/P5k0q9Ax](http://pastebin.com/P5k0q9Ax)

And now one Material Sample how they look XML-Based. (From Shift)

[http://pastebin.com/vhbn6Mvd](http://pastebin.com/vhbn6Mvd)
## Post #8
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-21T07:25:24+00:00
- Post Title: Need for Speed: Shift Track SGB Files

For the NODE and SUMM parts I would guess it should be possible to map the values to a structure similar to the referenced .vhf file

One block from SUMM

```
    325712  ----    0000078A    1930                    0.000000
    325716  string reference (821981): -><-
    325720  string reference (839718): ->tracks\_data\instances\gen_tree10_loda.vhf<-
    325724  ----    00000000    0                       0.000000
    325728  ----    00000018    24                      0.000000
    325732  ----    00000001    1                       0.000000
    325736  string reference (821982): ->LOD<-
    325740  string reference (839761): ->GEN_TREE10_LOD0<-
    325744  ----    00000000    0                       0.000000
    325748  ----    00000018    24                      0.000000
    325752  ----    BF7603EC    -1082784788             -0.960997
    325756  ----    41267816    1093040150              10.404318
    325760  ----    BF08A9B0    -1089951312             -0.533839
    325764  ----    41584419    1096303641              13.516625
    325768  ----    010100FF    16843007                0.000000
    325772  ----    C3E0C4BC    -1008679748             -449.536987
    325776  ----    C089C005    -1064714235             -4.304690
    325780  ----    C344F26F    -1018891665             -196.947006
    325784  ----    00000000    0                       0.000000
    325788  ----    BDEB820F    -1108639217             -0.114994
    325792  ----    00000000    0                       0.000000
    325796  ----    3F7E4D3F    1065241919              0.993366
    325800  ----    3F789922    1064868130              0.971087
    325804  ----    FFFFFFFF    -1                      -nan
    325808  ----    00000000    0                       0.000000
    325812  ----    0004F8B8    325816                  0.000000                        (325816 is ref to self)
    325816  string reference (822004): ->OBJECT<-
    325820  string reference (839777): ->Gen_Tree10_LODA<-
    325824  string reference (839793): ->Tracks\_Data\Instances\Gen_Tree10_LODA.imb<-
    325828  ----    00000018    24                      0.000000
    325832  ----    BF7603EC    -1082784788             -0.960997
    325836  ----    41267816    1093040150              10.404318
    325840  ----    BF08A9B0    -1089951312             -0.533839
    325844  ----    41584419    1096303641              13.516625
    325848  ----    00000000    0                       0.000000
    325852  ----    00000150    336                     0.000000

```


gen_tree10_loda.vhf:

```
    <NODE type="LOD" Name="GEN_TREE10_LOD0" MatrixNumber="-1" matrices="1" subobjects="1">
        <SPHERE Centre="-0.960997 10.404318 -0.533839 1.000000" Radius="13.516625" />
        <MATRIX Offset="-0.417953 0.000000 0.000000" Orientation="0.000000 0.000000 0.000000 1.000000" />
        <NODE type="OBJECT" Name="Gen_Tree10_LODA" MatrixNumber="0" instances="1" userflags="336">
            <RESOURCE Filename="Tracks\_Data\Instances\Gen_Tree10_LODA.imb" />
            <SPHERE Centre="-0.960997 10.404318 -0.533839 1.000000" Radius="13.516625" />
        </NODE>
        <CONTROL Distances="0 " />
    </NODE>
</CAR>
```


The values seems to match to a large extent, but some seem different and some I'm missing, maybe they are implicit. We will see...
## Post #9
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-07-21T17:36:15+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Thank you very much 

I think you are very right !!!

I found a existing SGX File and yes it looks like the VHF Ones. (Menu Background - no Track but I am sure there are no big differences:))

Any idea about the Partitions??

```
<SCENE FileVersion="0.1.0.0" ExporterVersion="Blimey Tools v1.066" NumObjects="0" NumPartitions="5">
    <OBJ_ID no="1">
        <NODE type="OBJECT" Name="background01" MatrixNumber="-1" instances="1" userflags="256">
            <RESOURCE Filename="GUI\Menu_Background\background01.meb" />
            <SPHERE Centre="0.265718 1.649576 -0.133457 1.000000" Radius="19.991062" />
            <MATRIX Offset="-0.218717 7.078418 0.086456" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="2">
        <NODE type="OBJECT" Name="Box01" MatrixNumber="-1" instances="1" userflags="352">
            <RESOURCE Filename="GUI\Menu_Background\Box01.meb" />
            <SPHERE Centre="0.000000 0.000000 0.000000 1.000000" Radius="11.547319" />
            <MATRIX Offset="0.000000 0.000000 0.000000" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="3">
        <NODE type="OBJECT" Name="canopy01" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\canopy01.meb" />
            <SPHERE Centre="0.199664 -3.046432 0.041888 1.000000" Radius="13.349008" />
            <MATRIX Offset="-0.165286 4.000000 -0.056393" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="4">
        <NODE type="OBJECT" Name="lensflare_on_a_stick" MatrixNumber="-1" instances="1" userflags="4352">
            <RESOURCE Filename="GUI\Menu_Background\lensflare_on_a_stick.meb" />
            <SPHERE Centre="0.000000 0.000000 0.000000 1.000000" Radius="0.707107" />
            <MATRIX Offset="0.000000 0.000000 0.000000" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="5">
        <NODE type="OBJECT" Name="Plane01" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane01.meb" />
            <SPHERE Centre="-0.124477 3.288883 0.000000 1.000000" Radius="6.453819" />
            <MATRIX Offset="-4.627467 0.000000 8.433906" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="6">
        <NODE type="OBJECT" Name="Plane01_copy01" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane01_copy01.meb" />
            <SPHERE Centre="-0.169971 3.288883 -0.096576 1.000000" Radius="5.831209" />
            <MATRIX Offset="4.340472 0.000000 -8.173466" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="7">
        <NODE type="OBJECT" Name="Plane01_copy01_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane01_copy01_flipped.meb" />
            <SPHERE Centre="-0.081509 3.288883 -1.165686 1.000000" Radius="5.957093" />
            <MATRIX Offset="8.446180 0.000000 5.083596" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="8">
        <NODE type="OBJECT" Name="Plane01_copy02_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane01_copy02_flipped.meb" />
            <SPHERE Centre="0.000049 3.288883 -0.450282 1.000000" Radius="5.855421" />
            <MATRIX Offset="-9.483070 0.000000 -3.759705" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="9">
        <NODE type="OBJECT" Name="Plane02" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane02.meb" />
            <SPHERE Centre="0.686900 3.288883 -0.146861 1.000000" Radius="5.695477" />
            <MATRIX Offset="-4.577936 0.000000 6.957845" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="10">
        <NODE type="OBJECT" Name="Plane02_copy01" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane02_copy01.meb" />
            <SPHERE Centre="-0.205161 3.288883 0.119712 1.000000" Radius="4.968668" />
            <MATRIX Offset="3.542260 0.000000 -7.221136" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="11">
        <NODE type="OBJECT" Name="Plane02_copy01_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane02_copy01_flipped.meb" />
            <SPHERE Centre="-0.332035 3.288883 -0.880271 1.000000" Radius="4.980958" />
            <MATRIX Offset="7.036367 0.000000 4.129752" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="12">
        <NODE type="OBJECT" Name="Plane02_copy02_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane02_copy02_flipped.meb" />
            <SPHERE Centre="-0.000000 3.288883 0.492196 1.000000" Radius="5.166797" />
            <MATRIX Offset="-8.051533 0.000000 -3.913574" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="13">
        <NODE type="OBJECT" Name="Plane03" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane03.meb" />
            <SPHERE Centre="1.663440 3.288883 0.000000 1.000000" Radius="5.902038" />
            <MATRIX Offset="2.806008 0.000000 8.444822" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="14">
        <NODE type="OBJECT" Name="Plane03_copy01" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane03_copy01.meb" />
            <SPHERE Centre="-0.696215 3.288883 0.053141 1.000000" Radius="6.536627" />
            <MATRIX Offset="-4.120506 0.000000 -8.331539" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="15">
        <NODE type="OBJECT" Name="Plane03_copy01_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane03_copy01_flipped.meb" />
            <SPHERE Centre="0.000001 3.288883 -1.022127 1.000000" Radius="5.765039" />
            <MATRIX Offset="8.363670 0.000000 -3.302207" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="16">
        <NODE type="OBJECT" Name="Plane03_copy02_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane03_copy02_flipped.meb" />
            <SPHERE Centre="0.000001 3.288883 0.993280 1.000000" Radius="5.943533" />
            <MATRIX Offset="-9.452579 0.000000 3.408917" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="17">
        <NODE type="OBJECT" Name="Plane04" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane04.meb" />
            <SPHERE Centre="0.813290 3.288883 -0.000000 1.000000" Radius="5.019483" />
            <MATRIX Offset="2.655695 0.000000 6.808184" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="18">
        <NODE type="OBJECT" Name="Plane04_copy01" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane04_copy01.meb" />
            <SPHERE Centre="0.200999 3.288883 -0.000000 1.000000" Radius="5.715281" />
            <MATRIX Offset="-4.175101 0.000000 -7.080558" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="19">
        <NODE type="OBJECT" Name="Plane04_copy01_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane04_copy01_flipped.meb" />
            <SPHERE Centre="0.000000 3.288883 -0.357754 1.000000" Radius="5.231984" />
            <MATRIX Offset="6.728292 0.000000 -3.251679" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="20">
        <NODE type="OBJECT" Name="Plane04_copy02_flipped" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane04_copy02_flipped.meb" />
            <SPHERE Centre="0.000001 3.288883 0.067990 1.000000" Radius="5.090075" />
            <MATRIX Offset="-8.053748 0.000000 3.345431" Orientation="0.000000 0.000000 0.000000 1.000000" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="21">
        <NODE type="OBJECT" Name="Plane05" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane05.meb" />
            <SPHERE Centre="0.617821 3.987296 3.313348 1.000000" Radius="6.487174" />
            <MATRIX Offset="-3.607941 0.000000 3.646768" Orientation="0.000000 0.460401 0.000000 0.887711" />
        </NODE>
    </OBJ_ID>
    <OBJ_ID no="22">
        <NODE type="OBJECT" Name="Plane07" MatrixNumber="-1" instances="1" userflags="320">
            <RESOURCE Filename="GUI\Menu_Background\Plane07.meb" />
            <SPHERE Centre="-0.207717 2.873017 0.280934 1.000000" Radius="4.578554" />
            <MATRIX Offset="3.048553 0.000000 -3.640991" Orientation="0.000000 0.871015 0.000000 -0.491256" />
        </NODE>
    </OBJ_ID>
    <PARTITION_ID no="0">
        <AABBOX min="-17.873489 -12.395439 -17.967491" max="17.967491 17.587719 17.873489" />
        <CHILD_PARTITIONS IDs="1 2 3 4 " />
        <CHILD_OBJS IDs="2 3 1 " />
    </PARTITION_ID>
    <PARTITION_ID no="1">
        <AABBOX min="-10.570891 -0.707107 -0.845085" max="4.634969 7.234096 9.649479" />
        <CHILD_PARTITIONS IDs="NONE" />
        <CHILD_OBJS IDs="5 9 21 16 20 4 " />
    </PARTITION_ID>
    <PARTITION_ID no="2">
        <AABBOX min="-0.730785 0.497535 -1.344726" max="9.669682 6.080231 9.180545" />
        <CHILD_PARTITIONS IDs="NONE" />
        <CHILD_OBJS IDs="13 17 7 11 " />
    </PARTITION_ID>
    <PARTITION_ID no="3">
        <AABBOX min="-10.727380 0.497535 -9.357251" max="1.093937 6.080231 0.937277" />
        <CHILD_PARTITIONS IDs="NONE" />
        <CHILD_OBJS IDs="8 12 14 18 " />
    </PARTITION_ID>
    <PARTITION_ID no="4">
        <AABBOX min="-0.949203 0.497535 -9.368545" max="9.290205 6.080231 0.815727" />
        <CHILD_PARTITIONS IDs="NONE" />
        <CHILD_OBJS IDs="22 6 10 15 19 " />
    </PARTITION_ID>
</SCENE>

```
## Post #10
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-25T11:09:21+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Assuming the above format the block could look like

```
<!-- objhead_t num_of_type=24  unknown=00000001 -->
<!-- objhead_t str2: tracks\_data\instances\gen_tree10_loda.vhf -->
        <!-- head subobjects=1 matrices=1 unknown=0 matrix_number=-1 -->
        <NODE type="LOD" Name="GEN_TREE10_LOD0" MatrixNumber="-1" matrices="1" subobjects="1">
                <SPHERE Centre="-0.960997 10.404318 -0.533839 1.000000" Radius="13.516625" />
                <MATRIX id="0" Offset="-449.536987 -4.304690 -196.947006" Orientation="0.000000 0.000000 -0.114994 1.000000" />
                <CONTROL Distances="0.000000 " />
                <!-- obj num_of_type=24 matrix_number=0 unknown=0 matrices=0 subobjects=0 -->
                <NODE type="OBJECT" Name="Gen_Tree10_LODA" MatrixNumber="0" instances="?" userflags="336">
                        <RESOURCE Filename="Tracks\_Data\Instances\Gen_Tree10_LODA.imb" />
                        <SPHERE Centre="-0.960997 10.404318 -0.533839 1.000000" Radius="13.516625" />
                </NODE>
        </NODE>
</OBJ_ID>

```


Assuming the first int is the object number, they seem to be unique (in the file, don't know between files).
I'm not really sure what to do with the vhf file reference, and I'm not sure about the orientation part of the matrix, there are two more values somehow belonging to the matrix.

The same block as before but with some comments on what the values are

```
    //ID
    325712  ----    0000078A    1930                    0.000000
    //Three string references
    325716  string reference (821981): -><-
    325720  string reference (839718): ->tracks\_data\instances\gen_tree10_loda.vhf<-
    325724  ----    00000000    0                       0.000000
    //Number of elements with this name
    325728  ----    00000018    24                      0.000000
    //Unknown
    325732  ----    00000001    1                       0.000000

    //Child object
    //Three string references
    325736  string reference (821982): ->LOD<-
    325740  string reference (839761): ->GEN_TREE10_LOD0<-
    325744  ----    00000000    0                       0.000000
    //Number of elements with this name
    325748  ----    00000018    24                      0.000000
    //SPHERE center,radius
    325752  ----    BF7603EC    -1082784788             -0.960997
    325756  ----    41267816    1093040150              10.404318
    325760  ----    BF08A9B0    -1089951312             -0.533839
    325764  ----    41584419    1096303641              13.516625
    //Four bytes, number of child element, number of matrices, unknown, matrix number
    325768  ----    010100FF    16843007                0.000000
    //Matrix first three are position, last is parent (-1 = no parent)
    325772  ----    C3E0C4BC    -1008679748             -449.536987
    325776  ----    C089C005    -1064714235             -4.304690
    325780  ----    C344F26F    -1018891665             -196.947006
    325784  ----    00000000    0                       0.000000
    325788  ----    BDEB820F    -1108639217             -0.114994
    325792  ----    00000000    0                       0.000000
    325796  ----    3F7E4D3F    1065241919              0.993366
    325800  ----    3F789922    1064868130              0.971087
    325804  ----    FFFFFFFF    -1                      -nan
    //One CONTROL Distance value per child
    325808  ----    00000000    0                       0.000000
    //One reference per child
    325812  ----    0004F8B8    325816                  0.000000                        (325816 is ref to self)

    //Sub object
    //Three string references
    325816  string reference (822004): ->OBJECT<-
    325820  string reference (839777): ->Gen_Tree10_LODA<-
    325824  string reference (839793): ->Tracks\_Data\Instances\Gen_Tree10_LODA.imb<-
    //Number of elements with this name
    325828  ----    00000018    24                      0.000000
    //SPHERE
    325832  ----    BF7603EC    -1082784788             -0.960997
    325836  ----    41267816    1093040150              10.404318
    325840  ----    BF08A9B0    -1089951312             -0.533839
    325844  ----    41584419    1096303641              13.516625
    //Matrix ID
    325848  ----    00000000    0                       0.000000
    //Userflags
    325852  ----    00000150    336                     0.000000

```


As for CollTarget and HATTarget and ShadowReceiver, I have one unknown value on position 325732.
There is also userflags, assuming that is a bit field we have 8 bits used and some seems quite popular.
## Post #11
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-25T19:20:33+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Looking at OCCL again, it's two string references, and four 3d points (4*3 floats) per block.

```
        String 1: 1703128 OccluderHeight01
        String 2: 1703145 Tracks\Monte_Grande\OccluderHeight01.meb
        p1 (c1 => 282.350647, c2 => 52.627357, c3 => 344.877411);
        p2 (c1 => 215.088501, c2 => 52.627357, c3 => 187.407806);
        p3 (c1 => 282.350647, c2 => -49.425030, c3 => 344.877411);
        p4 (c1 => 215.088501, c2 => -49.425030, c3 => 187.407806);
OCCL Block 1 (84)
        String 1: 1703186 OccluderHeight02
        String 2: 1703203 Tracks\Monte_Grande\OccluderHeight02.meb
        p1 (c1 => 147.950470, c2 => 77.145142, c3 => -64.882309);
        p2 (c1 => 339.124634, c2 => 77.145142, c3 => -28.453798);
        p3 (c1 => 147.950470, c2 => -18.870144, c3 => -64.882309);
        p4 (c1 => 339.124634, c2 => -18.870144, c3 => -28.453798);

```
## Post #12
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-27T20:24:27+00:00
- Post Title: Need for Speed: Shift Track SGB Files

So I guess the turn have come for FLAT.

FLAT consists of two structures repeated.

First a 32 byte header block

```
015500  ----    C40DB3D5        -1005734955             -566.809875                             
015516  ----    C10451A1        -1056681567             -8.269929                               
015532  ----    C34052A2        -1019194718             -192.322784                             
//One point (three floats) (max?)
015548  ----    C33D72D1        -1019383087             -189.448502                             
015564  ----    42E818C6        1122506950              116.048386                              
015580  ----    436E1668        1131288168              238.087524                              
//Number of the other kind of blocks following
015596  ----    00000002        2                       0.000000                                
//Unkown
015612  ----    000050A0        20640                   0.000000                        

```


Followed by the previously given number of 64bytes blocks

```
015628  ----    00000000        0                       0.000000                                
015644  ----    00000000        0                       0.000000                                
015660  ----    00000000        0                       0.000000                                
015676  ----    00000000        0                       0.000000                                
//A sphere? center x,z,y, radius (radius seems to match object at same position in SUMM, other coordinates do not)
015692  ----    C3E6127C        -1008332164             -460.144409                             
015708  ----    40BD30B4        1086140596              5.912195                                
015724  ----    C21A1A30        -1038476752             -38.525574                              
015740  ----    43352E9F        1127558815              181.182114                              
//Two points perhaps? Don't know
015756  ----    C40D8D82        -1005744766             -566.211060                             
015772  ----    C0CD099D        -1060304483             -6.407423                               
015788  ----    C34052A2        -1019194718             -192.322784                             
015804  ----    C3B109F3        -1011807757             -354.077728                             
015820  ----    4191DAC1        1100077761              18.231813                               
015836  ----    42E68B14        1122405140              115.271637                              
//Always zero
015852  ----    00000000        0                       0.000000                                
//ID or index, incremented by one for each block (this is the first one).
015868  ----    00000000        0                       0.000000     

```


After this there's a new 32 byte header followed by 64 byte blocks, repeated until end of the FLAT section.
## Post #13
- Username: rafal345
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jun 07, 2010 2:24 am
- Post datetime: 2010-07-28T09:59:38+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Did you try to use 3dsimed?
## Post #14
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-29T06:00:17+00:00
- Post Title: Need for Speed: Shift Track SGB Files

> Reply from rafal345
>
> Did you try to use 3dsimed?
There is nothing in the change log suggesting it have got support for exporting to this format yet.

The unknown value in FLAT is a length, it is sometimes written as the negative number I presume that is to indicate something.
So this could perhaps be the PARTITIONs, question is then why we have a sphere and two coordinates per child object.
Oh well, I guess I'll try to plot it and see what it looks like.
## Post #15
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-29T06:37:34+00:00
- Post Title: Need for Speed: Shift Track SGB Files

Just x,y of the bounding boxes (assuming that is what they are), none of their content and no regard for any grouping.
Seems to be some kind of shape there.
(alpental)
## Post #16
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-07-29T11:26:14+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

Hmm looks a little bit weird.

Could it be something with Lods?

OH for HATTarget and ShadowReceiver - I am not sure if they included this into Shift Versions.

What happens if you Convert all known things of the SGB to SGX and try loading the Track? (Be sure to Rename/Delete the SGB before)
## Post #17
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-29T16:42:38+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

> Reply from Simon
>
> What happens if you Convert all known things of the SGB to SGX and try loading the Track? (Be sure to Rename/Delete the SGB before)
Well, ignoring that I don't have the game and that I'm not running windows, there is too much data in the sgb not in the known sgx structure.
In order to be able to do that we need to learn more about the sgx format.

It is however possible to export to some own xml format for editing and then build a new sgb file based on that.
## Post #18
- Username: rafal345
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jun 07, 2010 2:24 am
- Post datetime: 2010-08-01T15:25:52+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

Can you compare .SGB file of tracks and .BML file of car?
They're using the same subformat - .meb.
## Post #19
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-08-01T15:43:00+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

> Reply from rafal345
>
> Can you compare .SGB file of tracks and .BML file of car?
No, not really.
bml files are the same format as bmt files, which is quite different from the sgb files.
[More about the bml/bmt format.](http://forum.xentax.com/viewtopic.php?f=18&t=4467)

> Reply from rafal345
>
> They're using the same subformat - .meb.
No.
## Post #20
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-08-04T21:08:10+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

> Reply from peppe
>
> It is however possible to export to some own xml format for editing and then build a new sgb file based on that.
I think it is working now.
[http://projects.pappkartong.se/sgbconverter/](http://projects.pappkartong.se/sgbconverter/)
Converting from sgb to sgb, that is, just reading the file into the internal structure and then writing it down again, results in binary equal files.
Converting from sgb to xml and back will result in a files that are not binary equal, probably due to lost precision in all the float values when going float->text->float.
## Post #21
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-08-05T02:00:52+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

Thank you very much testing this after some sleeping
## Post #22
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-08-08T09:41:44+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

> Reply from Simon
>
> Thank you very much testing this after some sleeping
Any success? Problems? Suggestions for improvements?
## Post #23
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-08-09T23:25:50+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

SOrry had no time .. max 1-2 days
## Post #24
- Username: rollobollo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 06, 2011 7:51 am
- Post datetime: 2011-04-06T00:02:07+00:00
- Post Title: Re: Need for Speed: Shift Track SGB Files

Peppe, I tried your sgbconverter with the sgb-track files of Shift2. Unfortunately it wont work anymore (it dies with an exception), maybe the exact file format changed between the 2 game releases . Would you be so kind to try to fix this issue?   

THX
