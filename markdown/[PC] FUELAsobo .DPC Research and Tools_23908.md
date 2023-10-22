## Post #1
- Username: EmilyWasAway
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 19, 2021 5:24 am
- Post datetime: 2021-05-18T23:49:24+00:00
- Post Title: [PC] FUEL/Asobo .DPC Research and Tools

Introduction

This topic is first and foremost dedicated to the research of the .DPC file format from Asobo games. Although I have provided tools I developed to aid my research, they are very much a work in progress and I have deliberately chosen not to post this in the [Tools & Programs](https://forum.xentax.com/viewforum.php?f=31%20section) section due to their severe limitations. The title of this post refers to FUEL because that is the game I studied, but this format is used across many Asobo games so this research should be useful to everyone studying Asobo games.  

Research

Huge thanks to [Ikskoks](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=43476) for transferring my research from the [FUEL Modding ToolKit GitHub Wiki](https://github.com/widberg/fmtk/wiki) to the [Asobo Studio DPC DPS XeNTaX Wiki Entry](https://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS) . Some notable entries in the FMTK Wiki include: [Asobo DPC File Format Specification](https://github.com/widberg/fmtk/wiki/Asobo-DPC-File-Format-Specification), [Asobo Classes](https://github.com/widberg/fmtk/wiki/Asobo-Classes), [Asobo LZ Compression](https://github.com/widberg/fmtk/wiki/Asobo-LZ-Compression), and [Asobo CRC32](https://github.com/widberg/fmtk/wiki/Asobo-CRC32).

Asobo DPC File Format Specification

This page contains a full description of the contents of a .DPC file with a detailed description of how each field is used and calculated. In this topic I will provide a tool to extract and repack any standard .DPC file. Also the tool can parse any .DPC to a json format matching this specification to help study the values of each field easily. The tool has some limitations in its repacking capabilities because I do not fully understand how a few remaining fields are calculated. The [BlockDescription](https://github.com/widberg/fmtk/wiki/Asobo-DPC-File-Format-Specification#block-description) structure has a workingBufferOffset that I am unable to calculate. The [PrimaryHeader](https://github.com/widberg/fmtk/wiki/Asobo-DPC-File-Format-Specification#primary-header) structure has the field poolManifestUnused0 which I am unable to calculate. Neither of these fields are needed to extract the .DPC but lead to some issues when repacking as described later in this topic. If you are able to help calculate either of these fields, please let me know.

Associated File Types

This subsection of the Specification page specifies file formats that are commonly associated with .DPC archives. Notable .NPC files which map CRC32 hashes to strings (read the Asobo CRC32 section of this topic to see why this is useful). Also .LPC and .DPC.LAYOUT which provide information about the order of objects and their sizes in .DPC archives. And .IWR this contains information for WorldRef_Z objects in FUEL.

Asobo Classes

This page contains format information about the Class Object files that you get when you extract a .DPC. This page by far requires the most research. There are a few Noesis scripts to extract usable data from these formats provided in this topic.

Asobo LZ Compression

Many Asobo games use the same LZSS compression algorithm; this page contains a C++ implementation of both the original decompression and original compression algorithms as well as an alternate compression algorithm. Notably, the alternate compression algorithm here is compatible with the Asobo LZSS decompression algorithm but produces a more compressed output than the compression algorithm Asobo uses in-house. For that reason, if you decompress something from a .DPC then compress the decompressed output, the newly compressed output will not exactly match the original compressed data. Although if you decompress the recompressed data it will exactly match the origin decompressed data despite being compressed with a different algorithm.

Asobo CRC32

This page contains the CRC32 algorithm used by Asobo in most games. Most frustratingly, .DPC files do not store the path of the files they contain as a string but rather as a 32-bit CRC hash of the path string. For this reason, it is impossible to recover the file names of objects in the archive directly. However, using other techniques like Reverse Engineering the game binary and examining files shipped with the game you can recover some of the paths. For games like Garfield 2 (PC), Monopoly Plus (PC), and WALL-E (PSP) this is not a concern because the games ship with the aforementioned .NPC Name PC files which map the hashes to the paths. For games that do not contain .NPC files I will provide a research tool to brute force hashes.

Tools

All of the following tools are a work in progress and intended for research purposes NOT modding purposes due to their severe limitations. Please post any bug reports for these tools to the issues page of their respective GitHub repository unless you don't have a GitHub account. I am 100% open to pull requests on all of these tools.

dpc

This project is where most of the magic happens. The latest pre-built binary releases for all platforms are located on the [GitHub Releases page](https://github.com/widberg/dpc/releases).

The help menu should give you a good idea of what this tool does.

```
widberg <https://github.com/widberg>
Work with DPC files

USAGE:
    dpc.exe [FLAGS] [OPTIONS] --game <GAME> [-- <CUSTOM_ARGS>]
    dpc.exe <SUBCOMMAND>

FLAGS:
    -c, --create          directory -> DPC
    -e, --extract         DPC -> directory
    -f, --force           Don't ask about existing folder
    -l, --lz              Apply Asobo LZ compression/deflation when appropriate
    -O, --optimization    Optimize the DPC
    -q, --quiet           No console output
    -u, --unsafe          Don't check the version string for compatibility
    -v, --validate        Checks if your DPC is valid  
    -h, --help            Prints help information      
    -V, --version         Prints version information   

OPTIONS:
    -g, --game <GAME>        The game the dpc should be compatible with [possible values: fuel]
    -i, --input <INPUT>      The input DPC file        
    -o, --output <OUTPUT>    The output directory      

ARGS:
    <CUSTOM_ARGS>    Supply arguments directly to the dpc backend

SUBCOMMANDS:
    help    Prints this message or the help of the given subcommand(s)
    lz      Used to compress raw files
    obj     Used to compress object files

EXAMPLES:
    -g fuel -- -h
    -cflO -g fuel -i BIKE.DPC.d -o BIKE.DPC
    -ef -g fuel -i /FUEL/**/*.DPC
```


Some quick examples of basic functionality:

To extract FONTES.DPC and decompress all of its objects to a directory called MY_FONTES

```
dpc -el -g fuel -i FONTES.DPC -o MY_FONTES
```


To then repack the FONTES.DPC from your MY_FONTES directory without compressing the objects

```
dpc -cf -g fuel -i MY_FONTES -o FONTES.DPC
```


To create a json layout of FONTES.DPC in the format of the specification

```
dpc -v -g fuel -i FONTES.DPC -o FONTES.DPC.json
```


Limitations of this tool: (1) Sometimes you may have to increase the block workingBufferOffset in the manifest.json file by a multiple of 2048 when repacking .DPC archives with modified/additional contents.

At the moment this tool only supports FUEL .DPC archives but I am open to accepting pull requests that add support for additional games; I am unlikely to add any other games myself until my research with FUEL is complete.

fmt_fuel

This repository is home to the python Noesis scripts that have been developed for the Class Object formats. To install these scripts, download the repository as a .zip using the green Code dropdown and extract the .py files to your Noesis python directory. Please feel free to make a pull request and add more scripts!

fuel-brute

This repository contains several projects aimed at brute forcing path names from .DPC CRC32 hashes. To be honest, I have mostly given up on this endeavor but have included the project here incase anyone wants to take a look and maybe continue my research in this area.

fmtk

This repository has an alternative launcher for the FUEL executable that hooks many functions and provides verbose logging output and full stack traces when the game crashes. Also it counters several of the FUEL and xlive anti-debugging features making it possible to hook with your debugger of choice. If you intend to perform dynamic analysis on the game then I strongly recommend you use the fmtk launcher.

Conclusion
Due to forum rules I am unable to attach any .DPC files to this topic because they are the property of Asobo. Many people consider FUEL to be abandonware but I'm going to respect Asobo's property and the rules of this forum by not include it or any links to the websites that provide the game and its .DPC files for free.

Please keep me in the loop with any .DPC research as I am very interested. Thank you for reading this topic and I hope it was useful to you!
