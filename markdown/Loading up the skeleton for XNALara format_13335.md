## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-17T20:48:49+00:00
- Post Title: Loading up the skeleton for XNALara format

Here is an example of a model in XNALara format: [https://drive.google.com/file/d/0B2T9_e ... ZjUzg/edit](https://drive.google.com/file/d/0B2T9_eVRhm4HbmN4TFhNZTZjUzg/edit)

It comes with an ASCII format which is plain-text. It has a binary format as well, and holds basically the same information.

Here's a noesis plugin for it: [https://www.dropbox.com/s/pbermnkst5c07 ... ps.py?dl=0](https://www.dropbox.com/s/pbermnkst5c07la/fmt_XNALara_xps.py?dl=0)

However, I'm not sure how to load the skeleton.
The bones come at the beginning, and we have 

1. The bone parent Index
2. a bone position (x,y,z)
3. The bone index (just the order that they appear in)

Can someone look at the plugin and figure out what I'm doing wrong?
I'm not sure if it's just because I'm assigning the bones to the model after the vertices and faces have been generated.

```
parser = SanaeParser(data)
parser.parse_file(filename)

# Create model and assign some other things to it.
mdl = rapi.rpgConstructModel()
mdl.setBones(parser.boneList)
mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
mdlList.append(mdl)       

```


I start by parsing all of the bones, then I parse the vertices/faces. I then generate the model, and THEN assign the skeleton.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-09-19T03:30:09+00:00
- Post Title: Loading up the skeleton for XNALara format

Didn't test it but I looked at your code and only thing I can nitpick is that XNALara/XPS was written in C# and strings are written with a length that is LEB128 encoded. Longer bone names and/or texture filenames may not load correctly in your code.

[http://jen20.com/2015/02/10/reading-dot ... om-go.html](http://jen20.com/2015/02/10/reading-dot-net-strings-from-go.html)
## Post #3
- Username: finale00
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-09-19T17:25:01+00:00
- Post Title: Loading up the skeleton for XNALara format

It looks like you probably want to be doing 
```
rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
```
 after the rpgCreateContext call.

The problem with the bones is that vec3's toMat43 is assuming the vec3 is a direction, so it derives a rotation about the direction and crosses that rotation vector with the vector itself to produce a full matrix - which has no translation. Hooray for no documentation. A simple enough way to do what you want is: 
```
            boneMat[3] = boneCoords
            bone = NoeBone(boneIndex, boneName, boneMat, None, parentIndex)

```


Also, your normals look busted - I'm not sure why you're using RPGEODATA_UINT for them. RPGEODATA_FLOAT fixes them.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-20T02:59:23+00:00
- Post Title: Loading up the skeleton for XNALara format

Thanks for the feedback. It seems to be working now!

For the string names, I did notice that some formats had an extra 0x01 byte after the length of the string, but before the actual string itself, so that's where the encoding format comes in.

> The interesting part here is the length prefix. LEB128 is an encoding which uses the 7 low bits of a byte to represent the value, and the high bit to represent whether or not the next byte must be considered part of the value or not.

For the bone matrix, I figured the vector represented a translation, but didn't think about how a translation would be represented in a matrix.

Now, the skeleton has been loaded and looks OK, but how can I verify whether the bone indices and weights are applied properly for each vertex?

One issue I've had was loading vertex colors.

```

```


I think that's how the call looks: each vertex 76 bytes, starting at offset 24, 4 bytes per pixel. But noesis just crashes on it.

I don't know how much of a difference vertex colors make to a model though.
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-09-29T06:54:34+00:00
- Post Title: Loading up the skeleton for XNALara format

To verify the weights, you can rotate the bones in the data viewer, or apply a procedural animation with something like

```
		#panims = [NoeProceduralAnim("bone011", 30.0, 1, 0.1), NoeProceduralAnim("bone016", 60.0, 1, 0.1)]
		#anims = rapi.createProceduralAnim(cpr.boneList, panims, 100)
		#mdl.setAnims(anims)
```


That snippet for the colors looks right, although you probably want _UBYTE and not _BYTE. Noesis shouldn't be crashing even if it goes out of bounds, so I must be missing a check somewhere. Feel free to send over a file that's crashing it, since your script+sample model is working fine for me with the color buffer set.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-29T19:17:43+00:00
- Post Title: Loading up the skeleton for XNALara format

Tried rotating the shoulders, and the model's arms tore apart at the shoulders since I used the wrong set of data for the weights 
But this makes it easier to test rather than loading it up manually in a 3D editor! Thanks.

Also, the colors are working for me now (even with signed bytes). Well, it doesn't crash the program at least. I don't really see a difference between colors and no colors though.
