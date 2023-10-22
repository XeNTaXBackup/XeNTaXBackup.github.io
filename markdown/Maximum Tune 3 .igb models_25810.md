## Post #1
- Username: avwrtn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 16, 2022 10:26 pm
- Post datetime: 2022-09-16T15:47:32+00:00
- Post Title: Maximum Tune 3 .igb models

I've been aware from a long time now that the Alchemy .igb models are considered impossible to access, however in recent years the Project Diva community seem to have learned a thing or two about Alchemy and those games. I want to ask if anybody can help get an understanding for the Maximum Tune 3 arcade games and maybe be able to find a reliable way to export those .igb into modern formats. Before anybody tells me to just look at the HD games, I understand that the HD games in this series have been figured out, but I'm only interested in preservation and documentation of MT3.   

My coding knowledge is very minimal, so I'll say what I do know.
Alchemy from the Project Diva forums can open a small amount of .igb files from MT3 such as courses, leftover test models and some menu 3D elements. However, it cannot open most of those same models from the later MT3DX-3DX+.
It appears all the data needed for the game engines such as, the 3D geometry, textures and materials, are all included in the files.

One interesting thing that could be looked at is the wheel models. For some reason MT3 uses very high polygon wheel models which are only seen in the menus when you would unlock them. I would love to document these and compare the quality to modern games.

Here's the link to the PD forum post about Alchemy: [https://projectdiva.net/community/threa ... dule.1883/](https://projectdiva.net/community/threads/tutorial-how-to-remove-parts-of-module.1883/)
And example models: [https://drive.google.com/file/d/1k636vK ... sp=sharing](https://drive.google.com/file/d/1k636vK-fZpEX-FHpejwF48J-WNK5HPwH/view?usp=sharing)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-16T18:20:28+00:00
- Post Title: Maximum Tune 3 .igb models

> Reply from avwrtn ↑Fri Sep 16, 2022 11:47 pm at Fri Sep 16, 2022 11:47 pm
>
> 
.igb models MT3. the wheel models.
[eigh_high.igb.png](https://xentaxbackup.github.io/file/22825_eigh_high.igb.png)
## Post #3
- Username: avwrtn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 16, 2022 10:26 pm
- Post datetime: 2022-09-16T19:43:42+00:00
- Post Title: Maximum Tune 3 .igb models

I didn't expect that to happen quickly, well done!
Where can I find that app? Is it yours? It almost looks like a Noesis tool.
## Post #4
- Username: avwrtn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 16, 2022 10:26 pm
- Post datetime: 2022-09-20T14:25:34+00:00
- Post Title: Maximum Tune 3 .igb models

> Reply from Durik256 ↑Sat Sep 17, 2022 2:20 am at Sat Sep 17, 2022 2:20 am
>
> 
avwrtn wrote: ↑Fri Sep 16, 2022 11:47 pm
.igb models MT3. the wheel models.

Hey, is there any chance you could share that mesh finder app please? I cannot seem to find it anywhere. No other hex to obj apps has that auto generate face feature. Manually creating thousands of ploygons is going to be a lot of pain.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-20T15:09:56+00:00
- Post Title: Maximum Tune 3 .igb models

> Reply from avwrtn ↑Tue Sep 20, 2022 10:25 pm at Tue Sep 20, 2022 10:25 pm
>
> 
No other hex to obj apps has that auto generate face feature.What are you talking about?  hex2obj was one the first if not the first to have it.
.



wheel-igb.jpg (91.21 KiB) Viewed 89 times
## Post #6
- Username: avwrtn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 16, 2022 10:26 pm
- Post datetime: 2022-09-20T19:16:51+00:00
- Post Title: Maximum Tune 3 .igb models

My mistake, I tried hex2obj but I couldn't find 0.24e so I got the 0.24d exe and didn't realise it's meant to be a full zip. And even then zippyshare is geo-restricted for me like the tutorial says. My bad.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-20T19:43:10+00:00
- Post Title: Maximum Tune 3 .igb models

The files had to be split up to 3 (three) zips, starting from here:

> Reply from shakotay2 ↑Sun Mar 07, 2021 10:29 pm at Sun Mar 07, 2021 10:29 pm
>
> 
(because of 250 kB size restriction of appended files)
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-20T21:46:09+00:00
- Post Title: Maximum Tune 3 .igb models

> Reply from avwrtn ↑Sat Sep 17, 2022 3:43 am at Sat Sep 17, 2022 3:43 am
>
> 
looks like a Noesis tool.
yes its noesis, and yes this my (tool)plugin with noewin. created just for convenience, for yourself.

"autoTriangles" you can do it in noesis:

```
rapi.rpgBindPositionBuffer(bs.readBytes(35100*12), noesis.RPGEODATA_FLOAT, 12)
rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, 35100, noesis.RPGEO_TRIANGLE)

```


or just use python (drop file on this script) it will create an *.obj:

```
import struct

input = sys.argv[1]

with open(input, 'rb') as rb, open(input.replace('.igb', '.obj'), 'w') as wb:
    rb.seek(1761231)
    vert = struct.unpack('%if'%(35100*3), rb.read(35100*12))
    
    for x in range(0, len(vert), 3):
        wb.write('v %f %f %f \n'%vert[x:x+3])
        
    for x in range(1, 35100, 3):
        wb.write('f %i %i %i \n'%(x, x + 1, x + 2))

```

or c++:

```
#include <iostream>

int main(int argc, char* argv[])
{
    if (argc > 1) 
    {
        FILE* rb = fopen(argv[1], "rb");
        FILE* obj = fopen("wheel.obj", "w");
        
        float* vert = new float[35100 * 12];

        fseek(rb, 1761231, 0);
        fread(vert, 4, 35100 * 3, rb);

        for(int i = 0; i < 35100 * 3; i+=3)
            fprintf(obj, "v %f %f %f \n", vert[i], vert[i+1], vert[i+2]);

        for (int i = 1; i < 35100; i += 3)
            fprintf(obj, "f %i %i %i \n", i, i + 1, i + 2);
    
    fclose(rb );
    fclose(obj);
    }
    std::cout << "Done!\n";
}

```

[c++_example.exe](https://drive.google.com/file/d/1rttKL-NXxcJaigKZ_E4uAfeJeRBzL-DD/view?usp=sharing)
or C#:

```

namespace example
{
    internal class Program
    {
        static void Main(string[] args)
        {
            if (args.Length > 0)
            {
                float[] vert = new float[35100 * 12];

                using (var InStream = File.Open(args[0], FileMode.Open))
                {
                    using (var reader = new BinaryReader(InStream))
                    {
                        InStream.Seek(1761231, SeekOrigin.Begin);
                        for (int i = 0; i < 35100 * 12; i++)
                            vert[i] = reader.ReadSingle();
                    }
                }

                using (var OutStream = new StreamWriter(args[0].Replace(".igb", ".obj")))
                {
                    for (int i = 0; i < 35100 * 3; i += 3)
                        OutStream.WriteLine($"v {vert[i]} {vert[i + 1]} {vert[i + 2]}".Replace(',', '.'));

                    for (int i = 1; i < 35100; i += 3)
                        OutStream.WriteLine($"f {i} {i + 1} {i + 2}");
                }
            }
        }
    }
}

```

[c#_example.exe](https://drive.google.com/file/d/1yMtjUJIvPC54C5LmhapDO9FyEm1b0Vy7/view?usp=sharing)



wheel_python_script.png (36.62 KiB) Viewed 70 times


well, or use hex2obj
