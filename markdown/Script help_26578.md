## Post #1
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-16T11:01:20+00:00
- Post Title: Script help

Hello.

Plz. On python for Noesis64
Mesh import plugin

> class MeshInfo:
>
>     # Infomations from 0x0400 Chunk
>
>     def __init__(self, index, name, numOfFaceChunk, parentID, indexOf0x0500Chunk, indexOf0x0600Chunk):
>
>         self.index = index  # Global Index
>
>         self.name = name
>
>         self.numOfFaceChunk = numOfFaceChunk
>
>         self.parentID = parentID
>
>         self.indexOf0x0500Chunk = indexOf0x0500Chunk
>
>         self.indexOf0x0600Chunk = indexOf0x0600Chunk
>
>         self.initialize0x0600ChunkInfo()
>
>         self.boneMap = None
>
> 
>
>     def initialize0x0600ChunkInfo(self):
>
>         self.indexOf0x0800Chunk = []
>
>         self.indexOf0x03000201Chunk = []
>
>         self.faceCount = []
>
>         self.faceIndex = []
>
>         self.texture = []

what is indexOf0x0800Chunk  and indexOf0x03000201Chunk  and why  0x0800 and 0x03000201.
How this work and what is it ? 
Same for indexOf0x0500Chunk  and indexOf0x0600Chunk  why this variables are named like that ? First time i see this.
Maybe something similar on C# ?
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-16T20:09:29+00:00
- Post Title: Script help

> Reply from gambikules ↑Thu Mar 16, 2023 7:01 pm at Thu Mar 16, 2023 7:01 pm
>
> 
what is indexOf0x0800Chunk...

It's just names variable and methods
## Post #3
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-20T23:02:48+00:00
- Post Title: Script help

Yes. Thank you. It's not a problem anymore.
But i have new questions...

What is this  

 linkedBone = linkedBone[:len(weight)]

and 

 linkedBone = [boneMap[x]-1 for x in linkedBone]  

I cant understand this pieces of code. 

I'm trying to find something similar in c++, but  I can't figure out what it does
## Post #4
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T11:28:02+00:00
- Post Title: Script help

Ok.

```
linkedBone = [boneMap[x]-1 for x in linkedBone]  
```
   it is

```
     foreach (int x in linkedBone)
     {
            linkedBone[LB] = boneMap[x] - 1;
             LB++;
     }
```


right ?
but what is linkedBone = linkedBone[:len(weight)]
[:] ok. its a slice.  So from 0 to weight.count  each 1.....lol.  
So we delete info in linkedBone  after len(weight) right ?

 linkedBone.RemoveRange(weight.Count, linkedBone.Count);.
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T12:03:19+00:00
- Post Title: Script help

*(I will write in c# as I am writing from memory from my phone)

> Reply from gambikules ↑Tue Mar 21, 2023 7:02 am at Tue Mar 21, 2023 7:02 am
>
> 
linkedBone = linkedBone[:len(weight)]

len(weight) - this list length weight.Count or (array) weight..Lenght
[:] - this slicing list/array [from which element: to which] - ([1:3] - from 1st to 3rd)
*(in this case, I don’t know what your type WEIGHT is, I will count it as INT)

```
List<int> linkedBone = new List<int> { 4,5,6,7,8 };

linkedBone.RemoveRange(weight.Count, linkedBone.Count - weight.Count);
out: (4,5,6)
```


> Reply from gambikules ↑Tue Mar 21, 2023 7:02 am at Tue Mar 21, 2023 7:02 am
>
> 
linkedBone = [boneMap[x]-1 for x в linkedBone]

```
List<int> boneMap= new List<int> { 5,6,7,8,9 };
for (int i = 0; i < linkedBone.Count; i++)
{
    linkedBone[i] = boneMap[linkedBone[i]] - 1;
}
out: (4,5,6,7,8)
```


EDIT: oh you already figured it out
## Post #6
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T12:40:22+00:00
- Post Title: Script help

linkedBone.RemoveRange(weight.Count, linkedBone.Count);  ==== >   

linkedBone.RemoveRange(weight.Count, linkedBone.Count - weight.Count);

yes thank you . Its a "count" and not "end index" =)

Wat does NoeVertWeight(linkedBone, weight) ?

Any Noesis Documentation ?
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T12:47:13+00:00
- Post Title: Script help

> Reply from gambikules ↑Tue Mar 21, 2023 8:40 pm at Tue Mar 21, 2023 8:40 pm
>
> 
Wat does NoeVertWeight(linkedBone, weight) ?

