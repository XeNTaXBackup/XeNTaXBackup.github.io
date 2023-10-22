## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-02-22T19:15:59+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

Hi.

I`ve recently been looking into the game files of bf3/bf4 and mohwf (frostbite2/3). I have written working texture  converters for them and a semi working mesh(chunk) to obj converter(based on hex2obj by shakotay).

But I want to breakdown the files further.
Ok so the model files are of two parts
1: the .mesh file (header file) and 
2: the .chunk file (payload file).


There still are a few things I don`t quite understand. For instance some of the models have multiple parts in a single mesh. But in game they all are separate models or model parts if you like i.e car body and its wheels are separate models in game, but in game files they are stored as one continuous mesh. Would this info be stored in the .mesh (header) or a .chunk (payload files)?

video [http://www.youtube.com/watch?v=URDXPxyoJvU](http://www.youtube.com/watch?v=URDXPxyoJvU)

And I`m also interested in bone weights and bone structures. The skeleton files are in readable format(txt file) and all the skeletal structure is available but now I need to know where the vertex values are stored so I can tie these together.
Here is a section from a .chunk (payload file)  



so my question is is this how bone weights are typically stored in mesh files? Or do I got it completely wrong and should look elsewhere? 

here are "rat" files [https://dl.dropboxusercontent.com/u/881 ... ch/rat.rar](https://dl.dropboxusercontent.com/u/88155050/BF4/Mesh%20research/rat.rar)
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-02-22T23:31:38+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

weights are stored in files called "bone influences" and bones in one standard bone structure named "skel"---- in BF3 - BF4 - MOHW all this files are inside of chunk files without names , for this is very difficult to find.

but in BFBC - BFBC2 - BF1943 all files have full names and are correctly classified , check the files from this games for find the structure and formats
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-23T08:48:55+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

> Reply from dainazinas
>
> some of the models have multiple parts in a single mesh. But in game they all are separate models or model parts if you like i.e car body and its wheels are separate models in game, but in game files they are stored as one continuous mesh.It's not uncommon for vehicle parts to be controlled by bones via "hard" animations (blend weights =1). I've seen it in games like GTA IV/V, Driver SF and NFS Rivals.

> Reply from dainazinas
>
> so my question is is this how bone weights are typically stored in mesh files? Or do I got it completely wrong and should look elsewhere?I think blend weights are right after bone indices, stored as uint8 and need to be /255 to convert to floats.
Check some vehicle meshes. If the presumed blend weights are always 0xFF you can prove both theories.

Here's my take on the vertex structure. I double-checked normals and tangents in max, there's no doubt about them. So that only leaves one option for blend weights.
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-23T10:43:40+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

Dumping the vertex shader is always helpful when figuring those out

```
{
    ID3DBlob* pBlob = NULL;
    HRESULT hRet = D3DDisassemble( pShaderBytecode, BytecodeLength, 0, "/*========================DUMPED BY D1GITALSLR================================*/ \n", &pBlob );
    char* buffer = (char*)malloc(pBlob->GetBufferSize());
    memcpy(buffer, pBlob->GetBufferPointer(), pBlob->GetBufferSize());
    mFile << buffer;
    mFile << "\r\n\r\n";
    return oCreateVertexShader( This, pShaderBytecode, BytecodeLength, pClassLinkage, ppVertexShader);
}  

```

Credits to d1gitalSLR @unknowncheats
## Post #5
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-02-27T02:49:02+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

> Reply from luxox18
>
> weights are stored in files called "bone influences" and bones in one standard bone structure named "skel"---- in BF3 - BF4 - MOHW all this files are inside of chunk files without names , for this is very difficult to find.

but in BFBC - BFBC2 - BF1943 all files have full names and are correctly classified , check the files from this games for find the structure and formats
Thanks for the info, but those files do not contain per/vertex information.

> Reply from Chipicao
>
> It's not uncommon for vehicle parts to be controlled by bones via "hard" animations (blend weights =1). I've seen it in games like GTA IV/V, Driver SF and NFS Rivals.
This makes a lot of sense, thanks. So here is a model of vehicle from Battlefield 3 (M_FA_18F_D). But vehicle parts don`t seem to have 0xFF weights but instead uses same bone index x4 , strange... . + this model uses 2 sets of UV`s one for normal and second for diffuse.


I wrote a maxscript that selects vertex`es based on bone indice positions in the chunk file, it seems to work quite well
Here`s the files if anyone wants to check them out. [https://dl.dropboxusercontent.com/u/881 ... _18F_D.rar](https://dl.dropboxusercontent.com/u/88155050/BF4/Mesh%20research/M_FA_18F_D.rar)


> Reply from cra0
>
> Dumping the vertex shader is always helpful when figuring those out

Thanks, mind elaborating?
## Post #6
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-27T19:30:45+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

> Reply from dainazinas
>
> vehicle parts don`t seem to have 0xFF weights but instead uses same bone index x4 , strange...
Not strange at all. Since blend weights would always be =1.0 in this model, it makes sense not to include them in order to save space and memory. The game probably detects this in a flag or in the shader.
## Post #7
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-03-03T15:01:46+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

> Reply from Chipicao
>
> dainazinas wrote:vehicle parts don`t seem to have 0xFF weights but instead uses same bone index x4 , strange...
Not strange at all. Since blend weights would always be =1.0 in this model, it makes sense not to include them in order to save space and memory. The game probably detects this in a flag or in the shader.

I`m having trouble finding in (*.mesh/aka_header file) something that would indicate the data structure in the .chunk file. What I do know is where the vertex block size, vertex/faceindice count, string name, for each model + total mesh/submesh count. But no reliable UV`s position. Anyone could shed some light on this?
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-03T16:12:18+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

This would go a bit faster if you'd share the structure you have identified so far.

Am I correct on the following?
[](http://www.imagebam.com/image/68fb4a311749556) 

Send me one or two more meshes that have different VB structures than the rat.
## Post #9
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-03-03T17:01:56+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

> Reply from Chipicao
>
> 
Send me one or two more meshes that have different VB structures than the rat.

Various models and a rat.hbk(in rat.rar)

[https://dl.dropboxusercontent.com/u/881 ... models.rar](https://dl.dropboxusercontent.com/u/88155050/BF4/various_models.rar)
[https://dl.dropboxusercontent.com/u/881 ... F4/Rat.rar](https://dl.dropboxusercontent.com/u/88155050/BF4/Rat.rar)

thanks
## Post #10
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-03-04T19:29:48+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

Chipicao did you get a chance to have a look at the structures? 

I`ve been trying and failing as the offsets I can read are inconsistent.

Please help when you get a chance
## Post #11
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-05T08:18:00+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

Sorry, I didn't have time to analyze them properly.
The only thing you got wrong in your hbk was the IB offset. What you bookmarked as "Mesh.0 Face Indice Count" is actually the offset in indices for the second mesh. It's just a coincidence that it matches the index count of the first mesh because they are both the same.

When I have some free time I will look more into it.
## Post #12
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-03-07T17:25:07+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

> Reply from Chipicao
>
> When I have some free time I will look more into it.

I really hope you can help me with the mesh files. As for  now I managed to get maxscript to import and name the skeletons(I think it does it properly) however it does not deal with hierarchy just yet, and another script that imports the geometry, it needs some manual input, and that`s where reading the .mesh/header files properly would be super useful. 

And thanks for the update Chipicao 

here are the updated scripts, skeleton, geometry and mesh/header files again. [https://dl.dropboxusercontent.com/u/881 ... ch/Rat.rar](https://dl.dropboxusercontent.com/u/88155050/BF3/Mesh%20Research/Rat.rar)
## Post #13
- Username: LALHW
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 10, 2016 8:37 am
- Post datetime: 2016-01-12T21:44:05+00:00
- Post Title: Battlefield 3 & Battlefield 4 mesh files

Sorry for messing with this old thread, but do you still have the texture converters?
