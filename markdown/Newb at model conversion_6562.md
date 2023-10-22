## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-05-06T13:19:34+00:00
- Post Title: Newb at model conversion

I have a model file stored in binary format and am planning to figure out how to get the information required to convert it to a more common format.

I skimmed through it in a hex editor and found some readable parts. It starts off with "objf" and then followed by a couple lines that are named like "material_02" followed by what appears to be a texture name. Ok so I can probably guess that this is the material list lol

Since I can read the material names (maybe), would it be safe to assume that is it not encrypted?

Based on my limited experience with 3D models, I'm guessing other information stored in the rest of the file is vertex, UV, normals, and maybe faces information (although reading around, it seems like some formats don't actually need to store all of the information if they can do some calculations to generate them, which would suck)

What kind of things should I look for that indicate which parts might correspond to what? Like any particular patterns in the hex values.

Any tools that might make the process easier?

I have a couple dozen of these files of varying sizes (from small 2-3 KB files to 1MB+), so I am planning to do cross comparisons as well, but even then I'm not sure what kind of things to look out for.