NoeVertWeight - vertex weight. it binds the vertex to the bone using the weight
a vertex can be affected by multiple bones. eg 1 or 8
contains: (as many vertices)
indices = array INT index bones
weights = array FLOAT weight
*(number of indices and weights should match)

share the original script, why are you doing this?
## Post #8
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T12:53:55+00:00
- Post Title: Script help

> Reply from Durik256 ↑Tue Mar 21, 2023 8:47 pm at Tue Mar 21, 2023 8:47 pm
>
> 
share the original script, why are you doing this?

I try to port noesis Plugin (model loadinging) script to Unity3D. 
I can load models in unity now with textures and materials.
Now i try to adding bonnes and weight to vertex. 

 original script [https://github.com/Team-Alua/GR2-gfx-ex ... _GFX_V2.py](https://github.com/Team-Alua/GR2-gfx-extractor/blob/master/GravityRush2_GFX_V2.py)

ligne 1252
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T13:00:43+00:00
- Post Title: Script help

> Reply from gambikules ↑Tue Mar 21, 2023 8:53 pm at Tue Mar 21, 2023 8:53 pm
>
> 
Unity3D. Now i try to adding bonnes and weight to vertex.
look at this:
[https://docs.unity3d.com/ScriptReferenc ... ights.html](https://docs.unity3d.com/ScriptReference/Mesh-boneWeights.html)

> Reply from gambikules ↑Tue Mar 21, 2023 8:53 pm at Tue Mar 21, 2023 8:53 pm
>
> 
ligne 1252

```
{
    BoneWeight[] weightList = new BoneWeight[vertexCount];
    for (int i = 0; i < vertexCount; i++)
    {
        weightList[i].weight0 = br.readHalfFloat();
        weightList[i].weight1 = br.readHalfFloat();
        weightList[i].weight2 = br.readHalfFloat();
        weightList[i].weight3 = br.readHalfFloat();

        weightList[i].boneIndex0 = boneMap[br.ReadUInt16()] - 1;
        weightList[i].boneIndex1 = boneMap[br.ReadUInt16()] - 1;
        weightList[i].boneIndex2 = boneMap[br.ReadUInt16()] - 1;
        weightList[i].boneIndex3 = boneMap[br.ReadUInt16()] - 1;
    }

    meshs[meshs.Count - 1].boneWeights = weightList;
}

```
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T13:18:42+00:00
- Post Title: Script help

> Reply from gambikules ↑Tue Mar 21, 2023 7:02 am at Tue Mar 21, 2023 7:02 am
>
> 
I'm trying to find something similar in c++
if this is for unity, then why do you need c++?
## Post #11
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T13:44:56+00:00
- Post Title: Script help

You load instantly information in  weights.
Thank you. But i prefer just stock information and assigne this Data at the end. 

but why they do this  
 
```
 linkedBone.RemoveRange(weight.Count, linkedBone.Count - weight.Count);
```

linkedBone count is always = 4  cause   
for (int ii = 0; ii < 4; ii++)
        linkedBone.Add(r.ReadUInt16());
... so this line is useless.

adn why they remove the first index from weight

```
            weight.remove(0)
        except:
            pass
```


or try = just try without execute the code. And if impossible just continue to the next Vertex ?

so if(weight.count == 0)
continue;
## Post #12
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T13:46:07+00:00
- Post Title: Script help

> Reply from Durik256 ↑Tue Mar 21, 2023 9:18 pm at Tue Mar 21, 2023 9:18 pm
>
> 
gambikules wrote: ↑Tue Mar 21, 2023 7:02 am
I'm trying to find something similar in c++

if this is for unity, then why do you need c++?
 I was wrong,  C#
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T14:05:50+00:00
- Post Title: Script help

> Reply from gambikules ↑Tue Mar 21, 2023 9:44 pm at Tue Mar 21, 2023 9:44 pm
>
> 
Thank you. But i prefer just stock information and assigne this Data at the end.
can be shortened

> Reply from gambikules ↑Tue Mar 21, 2023 9:44 pm at Tue Mar 21, 2023 9:44 pm
>
> 
adn why they remove the first index from weight try: weight.remove(0) except: pass[/code]
no, this is an attempt to remove zero. if he is (zero weight)

*(do what you want, i just suggested)
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T14:28:08+00:00
- Post Title: Script help

> Reply from gambikules ↑Tue Mar 21, 2023 9:44 pm at Tue Mar 21, 2023 9:44 pm
>
> 
But i prefer just stock information and assigne this Data at the end.

something like this, I don't think it should be done,  share which model you are load in unity

```
{
    BoneWeight[] weightList = new BoneWeight[vertexCount];
    for (int i = 0; i < vertexCount; i++)
    {
        float[] weight = new float[4];
        int[] linkedBone = new int[4];
        for (int j = 0; j < 4; j++)
            weight[j] = br.readHalfFloat();
        for (int j = 0; j < 4; j++)
            linkedBone[j] = br.ReadUInt16();

        try
        {
            int numIndex = Array.IndexOf(weight, 0);
            weight = weight.Where((val, idx) => idx != numIndex).ToArray();
        }

        linkedBone.RemoveRange(weight.Count, linkedBone.Count - weight.Count);
        if (weight.Lenght != linkedBone.Lenght)
            Console.WriteLine($"Error. NoeVertWeight mismatch. {linkedBone.Lenght}  {weight.Lenght}"); //need Exception

        for (int i = 0; i < linkedBone.Count; i++)
        {
            linkedBone[i] = boneMap[linkedBone[i]] - 1;// Globlize bone Index
        }

        weightList[i].weight0 = weight[0];
        weightList[i].weight1 = weight[1];
        weightList[i].weight2 = weight[2];
        weightList[i].weight3 = weight[3];

        weightList[i].boneIndex0 = linkedBone[0];
        weightList[i].boneIndex1 = linkedBone[1];
        weightList[i].boneIndex2 = linkedBone[2];
        weightList[i].boneIndex3 = linkedBone[3];
    }

    meshs[meshs.Count - 1].boneWeights = weightList;
}
```
## Post #15
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T15:04:44+00:00
- Post Title: Script help

> Reply from Durik256 ↑Tue Mar 21, 2023 10:28 pm at Tue Mar 21, 2023 10:28 pm
>
> 
gambikules wrote: ↑Tue Mar 21, 2023 9:44 pm
But i prefer just stock information and assigne this Data at the end. 


something like this, I don't think it should be done,  share which model you are load in unity
Code: Select allvoid loadMeshWeight(int vertexCount, List<int> boneMap, yourBinaryReader br)
{
    BoneWeight[] weightList = new BoneWeight[vertexCount];
    for (int i = 0; i < vertexCount; i++)
    {
        float[] weight = new float[4];
        int[] linkedBone = new int[4];
        for (int j = 0; j < 4; j++)
            weight[j] = br.readHalfFloat();
        for (int j = 0; j < 4; j++)
            linkedBone[j] = br.ReadUInt16();

        try
        {
            int numIndex = Array.IndexOf(weight, 0);
            weight = weight.Where((val, idx) => idx != numIndex).ToArray();
        }

        linkedBone.RemoveRange(weight.Count, linkedBone.Count - weight.Count);
        if (weight.Lenght != linkedBone.Lenght)
            Console.WriteLine($"Error. NoeVertWeight mismatch. {linkedBone.Lenght}  {weight.Lenght}"); //need Exception

        for (int i = 0; i < linkedBone.Count; i++)
        {
            linkedBone[i] = boneMap[linkedBone[i]] - 1;// Globlize bone Index
        }

        weightList[i].weight0 = weight[0];
        weightList[i].weight1 = weight[1];
        weightList[i].weight2 = weight[2];
        weightList[i].weight3 = weight[3];

        weightList[i].boneIndex0 = linkedBone[0];
        weightList[i].boneIndex1 = linkedBone[1];
        weightList[i].boneIndex2 = linkedBone[2];
        weightList[i].boneIndex3 = linkedBone[3];
    }

    meshs[meshs.Count - 1].boneWeights = weightList;
}

Its done now.  Its not more a problem. But thank you again! Sorry i should say you earlier.


I have  a new question  

```
  if indexList[index].typeID % 0x10000 == 0x0002:
```


what means  % 0x10000 == 0x0002 ?
if(indexList[index].typeID  ????)

for exemple     indexList[index].typeID == 0x02010008:  =  if ( indexList[index].typeID  == 0x02010008)  that is OK
but " % 0x10000 == 0x0002 " what is that ?
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-21T15:19:22+00:00
- Post Title: Re: Script help

> Reply from gambikules ↑
>
>  ↑ if indexList[index].typeID % 0x10000 == 0x0002:
Look modulo division in google

```
if(indexList[index].typeID % 0x10000 == 0x0002)
```
## Post #17
- Username: gambikules
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jun 30, 2021 11:34 pm
- Post datetime: 2023-03-21T15:23:55+00:00
- Post Title: Re: Script help

ok.  For my code it is 

```
if (indexList[i].typeID.Substring(0, 4) == "0200")
```


but i see how its work now.
