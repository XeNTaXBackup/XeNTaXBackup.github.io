## Post #1
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-17T13:07:58+00:00
- Post Title: Need for Speed: Shift Materials

Hi guys

I was playing a little bit with Shift Files and noticed, it is possible to create our own Materials from BMT Material Files in XML Style!!!

I think this is a great breakthrough because we don't need any longer the Materials inside from Shift!! 

Okay I tryed it by hand .. it's too much of Work.

And I have not everything figured out yet. Needs a little bit of Research. It could be possible that there are maybe some Values in the Header but I think not.

Maybe I'll code a Material Editor which Generates XML Files if the interest is big enough.

First Open one BMT File with a Hex Editor of your Choice (I use Hex Workshop the best Hex Editor I know). Then Scroll down to the Bottom:

[](http://www.abload.de/image.php?img=hexzb4e.png)

I marked the Important Area of the File.

And now we need to create a new File (in this case ferrari_599_badges.mtx) with any Text Editor you like:

```
<material name="ferrari_599_badges" shader="render\shaders\vehicles_basic.fx" technique="VehicleBasic_Translucent" fog="false" antialias="1" numparams="3" cull="EBFCT_ANTICLOCKWISE">
<shaderparam name="diffuseTexture" type="EPT_TEXTURE">
        <type t="ET_STANDARD" />
        <value v="Vehicles\Textures\FERRARI_599_BADGING_DIFFUSE.dds" />
		</shaderparam>
<shaderparam name="specularTexture" type="EPT_TEXTURE">
        <type t="ET_STANDARD" />
        <value v="Vehicles\Textures\FERRARI_599_BADGING_SPECULAR.dds" />
    </shaderparam>        
</material>
```


It is not finished only a start of the file and already working in Shift.

What you have to do: 
Write the first 2 Lines into the blank new file and insert the Values.

- material name: your Material Name (file name)
- shader: the shader you want (can be found on 0xbf8H)
- technique: The Technique which will be used. (0xc1cH)
- fog="false" antialias="1" (I'm not sure where to find these)
- numparams: (How many parameters you using, like the same thing for liverys)
- cull: Culling Options (0xc38H)

Now we have the Header done and can Insert the Parameters of the Textures.

First Value:
<shaderparam name="diffuseTexture" type="EPT_TEXTURE">
<type t="ET_STANDARD" />
        <value v="Vehicles\Textures\FERRARI_599_BADGING_DIFFUSE.dds" />
		</shaderparam>

Watch the Top Part of the Picture. You can find all of these Values:
- name Diffuse, Specular, Normalmap ... (0xa50H)
- type The Type no idea what EPT means (0xa60H)
- t="ET_STANDARD" no idea too whats that is (0xa10H)
- v="blablabla" This line points to the Texture you want to use (0xa1cH)

So I think it's that simple. Somewhere are the number Values in the File, don't ask me where. 

Now I add some (complete) MTX Files and BMTs too. Maybe you can help me Researching these. Sadly I don't have any MTX and BMT which is the same file...

Can you clever guys please please help me with creating a BMT to MTX (=XML) Converter?
[sample.rar](https://xentaxbackup.github.io/file/3047_sample.rar)
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-17T14:33:48+00:00
- Post Title: Need for Speed: Shift Materials

Thanks goes to Quadcoremax 

He told be that there are BMT Files and the Decrypted MTX Files too. Should be easier to create a converter with them?!

I attached them:

[http://ul.to/2lge24](http://ul.to/2lge24)
## Post #3
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-19T10:21:52+00:00
- Post Title: Need for Speed: Shift Materials

Can't anyone help me please?

This is really Important for me.

I'm trying to get this for 3 Days now without any success.

I am able to write most parts of the XML (Opening in Hex Editor and writing XML manually) but I have no idea where I could find the Number Values and I don't know if all Tags which will be used in the Sample Files are present (maybe Encrypted or with a Code Number like F3 = <shaderparam> or whatever) and I don't know exactly which Tag is the right for each Value. 


Looking forward to help, maybe with a QuickBMS Script?!
## Post #4
- Username: bigBear
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Oct 09, 2009 2:51 am
- Post datetime: 2010-05-20T16:11:36+00:00
- Post Title: Need for Speed: Shift Materials

You want to export it to other games?
Zmodeler2 already have NFS Shift exporter.

But the idea of Material editor wich generates in XML is a nice idea.
But how about the game?
Maybe it doesnt recognize them?
## Post #5
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-20T16:21:24+00:00
- Post Title: Need for Speed: Shift Materials

I want new Cars for Need for Speed: Shift  The Game is able to read XML-Based Materials too.

I know the zModeler 2 can Export this Materials as XML too but it's worthless because I don't have the Full Version so I can't Import the Cars to get the Materials. (Export is working with the free Version)

And maybe it's possible to Decrypt other Files (BML, Binary XML too) as well because they look exactly the same 

Oh and it should be able to read Big Endian Files too because X360 Materials.
## Post #6
- Username: jhonsadins
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 02, 2010 9:09 pm
- Post datetime: 2010-07-03T07:59:31+00:00
- Post Title: Need for Speed: Shift Materials

I would like to say something about the game is And even though the 2010 E3 Expo passed by without any news on a new Need for Speed from the British developer, a hot rumor started circulating the net yesterday, getting people excited about Need for Speed Shift 2.
## Post #7
- Username: peppe
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jul 09, 2010 1:21 pm
- Post datetime: 2010-07-10T17:32:11+00:00
- Post Title: Need for Speed: Shift Materials

Someone asked about this in an IRC channel a while back, so I have been playing a bit with it when I've been bored.
As of two days ago I have figured out enough to generate xml, though I still have no idea what the COLL block is.
[http://projects.pappkartong.se/bmt2xml/](http://projects.pappkartong.se/bmt2xml/)

The tag and attribute names must be known, so there might be tag and attribute names I haven't seen and don't handle.
I haven't seen any big endian versions of the files so I don't handle them.
