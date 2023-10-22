## Post #1
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-10T00:59:20+00:00
- Post Title: [XBOX] Crimson Sea XKMD

So far I've mainly focused on decryption, but I've started to want to learn how to get meshes for 3D models. So I chose Crimson Sea, a memorable game on XBOX.
I guess the model is stored in Model.pmd and the header is probably XKMD. A cutout of one of them is attached as a sample.

it's XBOX, so I guess use it's big endian.
I tried to get a face in my own way, but I'm groping so I don't know the correct answer. I suspect that startaddr is 0x1f31.
and I guess the start addr of vertices is around 0x4150.

In the mesh of a game that is not this game and the correct answer has already been shown to some extent by other advanced users, I already can get mesh acquisition with Hex2OBJ has been successful. I am motivated to learn, so I would appreciate your cooperation.
[xkmd.zip](https://xentaxbackup.github.io/file/21567_xkmd.zip)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-10T03:28:42+00:00
- Post Title: [XBOX] Crimson Sea XKMD

biggest submesh, bad polygons 

```
0x60 seek
int submesh1 sizeblock 36
int submesh1 count 1418
int submesh1 offset 16692

0x94 seek
int submesh2 sizeblock 40
int submesh2 count 1027
int submesh2 offset 67740

0xC8 seek
int submesh3 sizeblock 48
int submesh3 count 118
int submesh3 offset 108820
	
submesh-1 count:1418/ sizeblock: 36
0x4134(16692) vertices (padding 24)
0x412C(16684) normal (padding 24)
0x411C(16668) uv (padding 28)
0x1089b end

submesh-2 count:1027/ sizeblock: 40
0x1089c(67740) vertices (padding 28)
0x108a8(67752) normal (padding 28)
0x108bc(67772) uv (padding 32)
0x1a913 end

submesh-3 count:118/ sizeblock: 48
0x1a914(108820) vertices (padding 36)
0x1a92b(108843) normal (padding 36)
0x1a93c(108860) uv (padding 40)
0x1bf33 end
```

[xkmd2.png](https://xentaxbackup.github.io/file/21575_xkmd2.png)
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-10T03:39:27+00:00
- Post Title: [XBOX] Crimson Sea XKMD

Thank you, Durik256!
definitely see the character. And I find out that my guess was completely wrong. Above all, this may be a difficult format...

Since Hex2Obj can only see square objects, <-- (*EDIT / sorry, I fault )
I may need to use Advanced Mesh Reaper, which allows more parameters to be specified.
It seems that the file format is too difficult for the first step.

*EDIT
I found out that you are using software called 3D Model Researcher. Now I'm looking at the same screen.
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-10T04:11:33+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Mon Jan 10, 2022 11:39 am at Mon Jan 10, 2022 11:39 am
>
> 
Thank you, Durik256!
I have to go to bed, I'll take another look later 

> Reply from einherjar007 ↑Mon Jan 10, 2022 11:39 am at Mon Jan 10, 2022 11:39 am
>
> 
Hex2Obj
[xkmd.png](https://xentaxbackup.github.io/file/21577_xkmd.png)
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-10T08:41:23+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from Durik256 ↑Mon Jan 10, 2022 12:11 pm at Mon Jan 10, 2022 12:11 pm
>
> 
I have to go to bed, I'll take another look later
Thank you, Durik256! I never rush the results. I myself will be patient with this format. I would be grateful if you could continue to give me advice.
----
I'll summarize my questions from the data I was given, although it's already beyond my control since it used completely different numbers and endianness than I expected. I don't know if anyone will be able to answer them, but that should be the focus of my own future investigations into this format.

1. How did get vertices?
As Hex2Obj researched, I think the theory is usually to get a face and get a vertex count.
In fact, when I experimented with other games (e.g. Revue Starlight), that approach worked.
I don't know how you got the information about vertices, although the game has practically no face yet. Is it because it is a "submesh" and I am not understanding it?

2. Why are the vertices 0x10874 to 0x1a8f7?
Again, I couldn't find any obvious separation in the binary; the Bigchillghost tutorial mentioned that there was a relatively obvious separation, but this model doesn't seem to have it. Is that also due to the fact that it is a submesh? Just to be sure, I checked the binary from beginning to end, and sure enough, I see that the common point 0xFFFFFFFF is off by 4 bytes. Did you discover this by visual inspection?



1028.png (47.75 KiB) Viewed 287 times



3. If it's a submesh, how did discover the relationship between vertices and faces?
I think this is largely due to my lack of knowledge, but for example, if I had gotten vertices first, it is unclear how I would then get faces related to them. Do you do a brute force check on what you see as each face?

4. About UV parameters
I'm completely uninformed about this.
because in Revue Starlight the UV parameters provided by the advanced user were the same for almost all models, and I was able to get roughly the same results with other models without changing them. I will need to learn how to get it myself in the future.
Worst case scenario, if I don't get the UVs right, but I get the mesh, I can set it up myself in the 3D software (although I already have a feeling that if I don't get the UVs right, I won't get the mesh either  ).
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-10T15:36:50+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Mon Jan 10, 2022 8:59 am at Mon Jan 10, 2022 8:59 am
>
> 
it's XBOX, so I guess use it's big endian.
If I remember correctly, Xbox uses little-endian while Xbox360 uses big-endian.  

> Reply from einherjar007 ↑Mon Jan 10, 2022 4:41 pm at Mon Jan 10, 2022 4:41 pm
>
> 
I'll summarize my questions from the data I was given...I don't know if anyone will be able to answer them, but that should be the focus of my own future investigations into this format.
It's rare to see people asking "real" questions nowadays, you've made a good start. Keep that spirit!  


> 1. How did get vertices?
>
> ...Is it because it is a "submesh" and I am not understanding it?
Generally you need to find the vertex indices first to get an easy start. It'll save you from wasting time on the wrong file containing no geometry data. Then just scan through the file (or near by) looking for some "compact" data chunk that appear to be "alignable". It's most possibly to be vertices data. The next step is try to get some point cloud displayed. If there're "physically detached" submeshes, you'll see there're extra face in the model, or worse, it looks like a mess, assuming you get the right indices chunk. The details has been properly covered in my tutorial.

> 2. Why are the vertices 0x10874 to 0x1a8f7?
It's not actually.  
The biggest submesh of the 1st mesh:



mesh1_part1.png (141.43 KiB) Viewed 263 times



> I couldn't find any obvious separation in the binary
You need a good hex editor to make it more "eye catching". Try HexEdit some day.  
But I see that you've noticed the 0xFFFFFFFF marker already.

> 3. If it's a submesh, how did discover the relationship between vertices and faces?
The most effective way, try to find out the exact counts of one submesh, and use these values to locate the submesh info table. The trick has already been covered in my tutorial. Pay attetion to the 2nd paragraph of the following post:
[/viewtopic.php?p=139008#p139008](/viewtopic.php?p=139008#p139008)

> I think this is largely due to my lack of knowledge, but for example, if I had gotten vertices first, it is unclear how I would then get faces related to them. Do you do a brute force check on what you see as each face?
If there're indices chunk both before and after the vertices chunk and you don't know which belongs to which, one possible way is to parse the indices chunk first to get the max index value, and see if it matches with the count of the vertices. If it does, then you'll have more chance to visualize it and validate your guess. Of course there're other tricks but it's meaningless to enumerate all of them.
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-10T15:43:27+00:00
- Post Title: [XBOX] Crimson Sea XKMD

I have not seen the post from Bigchillghost 

> Reply from einherjar007 ↑Mon Jan 10, 2022 11:39 am at Mon Jan 10, 2022 11:39 am
>
> 
Thank you, Durik256!

update

> Reply from Durik256 ↑Mon Jan 10, 2022 11:28 am at Mon Jan 10, 2022 11:28 am
>
> 

```
0x80 int submesh1 triangles_offset: 7904

0xB0 int submesh2 count_triangles: 1739
0xB4 int submesh2 triangles_offset: 12884

0xE4 int submesh2 count_triangles: 164
0xE8 int submesh3 triangles_offset: 16364

0x50 int submesh count

0x60 seek
int submesh1 sizeblock 36
int submesh1 v_count 1418
int submesh1 v_offset 16692

0x94 seek
int submesh2 sizeblock 40
int submesh2 v_count 1027
int submesh2 v_offset 67740

0xC8 seek
int submesh3 sizeblock 48
int submesh3 v_count 118
int submesh3 v_offset 108820

submesh-1 count:1418/ sizeblock: 36
0x4134(16692) vertices (padding 24)
0x412C(16684) normal (padding 24)
0x411C(16668) uv (padding 28)
0x1089b end

submesh-2 count:1027/ sizeblock: 40
0x1089c(67740) vertices (padding 28)
0x108a8(67752) normal (padding 28)
0x108bc(67772) uv (padding 32)
0x1a913 end

submesh-3 count:118/ sizeblock: 48
0x1a914(108820) vertices (padding 36)
0x1a92b(108843) normal (padding 36)
0x1a93c(108860) uv (padding 40)
0x1bf33 end
```
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2022-01-10T16:51:23+00:00
- Post Title: [XBOX] Crimson Sea XKMD

I actually made a web model viewer for this game while I was learning babylon js and typescript. It should be able to load the models with skeleton and skinning. Seems to work fine with your sample.



I have hosted it here so that you can use it: [http://burakakdere.xyz/](http://burakakdere.xyz/) You will probably need a browser with webgl support.
## Post #9
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-11T02:43:16+00:00
- Post Title: [XBOX] Crimson Sea XKMD

Durik256, Bigchillghost, 
Thanks for all the advice! I will continue to research this format carefully. Well, the address I first guessed didn't seem to be perfectly wrong either. At close values, I can see what is clearly in shape.
The hint that there is some information near the header also seems to be of great help to me.

And always thank you, akderebur! It obviously seems to work effectively, except for some enemy models!
At first I thought the XKMD I presented was an OBJ with only a square mesh (because the data I entered gave me a similar shape).
But in reality, it was different, and it clearly included the character. By knowing the correct answer in advance, it seems that more effective trial and error can be performed on the file.
The extracted *.glb does not contain UV, but if I can derive the correct answer with Mesh Ripper, should probably be able to transfer it. Of course, can also create UV from scratch with blender.

When others people try rip for texture. This game works with xemu on the XBOX emulator. Simple capture with RenderDoc does not include too many objects, but continuous capture allows you to capture including the texture of the character model. It's a good idea to get the texture from there.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2022-01-11T05:56:05+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Tue Jan 11, 2022 10:43 am at Tue Jan 11, 2022 10:43 am
>
> 
The extracted *.glb does not contain UV
Hmm yes, I seem to have left this in an unfinished state. I am not planning to return to this format. I will post my script below to help anyone who wants to research the format. It relies heavily on babylon js and isn't a very clean code, but it might give an idea about how to parse the file.

```
import { BinaryReader } from "../helpers/io";
import { MeshX, ModelContainer } from "../model/modelcontainer";
import { MLBase } from "./baseloader";

export class CSLoader extends MLBase {

    private modelOffs: number[] = [];

    public ParseFile(): number {
        this.modelOffs = [];
        var br: BinaryReader = new BinaryReader(this.bData, true);

        while (br.position() < br.size() - 12) {
            let magic = br.readInt32();
            br.readInt32();
            let size = br.readInt32();

            if (magic == 1145916248)
            {
                this.modelOffs.push(br.position() - 12);
                br.seekRel(size - 12);
            }
            else
            {
                br.seek(br.position() - 8);
            }
            
        }

        return this.modelOffs.length;
    }

    public LoadModel(modInd: number): ModelContainer {
        var br: BinaryReader = new BinaryReader(this.bData, true);
        let modOff = this.modelOffs[modInd];
        var modCont: ModelContainer = new ModelContainer();

        //try {

        console.log(modOff);

        br.seek(modOff + 48);
        let boneC = br.readInt32();
        let skelOff = br.readInt32();
        let hierC = br.readInt32();
        let hierOff = br.readInt32();
        br.seekRel(12);
        let triDescOff = br.readInt32();
        let meshC = br.readInt32();
        let triP1C = br.readInt32();
        let triP2C = br.readInt32();

        triP1C += triP2C;

        let mdStart = br.position();

        let hasSkel = boneC > 0;
        modCont.hasSkel = hasSkel;

        let rootTrans: TransformNode = new TransformNode("__root__", this.scene);
        modCont.rootNode = rootTrans;

        // Skeleton
        var skeleton: Skeleton = new Skeleton("skeleton0", "skeleton0", this.scene);
        modCont.skeleton = skeleton;
        var bones: Bone[] = [];
        var tNodes: TransformNode[] = [];
        let parIds: number[] = [];
        let bMats: Matrix[] = [];
        let transMats: Matrix[] = [];

        let locIds: number[] = [];
        let hierIds: number[] = [];

        if (hasSkel) {
            br.seek(modOff + skelOff + 64 * boneC);

            for (let i = 0; i < boneC; i++) {
                br.readInt16();
                parIds.push(br.readInt16());
            }

            for (let i = 0; i < hierC; i++) {
                br.seek(modOff + hierOff + 40 * i);
                let bId = br.readInt16();
                let parId = br.readInt16();
                parIds[bId] = parId;
                hierIds.push(bId);
            }


            br.seek(modOff + skelOff);
            for (let i = 0; i < boneC; i++) {
                let bMat: Matrix = Matrix.FromValues(br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat(), br.readFloat());
                bMat = bMat.invert();
                bMats.push(bMat);
            }

            br.seek(modOff + hierOff);
            for (let i = 0; i < hierC; i++) {
                let bId = br.readInt16();
                locIds.push(bId);
                let parId = br.readInt16();

                let sca = new Vector3(br.readFloat(), br.readFloat(), br.readFloat());
                let rotX = Quaternion.RotationAxis(Vector3.Right(), br.readFloat());
                let rotY = Quaternion.RotationAxis(Vector3.Up(), br.readFloat());
                let rotZ = Quaternion.RotationAxis(Vector3.Forward(), br.readFloat());
                let rot = rotZ.multiply(rotY);
                rot = rot.multiply(rotX);

                let pos = new Vector3(br.readFloat(), br.readFloat(), br.readFloat());

                bMats[bId] = Matrix.Compose(sca, rot, pos);
                parIds[bId] = parId;
            }

            for (let i = 0; i < hierC; i++) {
                var bone: Bone = new Bone("Bone" + i, skeleton);
                var tNode = new TransformNode("Bone" + i, this.scene);

                bones.push(bone);
                tNodes.push(tNode);
            }

            for (let i = 0; i < hierC; i++) {
                var bone = bones[i];
                var tNode = tNodes[i];

                let parBone: Bone = null;
                let parTN: TransformNode = null;

                let targId = locIds[i];
                let parId = parIds[targId];

                if (parId > -1) {
                    parBone = bones[parId];
                    parTN = tNodes[parId];
                }

                if (parBone != null) {
                    bone.setParent(parBone);
                }

                if (parTN != null)
                    tNode.parent = parTN;
                else
                    tNode.parent = rootTrans;

                transMats.push(bone.getAbsoluteTransform());
            }

            for (let i = 0; i < hierC; i++) {
                var bone = bones[i];
                var tNode = tNodes[i];
                let targId = locIds[i];
                let bMat = bMats[targId];

                bone.updateMatrix(bMat);

                tNode.position = bone.position;
                tNode.rotation = bone.rotation;
                tNode.scaling = bone.scaling;

                bone.linkTransformNode(tNode);
            }
        }


        var xMeshes: { [id: number]: MeshX; } = {};
        let strOp = [1, -1, 0];

        let prevC = 0;
        let indCounts = [];
        for (let m = 0; m < meshC; m++) {
            br.seek(mdStart + 52 * m);
            br.readInt32();

            let vbStr = br.readInt32();
            let vertC = br.readInt32();
            let vertOff = br.readInt32();
            br.seekRel(16);
            let indC = br.readInt32();
            let indOff = br.readInt32();


            let meshX: MeshX = new MeshX();
            let vertData: VertData = new VertData();
            let wCount = (vbStr - 36) / 4;
            vertData.wCount = wCount;

            let alLVerts: Vector3[] = [];
            let allNorms: Vector3[] = [];

            let newVerts: Vector3[] = [];


            xMeshes[m] = meshX;

            let vbS = modOff + vertOff;
            for (let i = 0; i < vertC; i++) {
                br.seek(vbS + vbStr * i + 0);
                let x = br.readFloat(), y = br.readFloat(), z = br.readFloat();
                vertData.vertices.push(new Vector3(x, y, z));

                let wSum = 0;
                for (let w = 0; w < wCount; w++) {
                    let wei = br.readFloat();
                    wSum += wei;
                    vertData.weights.push(wei);
                }
                vertData.wSums.push(wSum);
                vertData.weights.push(1.0 - wSum);

                for (let w = 0; w < (4 - wCount - 1); w++) {
                    vertData.weights.push(0);
                }


                vertData.normals.push(new Vector3(br.readFloat(), br.readFloat(), br.readFloat()));
                // meshX.normals.push(br.readFloat());
                // meshX.normals.push(br.readFloat());
                // meshX.normals.push(br.readFloat());
            }

            let allInds: number[] = [];
            br.seek(modOff + indOff);
            for (let i = 0; i < indC; i++) {
                allInds.push(br.readUInt16());
            }
            // for (let i = 0; i < allInds.length - 2; i++) {
            //     meshX.indices.push(allInds[i]);
            //     meshX.indices.push(allInds[i + 1]);
            //     meshX.indices.push(allInds[i + 2]);
            // }

            let exInds: number[] = [];
            let indCur = 0;

            br.seek(modOff + triDescOff);

            let startStr = 1;
            for (let t = 0; t < triP1C; t++) {

                let b0Id = br.readUInt16();
                let weiC = br.readUInt8() / 2 + 1;
                br.seekRel(3);
                let b1Id = br.readUInt16();

                let strBIds = [];
                for (let b = 0; b < 4; b++) {
                    strBIds.push(br.readUInt16());
                }

                let meshId = br.readInt32();
                let entC = br.readInt32();

                for (let e = 0; e < entC; e++) {
                    let triType = br.readInt32();
                    let startVertex = br.readInt32();
                    let triIndC = br.readInt32();
                    let triIndOrg = br.readInt32();
                    let triIndOff = triIndOrg - prevC;
                    let triCount = br.readInt32();


                    //console.log(meshId);


                    if (meshId == m && triIndOff >= 0) {
                        if (triType == 5) {
                            console.log(triIndC + " -- " + startVertex);
                    
                            startStr++;
                            for (let i = 0; i < triIndC; i++) {

                                //meshX.indices.push(indCur++);
                                //newVerts.push(Vector3.TransformCoordinates(alLVerts[allInds[triIndOff + i]], transMats[b0Id]));

                                //meshX.normals.push(allNorms[allInds[triIndOff + i]]);

                                let ind = allInds[triIndOff + i];
                                meshX.indices.push(ind);

                                if (!exInds.includes(ind)) {
                                    exInds.push(ind);
                                    vertData.vertices[ind] = Vector3.TransformCoordinates(vertData.vertices[ind], transMats[b0Id]);
                                    vertData.normals[ind] = Vector3.TransformNormal(vertData.normals[ind], transMats[b0Id]);


                                    let wInd = ind * 4;
                                    if (weiC == 1) {
                                        vertData.weights[wInd] = 1;
                                        vertData.bIds[wInd] = b0Id;

                                        for (let w = 1; w < 4; w++) {
                                            vertData.bIds[wInd + w] = 0;
                                            vertData.weights[wInd + w] = 0;
                                        }
                                    }
                                    else {
                                        let wS = 0;
                                        for (let w = 0; w < weiC; w++) {
                                            vertData.bIds[wInd + w] = parIds[strBIds[w]];
                                            wS += vertData.weights[wInd + w];
                                        }

                                        let ex = 0;
                                        if (wS < 1 && weiC < 4) {
                                            vertData.bIds[wInd + weiC] = b0Id;
                                            vertData.weights[wInd + weiC] = 1.0 - wS;
                                            ex = 1;
                                        }


                                        for (let w = weiC + ex; w < 4; w++) {
                                            vertData.bIds[wInd + w] = 0;
                                            vertData.weights[wInd + w] = 0;
                                        }
                                    }
                                }
                            }
                        }
                        else if (triType == 6) {
                            console.log("str" + " -- " + startVertex);

                            let strInd = startStr;
                            for (let i = 0; i < triIndC - 2; i++) {


                                // meshX.indices.push(allInds[triIndOff + i + 1]);
                                // meshX.indices.push(allInds[triIndOff + i + 2]);

                                // meshX.indices.push(indCur++);
                                // meshX.indices.push(indCur++);
                                // meshX.indices.push(indCur++);


                                // newVerts.push(Vector3.TransformCoordinates(alLVerts[allInds[triIndOff + i]], transMats[b0Id]));
                                // newVerts.push(Vector3.TransformCoordinates(alLVerts[allInds[triIndOff + i + 1]], transMats[b0Id]));
                                // newVerts.push(Vector3.TransformCoordinates(alLVerts[allInds[triIndOff + i + 2]], transMats[b0Id]));
                                for (let s = 0; s < 3; s++) {
                                    let ind = allInds[triIndOff + i + s + strOp[s] * (strInd % 2)];

                                    meshX.indices.push(ind);
                                    if (!exInds.includes(ind)) {

                                        exInds.push(ind);
                                        vertData.vertices[ind] = Vector3.TransformCoordinates(vertData.vertices[ind], transMats[b0Id]);
                                        vertData.normals[ind] = Vector3.TransformNormal(vertData.normals[ind], transMats[b0Id]);

                                        let wInd = ind * 4;
                                        if (weiC == 1) {
                                            vertData.weights[wInd] = 1;
                                            vertData.bIds[wInd] = b0Id;

                                            for (let w = 1; w < 4; w++) {
                                                vertData.bIds[wInd + w] = 0;
                                                vertData.weights[wInd + w] = 0;
                                            }
                                        }
                                        else {
                                            let wS = 0;
                                            for (let w = 0; w < weiC; w++) {
                                                vertData.bIds[wInd + w] = parIds[strBIds[w]];
                                                wS += vertData.weights[wInd + w];
                                            }

                                            let ex = 0;
                                            if (wS < 1 && weiC < 4) {
                                                vertData.bIds[wInd + weiC] = b0Id;
                                                vertData.weights[wInd + weiC] = 1.0 - wS;
                                                ex = 1;
                                            }

                                            for (let w = weiC + ex; w < 4; w++) {
                                                vertData.bIds[wInd + w] = 0;
                                                vertData.weights[wInd + w] = 0;
                                            }
                                        }
                                    }
                                }

                                strInd++;

                                // ind = allInds[triIndOff + i + 1];
                                // meshX.indices.push(ind);
                                // if(!exInds.includes(allInds[triIndOff + i + 1]))
                                // {
                                //     exInds.push(allInds[triIndOff + i + 1]);
                                //     alLVerts[allInds[triIndOff + i + 1]] = Vector3.TransformCoordinates(alLVerts[allInds[triIndOff + i + 1]], transMats[b0Id]);
                                // }

                                // if(!exInds.includes(allInds[triIndOff + i + 2]))
                                // {
                                //     exInds.push(allInds[triIndOff + i + 2]);
                                //     alLVerts[allInds[triIndOff + i + 2]] = Vector3.TransformCoordinates(alLVerts[allInds[triIndOff + i + 2]], transMats[b0Id]);
                                // }
                            }
                        }
                        else
                            console.log(br.position());
                    }
                }
            }

            for (let i = 0; i < vertData.vertices.length; i++) {
                let vert = vertData.vertices[i];
                let norm = vertData.normals[i];


                meshX.vertices.push(vert.x);
                meshX.vertices.push(vert.y);
                meshX.vertices.push(vert.z);

                meshX.normals.push(norm.x);
                meshX.normals.push(norm.y);
                meshX.normals.push(norm.z);
            }

            meshX.bIds = Object.assign([], vertData.bIds);
            meshX.weights = Object.assign([], vertData.weights);

            // for(let vec of alLVerts)
            // {
            //     meshX.vertices.push(vec.x);
            //     meshX.vertices.push(vec.y);
            //     meshX.vertices.push(vec.z);
            // }

            // for(let vec of allNorms)
            // {
            //     meshX.normals.push(vec.x);
            //     meshX.normals.push(vec.y);
            //     meshX.normals.push(vec.z);
            // }

            //prevC += indC;
        }


        let materials: Material[] = [];

        for (let i = 0; i < meshC; i++) {
            let meshX = xMeshes[i];

            let mesh = new Mesh("Mesh" + modInd + "_" + i);

            let vData: VertexData = new VertexData();
            vData.positions = meshX.vertices;
            vData.indices = meshX.indices;
            //vData.calc
            vData.normals = meshX.normals;
            //vData.uvs = meshX.uvs;

            // var normals = [];
            // VertexData.ComputeNormals(meshX.vertices, meshX.indices, normals);
            // vData.normals = normals;


            if (hasSkel) {
                mesh.skeleton = skeleton;
                vData.matricesWeights = meshX.weights;
                vData.matricesIndices = meshX.bIds;
            }

            vData.applyToMesh(mesh);
            //mesh.flipFaces();

            let mat = new PBRMaterial("Material_" + i, this.scene);
            mat.roughness = 1;
            mat.metallic = 0;
            mat.backFaceCulling = false;
            mesh.material = mat;
            materials.push(mat);

            // mesh.subMeshes = [];
            // let curInd: number = 0;
            // let vertC = mesh.getTotalVertices();

            // for (let s = 0; s < meshX.indLens.length; s++) {
            //     new SubMesh(meshX.smMatIds[s], 0, vertC, curInd, meshX.indLens[s], mesh);
            //     curInd += meshX.indLens[s];
            // }

            modCont.meshes.push(mesh);
        }

        modCont.materials = materials;

        // }
        // catch {

        // }

        return modCont;
    }

}

class VertData {
    public vertices: Vector3[] = [];
    public normals: Vector3[] = [];

    public weights: number[] = [];
    public bIds: number[] = [];

    public wCount: number;
    public wSums: number[] = [];

    public strInd = 1;

}
```
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-12T00:34:42+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from akderebur ↑Tue Jan 11, 2022 1:56 pm at Tue Jan 11, 2022 1:56 pm
>
> 
I will post my script below to help anyone who wants to research the format
i have problem with bones  


[fmt_XKMD.zip](https://xentaxbackup.github.io/file/21584_fmt_XKMD.zip)
## Post #12
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-12T01:09:41+00:00
- Post Title: [XBOX] Crimson Sea XKMD

Durik256, Thanks for working on this format further!
It would be great if it were more easily available in scripts.



uvpaint.png (40.6 KiB) Viewed 178 times



By the way, I want to make sure I really want get the sho for the time being, so I stopped working on the format, got the mesh and skeleton using the tools of akderebur, and now I do UV and texture painting. I am.
Since the parts are sci-fi, it was a little difficult to UV, but I have already obtained good results. As for texture paint,
I want to get the result as close to the game as possible, so I synthesize it by the projection method from the top of the development drawing.
It's a time-consuming task, but one day I'll get good results.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-12T12:27:57+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Wed Jan 12, 2022 9:09 am at Wed Jan 12, 2022 9:09 am
>
> 
...so I stopped working on the format
Well, I guess you can learn a lot if you managed to handle this format.  
Though I'm still struggling with the bone mapping but I'll just leave this script here and call it a day for now. 


 fmt_CrimsonSea_xkmd.zip
(2.44 KiB) Downloaded 22 times




Make sure to have the file extension changed to ".xkmd" before using the script.
## Post #14
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-12T12:58:29+00:00
- Post Title: [XBOX] Crimson Sea XKMD

> Reply from Bigchillghost ↑Wed Jan 12, 2022 8:27 pm at Wed Jan 12, 2022 8:27 pm
>
> 
Well, I guess you can learn a lot if you managed to handle this format.
of course! I haven't given up yet. Only Sho is a model that I definitely want to get, so I'm definitely working with blender, but for other models I will get it after investigating the format. Perhaps I plan to get only the mesh and UVs first, without considering the bones and weights.

And thank you for updating the script! As I declared earlier, if someone creates a script or tool, I will continue to investigate this format.
I think learning in a memorable game is the best choice for me.
## Post #15
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-13T10:26:31+00:00
- Post Title: [XBOX] Crimson Sea XKMD

For the time being, I've settled on my own UV work to some extent, so I went back to investigating this format again.
Durik256, Bigchillghost, akderebur, thank you for giving me a lot of information.
I don't have the ability and experience to read data from the binary yet, so I decided to look for the parameters already given in the binary.



tryxkmd.png (94.18 KiB) Viewed 119 times



There are some data tables that Durik256 has investigated, so it should definitely be the correct answer. For face, I arbitrarily associated a close value. That may be a complete mistake.
When I used AXE with these data, I saw something that took shape. It looks dirty because I didn't know the setting of culling, but it looks a little more beautiful if I switch culling. Is this close to the correct answer to some extent? Also, it seems that all the parts exist at the origin 0,0,0. Is there a way to separate these at the time of AXE? (Yes, in blender I should be able to easily disconnect with the L key)
## Post #16
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-13T11:23:17+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

I couldn't add the image in the edit, so please allow me to post more. When I got the next mesh with the data I guess, it seemed wrong. However, it was shaped to some extent, and the UV on the trousers seemed to be correct. It seems that we need a little more wisdom.
[tryxkmd2.png](https://xentaxbackup.github.io/file/21594_tryxkmd2.png)
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-13T11:46:41+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Thu Jan 13, 2022 7:23 pm at Thu Jan 13, 2022 7:23 pm
>
> 
I couldn't add the image in the edit, so please allow me to post more
Which Windows OS are you using? I never expect to see such an old-style UI, not even on WinXP. 

> Reply from einherjar007 ↑Thu Jan 13, 2022 7:23 pm at Thu Jan 13, 2022 7:23 pm
>
> 
It seems that we need a little more wisdom.
The truth is, it's definitely gonna drive you crazy to load all the submeshes manually, let along the vertices need to be transformed to the correct positions with the corresponding bone transformation info. There's a submesh info table at 0x12AC where each entry takes 44 bytes and you'll find the count of the tristrip indices of each submesh (or "fragment" if more accurately) and the begin index id in the indices buffer. You can load correctly the 2nd and the 3rd meshes with AXE if you had that patience, given that their vertices positions are correct in the first place. But there's no point in doing so if you've already understood how it worked.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-13T12:10:04+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

> Reply from Bigchillghost ↑Thu Jan 13, 2022 7:46 pm at Thu Jan 13, 2022 7:46 pm
>
> let along the vertices need to be transformed to the correct positions with the corresponding bone transformation infoThis important sentence should be included into any tutorial "How to rip 3D models from hex data".  
(Took me years to understand the clumped mesh problem.  )
## Post #19
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-15T08:50:42+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

> Reply from Bigchillghost ↑Thu Jan 13, 2022 7:46 pm at Thu Jan 13, 2022 7:46 pm
>
> 
Which Windows OS are you using? I never expect to see such an old-style UI, not even on WinXP.

I don't have very good eyesight, so I prefer a simple view, and I always use the classic view of Windows. The OS is Win7  

> Reply from Bigchillghost ↑Thu Jan 13, 2022 7:46 pm at Thu Jan 13, 2022 7:46 pm
>
> 
The truth is, it's definitely gonna drive you crazy to load all the submeshes manually, let along the vertices need to be transformed to the correct positions with the corresponding bone transformation info. There's a submesh info table at 0x12AC where each entry takes 44 bytes and you'll find the count of the tristrip indices of each submesh (or "fragment" if more accurately) and the begin index id in the indices buffer. You can load correctly the 2nd and the 3rd meshes with AXE if you had that patience, given that their vertices positions are correct in the first place. But there's no point in doing so if you've already understood how it worked.

I have found that simply giving parameters does not give good results. I have been fortunate to have three advanced users who have given me scripts and information that work practically. I don't have enough experience and knowledge to understand it yet, but I will take the time to figure it out.
## Post #20
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-17T06:46:08+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

XBOX's Dynasty Warriros 3 (Sangoku Muso 2) also seemed to use something close to this format.
Looking at the results obtained with AXE and the results of the plugin, it seems that the face specifications are slightly different.
[muso2_xkmd.zip](https://xentaxbackup.github.io/file/21631_muso2_xkmd.zip)
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-17T15:26:28+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

Done:



linkdataUS.png (65.63 KiB) Viewed 100 times
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-17T15:27:42+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

The updated script:


 fmt_CrimsonSea_xkmd.zip
(2.56 KiB) Downloaded 19 times
## Post #23
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-17T17:30:22+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

Bigchillghost, thank you so much!
I would like to take a look at your script and learn what has changed!
## Post #24
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-17T17:42:11+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

I'm sorry, I think this is probably the last question.
Some files have a strange display, probably because the XYZ directions of each data are different.
If the Noesis script swaps this direction, what value should I change?
[wrongaxis_xkmd.zip](https://xentaxbackup.github.io/file/21638_wrongaxis_xkmd.zip)
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-18T12:43:11+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Tue Jan 18, 2022 1:42 am at Tue Jan 18, 2022 1:42 am
>
> probably because the XYZ directions of each data are different.
No it's not that. There're 4 extra bytes before the vertex chunks so the recorded addresses are no longer correct. Sadly there's no obvious way to tell when there'll be a 4-byte difference so this is just an experimental workaround:


 fmt_CrimsonSea_xkmd.zip
(2.63 KiB) Downloaded 14 times
## Post #26
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-18T13:33:35+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

I see, thank you! The object I was seeing looked correct to some extent, and I thought it was in the wrong direction because it was stretched. I'm surprised that even a 4 byte shift will bring about such a result.

Certainly, in the old plug-in state, when I shifted the vertex start point of enemy8 by 4 bytes, it loaded normally.
ex) 5fac to 5fb0, 111d8 to 111dc
I was able to confirm that there was extra data of 00 in the binary.

*EDIT
Bigchillghost, thanks for the hint! There were some other weird models, but the hint that they contained extra data was very helpful. Shifting them will load most of them correctly. And yes, the size of the shift varies from model to model. It doesn't seem to be written somewhere. In the sample, it was a 4-byte shift, but there are models that shift by 8-bytes.

*EDIT2
It's like an adjustment. I think they are trying to align the start position of the vertex data with the position of 0x*0. Now I noticed that I manually corrected all the damaged model data.
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-18T14:55:27+00:00
- Post Title: Re: [XBOX] Crimson Sea XKMD

> Reply from einherjar007 ↑Tue Jan 18, 2022 9:33 pm at Tue Jan 18, 2022 9:33 pm
>
> I think they are trying to align the start position of the vertex data with the position of 0x*0.
The original xkmd sample you uploaded uses addresses that're not aligned by 0x10 byte:



vertAddrs.png (16.42 KiB) Viewed 62 times


So unless this "alignment" is game-specific, there's no elegant solution to be compatible with all files.
