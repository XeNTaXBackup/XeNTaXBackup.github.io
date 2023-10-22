## Post #1
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2023-02-25T09:44:38+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

Hello xentax, I have several thousand PNG's I want to work on rebuilding, they have a JSON file that is a texture atlas in disguise, 
it's contents look like this. 

{"width":499,"imagePath":"lm_tex.png","height":511,"name":"lm","SubTexture":[{"width":137,"y":1,"height":250,"name":"arm_r","x":237},{"frameY":-1,"y":1,"frameWidth":114,"frameX":-1,"frameHeight":394,"width":112,"height":392,"name":"leg","x":1},
and so on and so forth.

all of the Atlas files and images have the same name and are in the same folder, nothing is encrypted or compressed. 

I was wondering if someone could help me by writing a script that could take this atlas file and cut up the PNG into separate PNG's.
I will include a sample.
It wouldn't let me upload a json or txt so I had to rar it. this includes the json and png sample.


 lm_tex.rar
(45.1 KiB) Downloaded 22 times



Any help on this would be very appreciated, other wise i have to do this by hand, and for some of the later PNG's that's impossible.
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2023-02-28T20:11:16+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

Here is a little Python 3.6+ script that do the work you wanted. Please note that you need an Python interpreter and Pillow library installed (pip install pillow). Hope that helps!

```
from json import load as json_load
from pathlib import Path
from sys import argv, exit

def split_image(json_path: Path, dst_path: Path):
    with json_path.open(encoding="utf8") as f:
        description = json_load(f)

    src_filename = description["imagePath"]
    src_name = description["name"]
    
    src_img = Image.open(json_path.parent.joinpath(src_filename))

    for desc in description["SubTexture"]:
        subname = desc["name"]
        x = int(desc["x"])
        y = int(desc["y"])
        w = int(desc["width"])
        h = int(desc["height"])
        # Ignoring framing, gettting raw pixels
        print(f"Saving {w}x{h} part from {src_filename} {x}:{y} as {src_name}.{subname}.png")
        src_img.crop((x, y, x + w, y + h)).save(dst_path.joinpath(f"{src_name}.{subname}.png"))

if __name__ == "__main__":
    if len(argv) not in (2, 3):
        print(f"Usage: {argv[0]} <json file|folder with jsons> [output dir]")
        exit(-1)

    json_path = Path(argv[1])
    dst_path = Path("" if len(argv) == 2 else argv[2])

    if not json_path.exists():
        print(f"Source not exists: {json_path}")
        exit(-1)

    if dst_path.exists() and not dst_path.is_dir():
        print(f"Output directory incorrect: {dst_path}")
        exit(-1)
    dst_path.mkdir(exist_ok=True)

    try:
        if json_path.is_file():
            split_image(json_path, dst_path)
        else:
            for json_file in json_path.glob("*.json"):
                split_image(json_file, dst_path)
    except Exception as e:
        print(f"Got an error {e} when splitting {json_path}")

```
## Post #3
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2023-02-28T20:45:57+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

I don't know why you took the time to do this for me, but thank you so much for your help, I didn't think anyone would reply. 
Thank you again, this project can get back on track because of your help!
I have used python before, I will see if I can figure this out too.
I have Pillow installed form past projects and python, though I can not figure out how to run this script, i tried PowerShell and Python console, but I don't know the command line to enter for this one?
## Post #4
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2023-02-28T22:39:16+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

Just save script as .py file and run in commandline or powershell like this:

```
python script.py example.json
```

Or

```
python script.py folder_with_jsons
```

You can also pass an output directory like this:

```
python script.py json_or_dir output_dir
```


Hope this helps!
## Post #5
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2023-02-28T23:21:37+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

I'm sorry I must be missing something, I've tried every combination I can think of, and I get numerous errors. 
in PowerShell I'm putting in the path to the py and the py, then putting the json and i get this

At line:1 char:128
+ ... \DOWNLOAD\sorted\long skirts\3331\002\LotPcutter.py" 3331002_tex.json
+                                                          ~~~~~~~~~~~~~~~~
Unexpected token '3331002_tex.json' in expression or statement.
    + CategoryInfo          : ParserError: ) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : UnexpectedToken

and if i run that same commad in python i get 

  File "<stdin>", line 1
SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape
## Post #6
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2023-02-28T23:48:23+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

> Reply from aspadm ↑Wed Mar 01, 2023 6:39 am at Wed Mar 01, 2023 6:39 am
>
> 
Just save script as .py file and run in commandline or powershell like this:
Code: Select allpython script.py example.json
Or
Code: Select allpython script.py folder_with_jsons
You can also pass an output directory like this:
Code: Select allpython script.py json_or_dir output_dir

Hope this helps!

It looks like running that same command in CMD just flashes up a window and does nothing. 
below is the command i used by dragging the .py and the .json into CMD

C:\Users\????\Desktop\002\LotPcutter.py C:\Users\????\Desktop\002\3331002_tex.json
## Post #7
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2023-03-01T14:40:02+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

You almost there. All that you need is to insert missing "python":

```
python C:\Users\????\Desktop\002\LotPcutter.py C:\Users\????\Desktop\002\3331002_tex.json
```

At least it must provide readable error.
## Post #8
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2023-03-01T17:21:07+00:00
- Post Title: PNG and Atlas cutter script? Legend of the Phoenix

> Reply from aspadm ↑Wed Mar 01, 2023 10:40 pm at Wed Mar 01, 2023 10:40 pm
>
> 
You almost there. All that you need is to insert missing "python":
Code: Select allpython C:\Users\????\Desktop\002\LotPcutter.py C:\Users\????\Desktop\002\3331002_tex.json
At least it must provide readable error.

Oh my you were absolutely right, thank you, sorry I missed that. this worked like a charm thank you so so much.
