## Post #1
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-15T11:53:54+00:00
- Post Title: Loading PBR in noesis Example

Hi,

Iv recently come across a game that uses PBR at part of its texturing pipeline,  and i dont seem to understand how to load it correctly in noesis.
i have looked at UE4 plugin by rich but dont really understand whats going on there   

i was hoping someone can write a very simple/basic LoadRGBA script to showcase how to do this/point me to a simple script that does it or modify sample script:

```
        matList = []
        TextureNames = []
        
        for i in range(len(TextureNames)):
            try:
                g = open(dirpath + TextureNames[i], 'rb')
                data = g.read()
                tex = rapi.loadTexByHandler(data, '.dds')
                tex.name = TextureNames[i][:-4]
                texList.append(tex)
                name = tex.name
                if i == 0:
                    material = NoeMaterial("Material" + Mesh_Name ,name)
                    matList.append(material)
                    material.setTexture(name)
                if i == 1:  
                    material.setNormalTexture(name)
                if i == 2:  
                    material.setSpecularTexture(name)
            except:
                print("texture not found")
                    
        return texList ,matList  
                    

```


i am most interested in loading the PM maps which are PBR, Albedo map seems like normal diffuse (correct?)

Here are the Specs given by Devs:

> ### from  Dev
>
> 
>
>         BM is indeed base colour/albedo
>
>         NM is our normal maps and we move our red channel to the alpha so rather than RGB we have XGBR this is to circumvent some compression details (red tends to get the least of the bytes)
>
>         PM is also indeed 3 combined grey scale maps with an optional alpha
>
> 
>
> 
>
>         R= Metal Mask
>
>         G = Roughness
>
>         B = Ambient Occlusion (actually unused we never got a AO slot in our shader model)
>
>         A= Optional reflectance value used for glass and unusual materials like some of the Eternal stuff
>
> 
>
>         there are also 4 types of masks depending on their use
>
>         MSK1 MSK2 MSK MSKA
>
> 
>
>         the number indicates number of available channels in the masks and considers 3 as a default in the naming
>
> 
>
>         most FX maps are single channel with some occasional exceptions if coloring via the effect tool isn't sufficient
>
> 
>
>         We use Block Compression
>
>         BC1 for RGB
>
>         BC3 for our normal maps and RGBA maps
>
> 
>
>         BC4 for Single channel maps (R)
>
>         BC5 for double channel maps (RB)
>
> 
>
>         GM = Glow map

i am attaching link to samples of maps and model in .obj format 

Thanks in advance for any help   

[https://drive.google.com/open?id=17POrL ... yKEHC9qiqs](https://drive.google.com/open?id=17POrLiE8RBsdTaUte2clo4yKEHC9qiqs)
