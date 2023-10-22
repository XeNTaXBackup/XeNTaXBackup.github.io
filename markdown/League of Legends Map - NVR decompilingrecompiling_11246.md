## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-23T16:41:24+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

Hey Guys,

I'm very new here and I have a question.
At the moment, I'll try to find a way to decompile and recompile an nvr-file.

I found this about the structure of a nvr-file, but I don't know If Riot changed this already.
[http://pastebin.com/my2bPpHa](http://pastebin.com/my2bPpHa)

I think I found a decompiler for this fileformat, but It won't work for me (It'll crash).
[http://pastebin.com/V2iJXPgJ](http://pastebin.com/V2iJXPgJ) (C++ Source Code)


It would be great if you could help me with this.


I uploaded one of the maps onto my server:
[http://chrisx930.de/lol/scene.rar](http://chrisx930.de/lol/scene.rar)
not available? Use this link
[http://uploaded.net/file/oi0das4w](http://uploaded.net/file/oi0das4w)


Thank you for help
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-02-25T04:15:28+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

[out]
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-25T06:25:45+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

> Reply from Wobble
>
> 
Link doesn't work.  Put it up somewhere else on reliable file sharing server.

Ul.to Link added
[http://uploaded.net/file/oi0das4w](http://uploaded.net/file/oi0das4w)
## Post #4
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-25T19:30:17+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

Update: 
Today I got an old League of Legends Client with older Map-Files.
I can run the decompiler without any crash, but it will stuck after converting the files to .x-files.
[](http://abload.de/img/decompmapkkud8.png)
The decompiler won't save the files to disk and I don't know why.
It would be great if you can check this out.
It would be nice if anyone can try to decompile the new map-file where my decompiler crashs.


Old Map Files (decompiler included): 
[http://uploaded.net/file/za27r2cx](http://uploaded.net/file/za27r2cx)


Thank you
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-02-26T01:24:49+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

[out]
## Post #6
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-26T09:42:02+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

Thank you 

I tried it out but it won't work at all :/
Do you have any ideas how can i fix the problem?
I can't get the code to work-.-

Any ideas for the new nvr-file-format?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-26T13:04:27+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

There is at least one other vertex list type with the size of 40 bytes at 0x145BB0
in the room.nvr
140200 (list size) / 40= 3505
 4777.406738 -38.057873 3405.364502  
 normals 0.692772 0.045192 -0.719740
 uv 0.016999 0.730632  
 unknown DWORDs 2F 2E 2C FF  7F 7F 7F FF
## Post #8
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-26T13:41:32+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

> Reply from shakotay2
>
> There is at least one other vertex list type with the size of 40 bytes at 0x145BB0
in the room.nvr
140200 (list size) / 40= 3505
 4777.406738 -38.057873 3405.364502  
 normals 0.692772 0.045192 -0.719740
 uv 0.016999 0.730632  
 unknown DWORDs 2F 2E 2C FF  7F 7F 7F FF

Could you fix it in my source code for me?
It would be REALLY great!
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-26T14:22:18+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

works for your uploaded room.nvr only I guess.

(There's a better solution required to determine what's of vertex list type 2
than checking for 0xFF7F7F7F or 0xFF16191E.)

```
    public:
            int size;
 >>>        int type;
            nvr_vertex *vertices;
    };


            //get vertex list

            int temp_values[4];		// 3-> 4
		...
>>>		_ReadNext(NULL, 12, true); _ReadNext(buffer_1, 4);
>>>		temp_values[3] = _MemToInt(buffer_1);
>>>             _ReadNext(NULL, -40, true);


            if (temp_size/36*36 == temp_size && temp_values[0] <= 1 && temp_values[1] <= 1 && temp_values[2] <= 1) {
                            nvr_struct.vertex_lists[i].size = temp_size/36;
                            nvr_struct.vertex_lists[i].type = 1;
		    }
		    else
>>>			if ((temp_values[3]==0xFF7F7F7F)||(temp_values[3]==0xFF16191E)) {
>>>                         nvr_struct.vertex_lists[i].size = temp_size/40;
>>>                         nvr_struct.vertex_lists[i].type = 2;
			} 
    			else {
                                nvr_struct.vertex_lists[i].size = temp_size/12;
                                nvr_struct.vertex_lists[i].type = 0;
	    		}





>>>		if (nvr_struct.vertex_lists[i].type >0) {
		        for (int j=0; j < nvr_struct.vertex_lists[i].size; j++) {
                                ...
				...

>>>				if (nvr_struct.vertex_lists[i].type ==2) _ReadNext(buffer_1, 4);                                    
               }
                cout << "Finished }\n";
     
        } else {

```


"beautfying"

```
            while(1); 
    }
     
    void _ReadNext(char *buffer, int bytes, bool seek)  {..
```


```
 ss << nvr_struct.materials[nvr_struct.models[i].material].name << ...

```


>>> marks additional/changed lines

this is the result:

```

     size:  32827   type: 1      vertices_0 [32827]     
     size:  3505   type: 2      vertices_1 [3505]     
     size:  16322   type: 2      vertices_2 [16322]     
     size:  9025   type: 2      vertices_3 [9025]     
     size:  30344   type: 2      vertices_4 [30344]     
     size:  27090   type: 1      vertices_5 [27090]     
     size:  470   type: 1      vertices_6 [470]     
     size:  16018   type: 2      vertices_7 [16018]     
     size:  1361   type: 2      vertices_8 [1361]     
     size:  2103   type: 2      vertices_9 [2103]     
     size:  854   type: 2      vertices_10 [854]     
     size:  1812   type: 2      vertices_11 [1812]     
     size:  7059   type: 2      vertices_12 [7059]     
     size:  395   type: 2      vertices_13 [395]     
     size:  12943   type: 2      vertices_14 [12943]     
     size:  2712   type: 2      vertices_15 [2712]     
     size:  1052   type: 2      vertices_16 [1052]     
     size:  1517   type: 2      vertices_17 [1517]     
     size:  23772   type: 2      vertices_18 [23772]     
     size:  7858   type: 2      vertices_19 [7858]     
     size:  454   type: 2      vertices_20 [454]     
     size:  1203   type: 2      vertices_21 [1203]     
     size:  875   type: 2      vertices_22 [875]     
     size:  26299   type: 2      vertices_23 [26299]     
     size:  11209   type: 2      vertices_24 [11209]     
     size:  240   type: 1      vertices_25 [240]     
     size:  2676   type: 2      vertices_26 [2676]     
     size:  2490   type: 2      vertices_27 [2490]     
     size:  88   type: 2      vertices_28 [88]     
     size:  2887   type: 2      vertices_29 [2887]     
     size:  7107   type: 2      vertices_30 [7107]     
     size:  1264   type: 2      vertices_31 [1264]     
     size:  58398   type: 2      vertices_32 [58398]     
     size:  13155   type: 2      vertices_33 [13155]     
     size:  3656   type: 2      vertices_34 [3656]     
     size:  352   type: 2      vertices_35 [352]     
     size:  658   type: 2      vertices_36 [658]     
     size:  1724   type: 2      vertices_37 [1724]     
     size:  20770   type: 1      vertices_38 [20770]     
     size:  548   type: 2      vertices_39 [548]     
     size:  1289   type: 2      vertices_40 [1289]     
     size:  10686   type: 2      vertices_41 [10686]     
     size:  789   type: 2      vertices_42 [789]     
     size:  96   type: 2      vertices_43 [96]     
     size:  400   type: 2      vertices_44 [400]     
     size:  3500   type: 1      vertices_45 [3500]     
     size:  75   type: 2      vertices_46 [75]     
     size:  3256   type: 2      vertices_47 [3256]     
     size:  307   type: 2      vertices_48 [307]     
     size:  6911   type: 2      vertices_49 [6911]     
     size:  3731   type: 2      vertices_50 [3731]     
     size:  74   type: 2      vertices_51 [74]     
     size:  48866   type: 0      vertices_52 [48866]     
     size:  57928   type: 0      vertices_53 [57928]     
     size:  64378   type: 0      vertices_54 [64378]     
     size:  64891   type: 0      vertices_55 [64891]     
     size:  63102   type: 0      vertices_56 [63102]     
     size:  59322   type: 0      vertices_57 [59322]     
     size:  22512   type: 0      vertices_58 [22512]     
  }

  index_lists[59] {

     size:  45129    d3dformat: 101      indices_0 [45129]        
     size:  7263    d3dformat: 101      indices_1 [7263]        
     size:  26307    d3dformat: 101      indices_2 [26307]        
     size:  15549    d3dformat: 101      indices_3 [15549]        
     size:  50979    d3dformat: 101      indices_4 [50979]        
     size:  50979    d3dformat: 101      indices_5 [50979]        
     size:  1623    d3dformat: 101      indices_6 [1623]        
     size:  26820    d3dformat: 101      indices_7 [26820]        
     size:  3612    d3dformat: 101      indices_8 [3612]        
     size:  2997    d3dformat: 101      indices_9 [2997]        
     size:  2271    d3dformat: 101      indices_10 [2271]        
     size:  5463    d3dformat: 101      indices_11 [5463]        
     size:  11220    d3dformat: 101      indices_12 [11220]        
     size:  882    d3dformat: 101      indices_13 [882]        
     size:  23373    d3dformat: 101      indices_14 [23373]        
     size:  5472    d3dformat: 101      indices_15 [5472]        
     size:  1470    d3dformat: 101      indices_16 [1470]        
     size:  2481    d3dformat: 101      indices_17 [2481]        
     size:  35508    d3dformat: 101      indices_18 [35508]        
     size:  20100    d3dformat: 101      indices_19 [20100]        
     size:  1968    d3dformat: 101      indices_20 [1968]        
     size:  2670    d3dformat: 101      indices_21 [2670]        
     size:  3129    d3dformat: 101      indices_22 [3129]        
     size:  46080    d3dformat: 101      indices_23 [46080]        
     size:  20673    d3dformat: 101      indices_24 [20673]        
     size:  360    d3dformat: 101      indices_25 [360]        
     size:  12438    d3dformat: 101      indices_26 [12438]        
     size:  6354    d3dformat: 101      indices_27 [6354]        
     size:  174    d3dformat: 101      indices_28 [174]        
     size:  8967    d3dformat: 101      indices_29 [8967]        
     size:  11253    d3dformat: 101      indices_30 [11253]        
     size:  1776    d3dformat: 101      indices_31 [1776]        
     size:  104925    d3dformat: 101      indices_32 [104925]
     size:  23841    d3dformat: 101      indices_33 [23841]        
     size:  5376    d3dformat: 101      indices_34 [5376]        
     size:  1170    d3dformat: 101      indices_35 [1170]        
     size:  2550    d3dformat: 101      indices_36 [2550]        
     size:  3048    d3dformat: 101      indices_37 [3048]        
     size:  24894    d3dformat: 101      indices_38 [24894]        
     size:  2226    d3dformat: 101      indices_39 [2226]        
     size:  2640    d3dformat: 101      indices_40 [2640]        
     size:  22119    d3dformat: 101      indices_41 [22119]        
     size:  1491    d3dformat: 101      indices_42 [1491]        
     size:  324    d3dformat: 101      indices_43 [324]        
     size:  600    d3dformat: 101      indices_44 [600]        
     size:  5541    d3dformat: 101      indices_45 [5541]        
     size:  105    d3dformat: 101      indices_46 [105]        
     size:  7803    d3dformat: 101      indices_47 [7803]        
     size:  690    d3dformat: 101      indices_48 [690]        
     size:  16185    d3dformat: 101      indices_49 [16185]        
     size:  8007    d3dformat: 101      indices_50 [8007]        
     size:  153    d3dformat: 101      indices_51 [153]        
     size:  93903    d3dformat: 101      indices_52 [93903]        
     size:  100977    d3dformat: 101      indices_53 [100977]        
     size:  115521    d3dformat: 101      indices_54 [115521]        
     size:  118347    d3dformat: 101      indices_55 [118347]        
     size:  123519    d3dformat: 101      indices_56 [123519]        
     size:  105723    d3dformat: 101      indices_57 [105723]        
     size:  31038    d3dformat: 101      indices_58 [31038]        
}
```
## Post #10
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-26T15:02:36+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

Thank yoU! 

But while compiling, I'll get this error and don't know why. ~_~

> Code: Select allFehler	12	error C4789: Der Puffer 'temp_values' mit der Größe von 12 Bytes wird überlaufen; 4 Bytes werden ab Offset 12 geschrieben.	c:\users\chrisx930\documents\visual studio 2012\projects\nvr-converter\nvr-converter\nvr-converter.cpp	203	1	NVR-Converter

Could you send me the whole code pls? 
I don't know where I failed xD
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-26T15:39:03+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

upps, sry:         int temp_values[4];		// 3-> 4
## Post #12
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-26T16:05:56+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

Tried it out, now I can compile it without errors, but It'll stuck again at 715/716.
Could you upload your VSC++-Project vor me?

btw. Any Ideas for the new file format of League of legends "nvr"?
I don't know if it possible to "run" a old map with the old file-format ingame.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-26T16:44:31+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

guess, that won't change anything. There's two x-files missing for the old version room.nvr (7413320 bytes) for me. (Also got last line 715/716 because the index i counts from 0, so doesn't reach max index.)

For the new format only tested with the uploaded room.nvr, file size: 23602376 bytes.

For other nvrs the line for detecting vertex list type 2
if ((temp_values[3]==0xFF7F7F7F)||(temp_values[3]==0xFF16191E))
probably has to be changed.

```

    #include <iostream>
    #include <fstream>
    #include <string>
    #include <sstream>
    #include <windows.h>
    #include <bitset>
    #include <math.h>
    #include <float.h>
    #include <iomanip>
     
    using namespace std;
     
    class nvr_vertex {
    public:
            float position[3];
            float normals[3];
            float uv[2];
            int unknown;
    };
     
    class nvr_material_struct_class {
    public:
            string name;
            float emissive_color[3];
            float blend_color[4];
            string texture_filename;
            float opacity;
            string blend_filename;
            int used;
    };
     
    class nvr_vertexlist_struct_class {
    public:
            int size;
            int type;
            nvr_vertex *vertices;
    };
     
    class nvr_indexlist_struct_class {
    public:
            int size;
            unsigned int d3dfmt;
            unsigned short *indices;
    };
     
    class nvr_model_model_struct_class {
    public:
            int vertex_index;
            int vertex_offset;
            int vertex_length;
            int index_index;
            int index_offset;
            int index_length;
    };
     
    class nvr_model_struct_class {
    public:
            int flag_1;
            int flag_2;
            float b[10];
            int material;
            nvr_model_model_struct_class model[2];
    };
     
    class nvr_unknown3_struct_class {
    public:
            float a[6];
            int b[4];
    };
     
    class nvr_struct_class {
    public:
            string magic;
            unsigned short unknown_1;
            unsigned short unknown_2;
            unsigned int count_material;
            unsigned int count_vertex_list;
            unsigned int count_index_list;
            unsigned int count_model;
            unsigned int count_unknown_3;
     
            nvr_material_struct_class * materials;
            nvr_vertexlist_struct_class * vertex_lists;
            nvr_indexlist_struct_class * index_lists;
            nvr_model_struct_class * models;
            nvr_unknown3_struct_class * unknown_3;
     
    };
     
    nvr_struct_class nvr_struct;
    char * nvr_data;
     
    void _ReadNext(char *buffer, int bytes, bool seek = false);
    string _MemToString(char *buffer);
    unsigned short _MemToShort(char *buffer);
    unsigned int _MemToInt(char *buffer);
    float _MemToFloat(char *buffer);
    float _MemToFloat2(char *buffer);
     
    string _XFileHead();
     
    string _NvrHeadToString(nvr_struct_class &nvr);
    string _NvrMaterialToString(nvr_material_struct_class material);
    string _NvrVertexToString(nvr_vertex vertex);
    string _NvrVertexToString2(nvr_vertex vertex);
    string _NvrModelToString(nvr_model_struct_class model);
     
    float round(float r, int places);
     
     
    int main () {
            HANDLE hConsole = GetStdHandle(STD_OUTPUT_HANDLE);
            //SMALL_RECT windowSize = {0, 0, 150, 100};
            //SetConsoleWindowInfo(hConsole, TRUE, &windowSize);
     
            cout << "\nNVR Converter        Version 1.0\n\nA room.nvr file has to be located next to this exe. \nExtracted files can be found in the output folder. \nMatching texture files are located in \"[MapPath]\\Schens\\Textures\"\nThe default texture path is \"teture\\[name].dds\", relative to the programm loading it. \nNo customization of these parameter currently possible.\n\n\n\n";
     
            cout << "Press ENTER to continue...";
            cin.ignore();
     
     
            cout << "Loading file into memory... ";
            ifstream nvr_file;
            nvr_file.open ("room.nvr", ios::binary | ios::in | ios::ate);
            int size = nvr_file.tellg();
				if (size==-1) { cout << "error loading file\n\n"; return 0 ; }
            nvr_data = new char [size];
            nvr_file.seekg (0, ios::beg);
            nvr_file.read (nvr_data, size);
            nvr_file.close();
            cout << "Finished\n\n";
           
            cout << "Resolving file structure: \n\n";
     
            char buffer_1[4], buffer_2[2], buffer_3[256], buffer_4[336], buffer_5[2364];
     
            //get head data
            _ReadNext(buffer_1, 4);
            nvr_struct.magic = _MemToString(buffer_1);                      //magic number (4 byte char array)
            _ReadNext(buffer_2, 2);
            nvr_struct.unknown_1 = _MemToShort(buffer_2);           //unknown value (2 byte short)
            _ReadNext(buffer_2, 2);
            nvr_struct.unknown_2 = _MemToShort(buffer_2);           //unknown value (2 byte short)
            _ReadNext(buffer_1, 4);
            nvr_struct.count_material = _MemToInt(buffer_1);        //material count (4 byte int)
            _ReadNext(buffer_1, 4);
            nvr_struct.count_vertex_list = _MemToInt(buffer_1);     //vertex list count (4 byte int)
            _ReadNext(buffer_1, 4);
            nvr_struct.count_index_list = _MemToInt(buffer_1);      //index list count (4 byte int)
            _ReadNext(buffer_1, 4);
            nvr_struct.count_model = _MemToInt(buffer_1);           //model count (4 byte int)
            _ReadNext(buffer_1, 4);
            nvr_struct.count_unknown_3 = _MemToInt(buffer_1);       //unknown3 count (4 byte int)
            //display result
            cout << _NvrHeadToString(nvr_struct);
     
     
            //get material data
            cout << "  materials [" << nvr_struct.count_material << "]      { Processing... ";
            nvr_struct.materials = new nvr_material_struct_class[nvr_struct.count_material];
            for (int i = 0; i < nvr_struct.count_material; i++) {
                    _ReadNext(buffer_3, 256);
                    nvr_struct.materials[i].name = _MemToString(buffer_3);                          //name (256 byte char array)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].emissive_color[0] = _MemToFloat(buffer_1);      //emissive color Red (4 byte float)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].emissive_color[1] = _MemToFloat(buffer_1);      //emissive color Green (4 byte float)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].emissive_color[2] = _MemToFloat(buffer_1);      //emissive color Blue (4 byte float)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].blend_color[0] = _MemToFloat(buffer_1);         //blend color Alpha (4 byte float)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].blend_color[1] = _MemToFloat(buffer_1);         //blend color Red (4 byte float)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].blend_color[2] = _MemToFloat(buffer_1);         //blend color Green (4 byte float)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].blend_color[3] = _MemToFloat(buffer_1);         //blend color Blue (4 byte float)
                    _ReadNext(buffer_4, 336);
                    nvr_struct.materials[i].texture_filename = _MemToString(buffer_4);      //texture file name (336 byte char array)
                    _ReadNext(buffer_1, 4);
                    nvr_struct.materials[i].opacity = _MemToFloat(buffer_1);                        //opacity (4 byte float)
                    _ReadNext(buffer_5, 2364);
                    nvr_struct.materials[i].blend_filename = _MemToString(buffer_5);        //blend file name (2364 byte char array)
                    nvr_struct.materials[i].used = 0;                                                                       //used 0 times (reset)
            }
            cout << "Finished }\n\n";
     
     
            //get vertex list
            cout << "  vertex_lists [" << nvr_struct.count_vertex_list << "] {\n\n";
            nvr_struct.vertex_lists = new nvr_vertexlist_struct_class[nvr_struct.count_vertex_list];
     
            for (int i=0; i < nvr_struct.count_vertex_list; i++) {
                    _ReadNext(buffer_1, 4);
                    int temp_size = _MemToInt(buffer_1);    //size of current vertex list
                    int temp_values[4];
     
     
                    _ReadNext(NULL, 12, true);
                    _ReadNext(buffer_1, 4);
                    temp_values[0] = _MemToFloat(buffer_1);
                    _ReadNext(buffer_1, 4);
                    temp_values[1] = _MemToFloat(buffer_1);
                    _ReadNext(buffer_1, 4);
                    temp_values[2] = _MemToFloat(buffer_1);

					_ReadNext(NULL, 12, true); _ReadNext(buffer_1, 4);
					temp_values[3] = _MemToInt(buffer_1);
                    _ReadNext(NULL, -40, true);
     
                    if (temp_size/36*36 == temp_size && temp_values[0] <= 1 && temp_values[1] <= 1 && temp_values[2] <= 1) {
                            nvr_struct.vertex_lists[i].size = temp_size/36;
                            nvr_struct.vertex_lists[i].type = 1;
                    } else 
						if ((temp_values[3]==0xFF7F7F7F)||(temp_values[3]==0xFF16191E)) {
                            nvr_struct.vertex_lists[i].size = temp_size/40;
                            nvr_struct.vertex_lists[i].type = 2;
						} 
						else {
                            nvr_struct.vertex_lists[i].size = temp_size/12;
                            nvr_struct.vertex_lists[i].type = 0;
                    }
     
     
                    cout << "     size:  " << nvr_struct.vertex_lists[i].size
                             << "   type: " << nvr_struct.vertex_lists[i].type
                             << "      vertices_"<<i<<" ["<<nvr_struct.vertex_lists[i].size<<"]     { Processing... ";
     
                    nvr_struct.vertex_lists[i].vertices = new nvr_vertex[nvr_struct.vertex_lists[i].size];
                   
                    if (nvr_struct.vertex_lists[i].type > 0) {
     
                            for (int j=0; j < nvr_struct.vertex_lists[i].size; j++) {
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].position[0] = _MemToFloat(buffer_1);             //x position of current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].position[1] = _MemToFloat(buffer_1);             //y position of current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].position[2] = _MemToFloat(buffer_1);             //z position of current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].normals[0] = _MemToFloat(buffer_1);              //x component of normal on current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].normals[1] = _MemToFloat(buffer_1);              //y component of normal on current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].normals[2] = _MemToFloat(buffer_1);              //z component of normal on current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].uv[0] = _MemToFloat(buffer_1);                   //u coordinate on texture
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].uv[1] = _MemToFloat(buffer_1);                   //v coordinate on texture
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].unknown = _MemToInt(buffer_1);                   //unknown value
									if (nvr_struct.vertex_lists[i].type ==2) _ReadNext(buffer_1, 4);
                            }
                            cout << "Finished }\n";
     
                    } else {
     
                            for (int j=0; j < nvr_struct.vertex_lists[i].size; j++) {
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].position[0] = _MemToFloat(buffer_1);             //x position of current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].position[1] = _MemToFloat(buffer_1);             //y position of current vertex
                                    _ReadNext(buffer_1, 4);
                                    nvr_struct.vertex_lists[i].vertices[j].position[2] = _MemToFloat(buffer_1);             //z position of current vertex
                            }
                            cout << "Finished }\n";
     
                    }
            }
            cout << "  }\n\n";
     
            //get index list
            cout << "  index_lists["<<nvr_struct.count_index_list<<"] {\n\n";
            nvr_struct.index_lists = new nvr_indexlist_struct_class[nvr_struct.count_index_list];
     
            for (int i=0; i < nvr_struct.count_index_list; i++) {
                    _ReadNext(buffer_1, 4);
                    nvr_struct.index_lists[i].size = _MemToInt(buffer_1)/2;  //size of current index list
                    _ReadNext(buffer_1, 4);
                    nvr_struct.index_lists[i].d3dfmt = _MemToShort(buffer_1);       //d3dformat
     
                    cout << "     size:  " << nvr_struct.index_lists[i].size
                    << "    d3dformat: " << nvr_struct.index_lists[i].d3dfmt
                    << "      indices_"<<i<<" ["<<nvr_struct.index_lists[i].size<<"]        { Processing... ";
     
                    nvr_struct.index_lists[i].indices= new unsigned short[nvr_struct.index_lists[i].size];
     
                    for (int j=0; j < nvr_struct.index_lists[i].size; j++) {
                            _ReadNext(buffer_2, 2);
                            nvr_struct.index_lists[i].indices[j] = _MemToShort(buffer_2);           //vertex id
                    }
                    cout << "Finished }\n";
            }
            cout << "  }\n\n";
     
            //get models
            cout << "  models[" << nvr_struct.count_model << "]             { Processing... ";
            nvr_struct.models = new nvr_model_struct_class[nvr_struct.count_model];
     
            for (int i=0; i < nvr_struct.count_model; i++) {
                    _ReadNext(buffer_1, 4);
                    nvr_struct.models[i].flag_1 = _MemToInt(buffer_1);              //flag 1
                    _ReadNext(buffer_1, 4);
                    nvr_struct.models[i].flag_2 = _MemToInt(buffer_1);              //flag 2
                    for (int j=0; j < 10; j++) {
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].b[j] = _MemToFloat(buffer_1);      //b
                    }
                    _ReadNext(buffer_1, 4);
                    nvr_struct.models[i].material = _MemToInt(buffer_1);    //material
                    for (int j=0; j < 2; j++) {
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].model[j].vertex_index = _MemToInt(buffer_1);       //vertex index
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].model[j].vertex_offset = _MemToInt(buffer_1);      //vertex offset
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].model[j].vertex_length = _MemToInt(buffer_1);      //vertex length
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].model[j].index_index = _MemToInt(buffer_1);        //index index
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].model[j].index_offset = _MemToInt(buffer_1);       //index offset
                            _ReadNext(buffer_1, 4);
                            nvr_struct.models[i].model[j].index_length = _MemToInt(buffer_1);       //index length
                    }
     
            }
            cout << "Finished }\n\n";
     
            //get unknown_3s
            cout << "  unknown_3s[" << nvr_struct.count_unknown_3 << "]     { Processing... ";
            nvr_struct.unknown_3 = new nvr_unknown3_struct_class[nvr_struct.count_unknown_3];
     
            for (int i=0; i < nvr_struct.count_unknown_3; i++) {
                    for (int j=0; j < 6; j++) {
                            _ReadNext(buffer_1, 4);
                            nvr_struct.unknown_3[i].a[j] = _MemToFloat(buffer_1);           //a
                    }
                    for (int j=0; j < 4; j++) {
                            _ReadNext(buffer_1, 4);
                            nvr_struct.unknown_3[i].b[j] = _MemToInt(buffer_1);                     //b
                    }
            }
     
            cout << "Finished }\n\n}\n\n\n";
     
            //convert to .x files
            cout << "Converting "<<nvr_struct.count_model<<" models to X Format...\n\n";
     
            for (int i=0; i < nvr_struct.count_model; i++) {
     
                    int XFile_vertex_index = nvr_struct.models[i].model[0].vertex_index;
                    int XFile_vertex_offset = nvr_struct.models[i].model[0].vertex_offset;
                    int XFile_vertex_length = nvr_struct.models[i].model[0].vertex_length;
     
                    int XFile_index_index = nvr_struct.models[i].model[0].index_index;
                    int XFile_index_offset = nvr_struct.models[i].model[0].index_offset;
                    int XFile_index_length = nvr_struct.models[i].model[0].index_length;
     
                    string XFile_texture = nvr_struct.materials[nvr_struct.models[i].material].texture_filename;
     
                    stringstream ss;	// << "output\\" 
                    ss <<nvr_struct.materials[nvr_struct.models[i].material].name << nvr_struct.materials[nvr_struct.models[i].material].used << ".x";
                    string xFile_name = ss.str();
                    nvr_struct.materials[nvr_struct.models[i].material].used += 1;
     
                    cout << "Converting Model "<<i<<"/"<<nvr_struct.count_model<<"          "<< xFile_name << "\n";
     
     
                    stringstream ssXFile;
                    ssXFile << fixed << showpoint << setprecision(6);
     
                    ssXFile << _XFileHead() << "\n";
                    ssXFile << "Mesh {\n";
     
                    //positions
                    ssXFile << " " << XFile_vertex_length << ";\n";
                    for (int j=XFile_vertex_offset ; j < XFile_vertex_offset+XFile_vertex_length; j++) {
                            if(j < XFile_vertex_offset+XFile_vertex_length-1) {
                                    ssXFile << " " << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].position[0] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].position[1] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].position[2] << ";,\n";
                            } else {
                                    ssXFile << " " << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].position[0] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].position[1] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].position[2] << ";;\n\n";
                            }
                    }
                    //indices for positions
                    ssXFile << " " << ((int) XFile_index_length/3) << ";\n";
                    for (int j=XFile_index_offset ; j < XFile_index_offset+XFile_index_length; j += 3) {
                            if(j < XFile_index_offset+XFile_index_length-3) {
                                    ssXFile << " 3;" << (nvr_struct.index_lists[XFile_index_index].indices[j]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+1]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+2]-XFile_vertex_offset) << ";,\n";
                            } else {
                                    ssXFile << " 3;" << (nvr_struct.index_lists[XFile_index_index].indices[j]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+1]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+2]-XFile_vertex_offset) << ";;\n\n";
                            }
                    }
                    //noramls
                    ssXFile << " MeshNormals {\n  " << XFile_vertex_length << ";\n";
                    for (int j=XFile_vertex_offset ; j < XFile_vertex_offset+XFile_vertex_length; j++) {
                            if(j < XFile_vertex_offset+XFile_vertex_length-1) {
                                    ssXFile << "  " << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].normals[0] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].normals[1] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].normals[2] << ";,\n";
                            } else {
                                    ssXFile << "  " << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].normals[0] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].normals[1] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].normals[2] << ";;\n\n";
                            }
                    }
                    //indices for normals
                    ssXFile << "  " << ((int) XFile_index_length/3) << ";\n";
                    for (int j=XFile_index_offset ; j < XFile_index_offset+XFile_index_length; j += 3) {
                            if(j < XFile_index_offset+XFile_index_length-3) {
                                    ssXFile << "  3;" << (nvr_struct.index_lists[XFile_index_index].indices[j]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+1]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+2]-XFile_vertex_offset) << ";,\n";
                            } else {
                                    ssXFile << "  3;" << (nvr_struct.index_lists[XFile_index_index].indices[j]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+1]-XFile_vertex_offset) << ","
                                                    << (nvr_struct.index_lists[XFile_index_index].indices[j+2]-XFile_vertex_offset) << ";;\n }\n\n";
                            }
                    }
                    //texture coodrinates
                    ssXFile << " MeshTextureCoords {\n  " << XFile_vertex_length << ";\n";
                    for (int j=XFile_vertex_offset ; j < XFile_vertex_offset+XFile_vertex_length; j++) {
                            if(j < XFile_vertex_offset+XFile_vertex_length-1) {
                                    ssXFile << "  " << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].uv[0] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].uv[1] << ";,\n";
                            } else {
                                    ssXFile << "  " << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].uv[0] << ";"
                                                    << nvr_struct.vertex_lists[XFile_vertex_index].vertices[j].uv[0] << ";;\n }\n\n";
                            }
                    }
                    //material list
                    ssXFile << " MeshMaterialList {\n  1;\n  1;\n  0;\n\n";
                    //material
                    ssXFile << "  Material {\n"
                                    << "   1.000000;1.000000;1.000000;1.000000;;\n"
                                    << "   3.200000;\n"
                                    << "   0.000000;0.000000;0.000000;;\n"
                                    << "   0.000000;0.000000;0.000000;;\n\n";
                    //texutre
                    ssXFile << "   TextureFilename {\n"
                                    << "    \"texture\\\\" << XFile_texture << "\";\n   }\n  }\n }\n}";
     
                    //save to file
                    ofstream XFile;
                    XFile.open (xFile_name);
                    XFile << ssXFile.str();
                    XFile.close();
            }
     return 0 ;     
            while(1);
    }
     
     
    void _ReadNext(char *buffer, int bytes, bool seek)  {
            static int pos=0;
     
            if(!seek) {
                    for (int i=0; i<bytes; i++) {
                            buffer[i] = nvr_data[i+pos];
                    }
            }
     
            pos += bytes;
            return;
    }
     
    string _MemToString(char *buffer) {
            string ret = buffer;
            return ret;
    }
     
    unsigned short _MemToShort(char *buffer) {
            return *((short*) buffer);
            //return ((0xFF00&(buffer[1]<<8))|(0x00FF&buffer[0]));
    }
     
    unsigned int _MemToInt(char *buffer) {
            return *((int*) buffer);
            //return ((0xFF000000&(buffer[3]<<24))|(0x00FF0000&(buffer[2]<<16))|(0x0000FF00&(buffer[1]<<8))|(0x000000FF&buffer[0]));
    }
     
    float _MemToFloat2(char *buffer) {
            int full = ((0xFF000000&(buffer[3]<<24))|(0x00FF0000&(buffer[2]<<16))|(0x0000FF00&(buffer[1]<<8))|(0x000000FF&buffer[0]));
            int sign = 0x00000001&(full>>31);
            int exponent = 0x000000FF&(full>>23);
            int mantissa = 0x007FFFFF&full;
            float ret = round(pow(-1.0f, sign)*(1.0+((float)mantissa)/8388608)*pow(2.0f, exponent-127),6);
     
            if (!_finite(ret)) {ret=0;} //catch NaN and infinite
            return ret;
    }
     
    float _MemToFloat(char *buffer) {
            return *((float*) buffer);
    }
     
     
    string _NvrHeadToString(nvr_struct_class &nvr) {
            stringstream ss;
            ss      << "NVR {\n\n"
                    << "  magic:            " << nvr.magic << "\n"
                    << "  unknown_1:                " << nvr.unknown_1 << "\n"
                    << "  unknown_2:                " << nvr.unknown_2 << "\n"
                    << "  count_material:   " << nvr.count_material << "\n"
                    << "  count_vertex_list:        " << nvr.count_vertex_list << "\n"
                    << "  count_index_list: " << nvr.count_index_list << "\n"
                    << "  count_model:              " << nvr.count_model << "\n"
                    << "  count_unknown_3:  " << nvr.count_unknown_3 << "\n\n";
     
            return ss.str();
    }
     
    string _NvrMaterialToString(nvr_material_struct_class material) {
            stringstream ss;
            ss <<   "    " <<
                            material.name <<"|"<<
                            material.emissive_color[0] <<"|"<< material.emissive_color[1] <<"|"<< material.emissive_color[2] <<"|"<<
                            material.blend_color[0] <<"|"<< material.blend_color[1] <<"|"<< material.blend_color[2] <<"|"<< material.blend_color[3] <<"|"<<
                            material.texture_filename <<"|"<<
                            material.opacity <<"|"<<
                            material.blend_filename << "\n";
     
            return ss.str();
    }
     
    string _NvrVertexToString(nvr_vertex vertex) {
            stringstream ss;
            ss <<   "    " <<
                            vertex.position[0] <<"|"<< vertex.position[1] <<"|"<< vertex.position[2] <<"|"<<
                            vertex.normals[0] <<"|"<< vertex.normals[1] <<"|"<< vertex.normals[2] <<"|"<<
                            vertex.uv[0] <<"|"<< vertex.uv[1] <<"|"<<
                            vertex.unknown << "\n";
     
            return ss.str();
    }
     
    string _NvrVertexToString2(nvr_vertex vertex) {
            stringstream ss;
            ss <<   "    " <<
                            vertex.position[0] <<"|"<< vertex.position[1] <<"|"<< vertex.position[2] <<"\n";
     
            return ss.str();
    }
     
    /*string _NvrIndexToString(nvr_index index) {
            stringstream ss;
            ss <<   "    " <<
                            index.id[0] <<"|"<< index.id[1] <<"|"<< index.id[2] <<"\n";
     
            return ss.str();
    }*/
     
    string _NvrModelToString(nvr_model_struct_class model) {
            stringstream ss;
            ss <<   "    " <<
                            model.flag_1 <<"|"<< model.flag_2 <<"|"<< model.material <<"|"<<
                            model.model[0].vertex_index <<"|"<< model.model[0].vertex_offset <<"|"<< model.model[0].vertex_length <<"|"<< model.model[0].index_index <<"|"<< model.model[0].index_offset <<"|"<< model.model[0].index_length <<"|"<<
                            model.model[1].vertex_index <<"|"<< model.model[1].vertex_offset <<"|"<< model.model[1].vertex_length <<"|"<< model.model[1].index_index <<"|"<< model.model[1].index_offset <<"|"<< model.model[1].index_length <<"|"<<
                            "\n";
     
            return ss.str();
    }
     
    float round(float r, int places) {
            return floor(pow(10.0f, places)*r+0.5f)/pow(10.0f, places);
    }
     
    string _XFileHead() {
            string ret;
            ret = ""
                    "xof 0303txt 0032\n"
                    "template Vector {\n"
                    " <3d82ab5e-62da-11cf-ab39-0020af71e433>\n"
                    " FLOAT x;\n"
                    " FLOAT y;\n"
                    " FLOAT z;\n"
                    "}\n"
                    "\n"
                    "template MeshFace {\n"
                    " <3d82ab5f-62da-11cf-ab39-0020af71e433>\n"
                    " DWORD nFaceVertexIndices;\n"
                    " array DWORD faceVertexIndices[nFaceVertexIndices];\n"
                    "}\n"
                    "\n"
                    "template Mesh {\n"
                    " <3d82ab44-62da-11cf-ab39-0020af71e433>\n"
                    " DWORD nVertices;\n"
                    " array Vector vertices[nVertices];\n"
                    " DWORD nFaces;\n"
                    " array MeshFace faces[nFaces];\n"
                    " [...]\n"
                    "}\n"
                    "\n"
                    "template MeshNormals {\n"
                    " <f6f23f43-7686-11cf-8f52-0040333594a3>\n"
                    " DWORD nNormals;\n"
                    " array Vector normals[nNormals];\n"
                    " DWORD nFaceNormals;\n"
                    " array MeshFace faceNormals[nFaceNormals];\n"
                    "}\n"
                    "\n"
                    "template Coords2d {\n"
                    " <f6f23f44-7686-11cf-8f52-0040333594a3>\n"
                    " FLOAT u;\n"
                    " FLOAT v;\n"
                    "}\n"
                    "\n"
                    "template MeshTextureCoords {\n"
                    " <f6f23f40-7686-11cf-8f52-0040333594a3>\n"
                    " DWORD nTextureCoords;\n"
                    " array Coords2d textureCoords[nTextureCoords];\n"
                    "}\n"
                    "\n"
                    "template Material {\n"
                    " <3d82ab4d-62da-11cf-ab39-0020af71e433>\n"
                    " ColorRGBA faceColor;\n"
                    " FLOAT power;\n"
                    " ColorRGB specularColor;\n"
                    " ColorRGB emissiveColor;\n"
                    " [...]\n"
                    "}\n"
                    "\n"
                    "template MeshMaterialList {\n"
                    " <f6f23f42-7686-11cf-8f52-0040333594a3>\n"
                    " DWORD nMaterials;\n"
                    " DWORD nFaceIndexes;\n"
                    " array DWORD faceIndexes[nFaceIndexes];\n"
                    " [Material <3d82ab4d-62da-11cf-ab39-0020af71e433>]\n"
                    "}\n"
                    "\n"
                    "template TextureFilename {\n"
                    " <a42790e1-7810-11cf-8f52-0040333594a3>\n"
                    " STRING filename;\n"
                    "}\n";
                   
            return ret;
    }
```
## Post #14
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-26T16:52:11+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

hmmm.... 
I don't know what we can do now.
No files got extracted, and there are two files that won't be converted.
Any Ideas what we can do?

And any ideas for the new file format?


EDIT: Okay, It seems so that the files got converted, but only 714 of 716 files


EDIT2: Aaaaaand we need a way to recompile the map to nvr^^
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-02-26T23:47:02+00:00
- Post Title: League of Legends Map - NVR decompiling/recompiling

[out]
## Post #16
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-27T08:48:44+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

But will it be possible to decrypt the newer Files like the older files ?
I really want to create my own map.
Older maps like "Old twisted Treeline" and "Summoner's Rift (Winter & Autumn) already work again for me in "Co-op vs AI" and "Custom" mode.

(For example, a Screenshot)
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-02-28T11:17:54+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

[out]
## Post #18
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-02-28T15:03:37+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

Now, I uploaded the whole Folder of one of the maps.
The package includes: 
- scripts (I already decompiled luaobj to readable lua), 
- sco and scb files (Models, I think. sco is readable as text with notepad++/wordpad/editor)
- dat files (can be opened with any text editor. It's readable as text).
- dds files (textures and images) 
- inibin - files (don't know how to open them | file size ~1kb)

now I try to find out how League of Legends read the maps, but it could be really hard.


[DOWNLOAD MAP-FOLDER](http://uploaded.net/file/pt4ygptm)
## Post #19
- Username: Pupix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 22, 2010 11:50 pm
- Post datetime: 2014-03-02T14:44:33+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> Reply from ChrisX930
>
> Now, I uploaded the whole Folder of one of the maps.
The package includes: 
- scripts (I already decompiled luaobj to readable lua), 
- sco and scb files (Models, I think. sco is readable as text with notepad++/wordpad/editor)
- dat files (can be opened with any text editor. It's readable as text).
- dds files (textures and images) 
- inibin - files (don't know how to open them | file size ~1kb)

now I try to find out how League of Legends read the maps, but it could be really hard.


DOWNLOAD MAP-FOLDER

What did you use to decompile the luaobj files?
I keep getting "DECOMPILER ERROR: Unhandled construct in list (SETLIST)" when trying to decompile the files with luadec51.

Btw scb are just sco converted in binary, and yes, they are in game models.
## Post #20
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-03-02T14:50:48+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

I used luadec v2.1 r80 by viruscamp^^
## Post #21
- Username: Pupix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 22, 2010 11:50 pm
- Post datetime: 2014-03-02T15:08:49+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> Reply from ChrisX930
>
> I used luadec v2.1 r80 by viruscamp^^

I am still getting the same error. I should have mentioned that I get this error when I try to decompile character related .luaobj files not the ones from the LEVELS folders.

May I also ask how did you manage to add the other maps into your LoLClient.exe( the launcher ) ? Did you edit the .dat files?
## Post #22
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-03-02T15:19:30+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> Reply from Pupix
>
> ChrisX930 wrote:I used luadec v2.1 r80 by viruscamp^^

I am still getting the same error. I should have mentioned that I get this error when I try to decompile character related .luaobj files not the ones from the LEVELS folders.

May I also ask how did you manage to add the other maps into your LoLClient.exe( the launcher ) ? Did you edit the .dat files?

I had to edit more then only one file^^ 
I don't really want to describe how you can add other maps to the game, because I think I'm the only one atm who can do this / who know how it works.


The Character-related luaobj files? I'll check it out 
EDIT: Same decompiler Error with character related scripts
## Post #23
- Username: Pupix
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 22, 2010 11:50 pm
- Post datetime: 2014-03-02T15:30:20+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> Reply from ChrisX930
>
> Pupix wrote:ChrisX930 wrote:I used luadec v2.1 r80 by viruscamp^^

I am still getting the same error. I should have mentioned that I get this error when I try to decompile character related .luaobj files not the ones from the LEVELS folders.

May I also ask how did you manage to add the other maps into your LoLClient.exe( the launcher ) ? Did you edit the .dat files?

I had to edit more then only one file^^ 
I don't really want to describe how you can add other maps to the game, because I think I'm the only one atm who can do this / who know how it works.


The Character-related luaobj files? I'll check it out 
EDIT: Same decompiler Error with character related scripts

You are not the only one who can do that for sure. You could google AstralFoxy, she enabled players to pick the same champion more than once, hence the "One for All" mode Riot made available after they noticed that almost everybody had modified their in game files to do able to do that.
She only needed to edit ClientLibGame.dat to allow this.
## Post #24
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-03-02T15:33:47+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> Reply from Pupix
>
> 

You are not the only one who can do that for sure. You could google AstralFoxy, she enabled players to be pick the same champion more than once, hence the "One for All" mode Riot made available after they noticed that almost everybody had modified their in game files to do able to do that.
She only needed to edit ClientLibGame.dat to allow this.

I know this, but Riot already fixed this.
But I added a new menu (ChrisX930's Mods) with all available modes. And I can re-enable all maps and possibly, add new maps (if I could create my own)
## Post #25
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2014-03-03T08:52:38+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

It is very interesting subject that LOL can be made mod.
I was hard-coded like below to check vertex type.

```
    for ( int i=0 ; i < m_Header.mVertexArrayCount ; ++i )
    {
        if ( flagArray[i] == false )
        {
            continue;
        }

        NVRVertexArray tempMesh ;

        buffer.Read( &tempMesh.mDataSize, sizeof( tempMesh.mDataSize ) ) ;

        uint32 currPos    = buffer.GetPosition() ;
        int8   vertType44 = *( buffer.GetData() + currPos + 43 ) ; // just hack
        int8   vertType40 = *( buffer.GetData() + currPos + 39 ) ; // just hack
        uint32 bookMark = currPos + tempMesh.mDataSize ;

        if ( vertType44 == -1 ) // if vertex size is 44 , always -1 ( 0xFF )
        {
            uint32 vertCount = tempMesh.mDataSize / sizeof( NVRVertex44 ) ;
            tempMesh.mVertices.resize( vertCount ) ;

            for ( int j=0 ; j < vertCount ; ++j )
            {
                NVRVertex44 tempVert ;
                buffer.Read( &tempVert, sizeof( tempVert ) ) ;

                tempMesh.mVertices[j].mPosition = tempVert.mPosition ;
                tempMesh.mVertices[j].mNormal   = tempVert.mNormal ;
                tempMesh.mVertices[j].mUV       = tempVert.mUV ;
                //tempMesh.mVertices[j].mTangent  = tempVert.mTangent ;
            }
        }
        else if ( vertType40 == -1 ) // if vertex size is 40 , always -1 ( 0xFF )
        {
            uint32 vertCount = tempMesh.mDataSize / sizeof( NVRVertex40 ) ;
            tempMesh.mVertices.resize( vertCount ) ;

            for ( int j=0 ; j < vertCount ; ++j )
            {
                NVRVertex40 tempVert ;
                buffer.Read( &tempVert, sizeof( tempVert ) ) ;

                tempMesh.mVertices[j].mPosition = tempVert.mPosition ;
                tempMesh.mVertices[j].mNormal   = tempVert.mNormal ;
                tempMesh.mVertices[j].mUV       = tempVert.mUV ;
                //tempMesh.mVertices[j].mTangent  = tempVert.mTangent ;
            }
        }
        else
        {
            uint32 vertCount = tempMesh.mDataSize / sizeof( NVRVertex36 ) ;
            tempMesh.mVertices.resize( vertCount ) ;
            buffer.Read( &tempMesh.mVertices[0],
                         sizeof( NVRVertex36 ) * vertCount ) ;
        }

        m_MeshArray.push_back( tempMesh ) ;

        buffer.SetPosition( bookMark ) ;
    }

```
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-03-03T21:56:09+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

[out]
## Post #27
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2014-03-04T05:59:54+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> I have seen 4 vertex formats, although, there could be 5 or more.
>
> 44, 40, 36, 24, and 12 bytes.
I had found just 4 vertex types, too.

> That 0xFF byte could simply be the alpha value of a color stored as a 32-bit value (RGBA).
>
> Which means, your check is prone to error, and will fail sometimes.
I think they are 4 byte-packed tangent, and binormal ...

NVRSubmesh1 uses 44, 40, 36 vertex, and
NVRSubmesh2 uses 12 vertex.

[http://code.google.com/p/gamefileformat ... lateNVR.bt](http://code.google.com/p/gamefileformat/source/browse/trunk/FileFormat/LeagueOfLegendsTemplateNVR.bt)
and I had got this picture.
[LoL01.png](https://xentaxbackup.github.io/file/7066_LoL01.png)
## Post #28
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-03-20T20:34:37+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

Any updates to this?
Anyone knows if it possible to Edit this files?
## Post #29
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-07-15T01:22:46+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

My Documentation on it, I haven't read any of the posts so sorry if anything is incorrect etc:

[http://pastebin.com/pvxd6ABi](http://pastebin.com/pvxd6ABi)
## Post #30
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-15T23:14:03+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

[out]
## Post #31
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2014-07-16T11:28:25+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

> Reply from Wobble
>
> Uli wrote:My Documentation on it, I haven't read any of the posts so sorry if anything is incorrect etc:
http://pastebin.com/pvxd6ABi

There is nothing in the NVR file that I can find that accurately describes the vertex buffer format.

For example, this variable, IndexBufferFormat Format, can be 0x65 for all vertex buffers, 
yet the vertex buffer itself can be either 40 bytes or 12 bytes.  Unless this information is stored somewhere else,
I don't see how to load this data.

Unfortunately extracting exact data on that is super difficult, it looks like the data gets passed into a lot of same sectors as what other things are using.  I assume there are some form of flags in it to specify length at least thats what it looks like but again due to it getting reused like crazy no idea what is happening with them.

I'll need to grab the file and get a bunch of different ones and see whats going on, but I'm not interested enough unfortunately to dedicate that much time.
## Post #32
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-19T17:05:05+00:00
- Post Title: Re: League of Legends Map - NVR decompiling/recompiling

[out]
