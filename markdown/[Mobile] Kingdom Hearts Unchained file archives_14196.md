## Post #1
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-04-07T09:18:00+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Kingdom Hearts Unchained seems to use two files to store almost all gameplay elements: misc.mp4 and misc.png. The files originally used in the install archive are enlarged whenever there is an update, the post-installation file download increases their size a hundred times.

The question is how they work, the smaller file is probably referencing stuff in the bigger one, but beyond that I'm clueless where to start.

Since the game is free2play it shouldn't be a problem linking these two files (ca. 20 MB) here:
[http://www10.zippyshare.com/v/YhnYeNaS/file.html](http://www10.zippyshare.com/v/YhnYeNaS/file.html)

The original apk file containing these files can be downloaded here:
[https://apkpure.com/store/apps/details? ... lay.khuxww](https://apkpure.com/store/apps/details?id=com.square_enix.android_googleplay.khuxww)

If there is interest in the larger post-installation files (over 1 GB), I could upload them too.
## Post #2
- Username: ggbhtg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 10, 2016 2:53 am
- Post datetime: 2016-04-09T19:11:11+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

What more can I say than, PLEASE FOR THE LOVE OF GOD, POST THE FILES. I've spent the entire time since the NA version came out trying to figure out how to get it on my phone, and long story short, I need the post-install files. All of it. The entire "data/data/com" square enix whatever folder. Also, PLEASE don't make an account/avatar before exporting the files, because the account and save data carries over inside of the misc.mp4 file, and I could not find a way to delete said account by itself. I found an upload of all the files by someone on some jank, ad-filed website I don't care to remember the name of, only to get screwed over by that revelation. It needs to be clean, so people savvy enough to go through the process can go right in on their own accounts.
## Post #3
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-04-10T05:00:20+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

The misc.mp4 file contains multiple archives

```
    int magic;
    short unk0;
    short unk1;
    short headerSize;
    short extensionSize;
    short unk2;
    short unk3;
    int dataSize;
    int unknownSize;
};

```

To get the next archive in the misc.mp4 file, just keep adding an offset of headerSize + extensionSize + dataSize

Example C code: [https://db.tt/dMIdazju](https://db.tt/dMIdazju)
Hope this helps a bit
## Post #4
- Username: ggbhtg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 10, 2016 2:53 am
- Post datetime: 2016-04-10T19:04:37+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

> Reply from MayBeePah
>
> The misc.mp4 file contains multiple archives
Code: Select allstruct BGADArchive {
    int magic;
    short unk0;
    short unk1;
    short headerSize;
    short extensionSize;
    short unk2;
    short unk3;
    int dataSize;
    int unknownSize;
};

To get the next archive in the misc.mp4 file, just keep adding an offset of headerSize + extensionSize + dataSize

Example C code: https://db.tt/dMIdazju
Hope this helps a bit
 If that was directed towards me, sorry, but I don't know anything about scripting. More to the point, all I want is to copy-paste the full "data/com.squareenix" yada yada whatever folder in directly, because that jank file I mentioned proved to me that the game can recognize the files properly when you do that. Problem is, that file already had an account made, at level 15, no less.

I need a clean folder of files, because misc.mp4 is larger than my phone's entire cache folder, meaning it's impossible for me to download it myself. My phone can't store app data on the external SD Card for some stupid manufacturing cost-saving reason, and I've bricked my phone multiple times trying to do all this ever since the NA version came out. I've asked on KH13, KHInsider, Reddit, and more, but everyone just ignores me, so I'm very annoyed at this point. I just, need, the files, please.
## Post #5
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-04-10T23:21:59+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Thank you MayBeePah, I'll try to make sense of it. Were you able to extract one of the archives in the misc.mp4?

@ggbhtg: I uploaded all files here:
[http://www.share-online.biz/dl/GE20MF5OETM](http://www.share-online.biz/dl/GE20MF5OETM)
[http://www.share-online.biz/dl/2KGQOF5OS8O6](http://www.share-online.biz/dl/2KGQOF5OS8O6)
[http://www.share-online.biz/dl/67HSUF5OQ8X](http://www.share-online.biz/dl/67HSUF5OQ8X)
[http://www.share-online.biz/dl/Q2ILXF5O8M](http://www.share-online.biz/dl/Q2ILXF5O8M)

It's four parts because my internet connection is not that good and gets cut sometimes. It's packed with 7-zip, I didn't click on anything after the download started so hopefully this will help you. You could always get these files with an android emulator yourself though.
## Post #6
- Username: ggbhtg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 10, 2016 2:53 am
- Post datetime: 2016-04-11T03:02:39+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

> Reply from Azurfan
>
> Thank you MayBeePah, I'll try to make sense of it. Were you able to extract one of the archives in the misc.mp4?

@ggbhtg: I uploaded all files here:
http://www.share-online.biz/dl/GE20MF5OETM
http://www.share-online.biz/dl/2KGQOF5OS8O6
http://www.share-online.biz/dl/67HSUF5OQ8X
http://www.share-online.biz/dl/Q2ILXF5O8M

It's four parts because my internet connection is not that good and gets cut sometimes. It's packed with 7-zip, I didn't click on anything after the download started so hopefully this will help you. You could always get these files with an android emulator yourself though.

THANK. YOU. I can't use an emulator because I don't have my own computer. It's gonna take a while to retrieve on my own crap internet connection, but I'll definitely post my results tomorrow.
## Post #7
- Username: ggbhtg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 10, 2016 2:53 am
- Post datetime: 2016-04-12T04:28:38+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Ok....unfortunately, I still can't get the game to actually run. Why? Because I get a "logged out due to inactivity" error. If I copy paste in certain files, this error message triggers and locks me into the title screen. Misc.mp4 isn't one of these files, but there's still a big issue here.

Initially, I seemed to circumvent this by installing the game without pasting in your files first, extracted  cookieFile.txt, then pasted it over your cookies that seem to just become invalid to the game after a period of time. I've not done research yet to know if this is a known issue. HOWEVER, even though I got the game to run using this fix, and made it all the way to avatar creation and clan selection, the game spontaneously gave me the "inactivity" error anyway.

So right now, I'm trying to figure out which combination of files will actually let the game run, hoping that this isn't caused by that Permission I had to remove in order to get the apk to even install.

The worst part? This error also cause the game's data files to completely self-destruct on my end. That means I have to keep going back and forth on my phone to try different variations of using your files and fresh files from the game to trick itself into running properly...and every time I'm wrong, I have to uninstall and reinstall the app from scratch and twiddle my thumbs while that 1GB misc file transfers.

It also doesn't help that there's a specific file(s) that detects whether you have the misc files and whatever else is in the download. This file decides you don't actually have the download, gives a "storage space error" when you try and start the game, because it wants to download everything from scratch, then blows up all your app's files like the inactivity error.
## Post #8
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-04-13T05:36:25+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

I can decrypt and uncompress the archive with names now 
But the images and some other files are custom formats (PNGs are compressed). I'll figure them out soon...
[exampleFiles.png](https://xentaxbackup.github.io/file/10767_exampleFiles.png)
## Post #9
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-04-13T09:48:31+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Omg, you are my hero MayBeePah.
## Post #10
- Username: Kori
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 12, 2016 5:05 pm
- Post datetime: 2016-04-13T10:54:01+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Dumb question, but would it be possible to get the player character body parts(hair, faces, limbs, outfits, etc) extracted? I realized they could probably be used in animations and neat stuff like that.
## Post #11
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2016-04-15T07:43:32+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

> Reply from MayBeePah
>
> I can decrypt and uncompress the archive with names now 
But the images and some other files are custom formats (PNGs are compressed). I'll figure them out soon...

Could you share more on how you were able to get the file names? The game appears to be using the cocos2d-x sdk. It may use "VP8L" as an image format. I'm not sure if they would use Google's WebP though since it's unconventional.
## Post #12
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-04-24T10:05:42+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Sorry, I've been busy and I forgot to work on Unchained.
I haven't got time at the moment to continue but here's the decryption algorithm if anyone wants to try:

```

int khux_random(int seed) {
    return 0x19660D * seed + 0x3C6EF35F;
}

void khux_decrypt(int* data, int length, int key) {
    int i = 0;
    int count = (length + 3) >> 2;
    
    while (i < count) {
        key = khux_random(key);
        data[i] ^= key;
        i++;
    }
}

struct BGAD {
    int magic;
    short key_type;
    short unk;
    short header_size;
    short name_length;
    short data_type;
    short is_compressed;
    int data_size;
    int decompressed_size;
    
    //char name[nameLength];
    //char data[dataSize];
    
    /* how to:
        decrypt name: khux_decrypt(&name, name_length, data_size)
        decrypt data: khux_decrypt(&data, data_size, name_length)
     
        calculate offset to next BGAD file: header_size + name_length + data_size
     
        validate: magic == BGADMagic
     
        after decryption use zlib to decompress:
            if (is_compressed) {
                void* decompressed_buffer = malloc(decompressed_size);
                uncompress(decompressed_buffer, &decompressed_size, &data, data_size)
            }
     */
};

```
## Post #13
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-05-18T17:14:47+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Okay I tried but failed, getting the decryption to work seems to be way out of my league. Did anyone here had more luck with it?
## Post #14
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-05-19T23:19:05+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

This should extract every file in the misc.mp4 file
I just made this quickly so tell me if anything went wrong 

requires zlib
usage: khux_decrypt .../misc.mp4 .../'directory name'

```
#include <string.h>
#include <stdlib.h>
#include <zlib.h>
#include <sys/stat.h>

#define BGADMagic 0x44414742
#define BGADSize sizeof(struct BGAD)
#define BGADMaxNameLength 0x100
#define BGADMaxDataSize 0x1000000

#define false 0
#define true 1

#define CatchError(condition) if (condition) { return false; }
#define Read(ptr, size) CatchError(fread(ptr, size, 1, file) != 1)

int khux_random(int seed) {
    return 0x19660D * seed + 0x3C6EF35F;
}

void khux_decrypt(int* data, int length, int key) {
    int count = (length + 3) >> 2;
    
    for (int i=0; i<count; i++) {
        key = khux_random(key);
        data[i] ^= key;
    }
}

struct BGAD {
    int magic;
    short key_type;
    short unk;
    short header_size;
    short name_length;
    short data_type;
    short is_compressed;
    int data_size;
    int decompressed_size;
};

struct BGADInfo {
    struct BGAD header;
    void* name;
    void* data;
    void* decompressed;
};

typedef struct BGADInfo BGADInfo;

void BGADInfoInit(BGADInfo* info) {
    info->name = malloc(BGADMaxNameLength);
    info->data = malloc(BGADMaxDataSize);
    info->decompressed = malloc(BGADMaxDataSize);
}

void BGADDecryptName(BGADInfo* info) {
    khux_decrypt(info->name, info->header.name_length, info->header.data_size);
    
    ((char*)info->name)[info->header.name_length] = 0;
}

void BGADDecryptData(BGADInfo* info) {
    khux_decrypt(info->data, info->header.data_size, info->header.name_length);
    
    if (info->header.is_compressed) {
        unsigned long int size = info->header.decompressed_size;
        uncompress(info->decompressed, &size, info->data, info->header.data_size);
    }
}

int ReadBGAD(FILE* file, BGADInfo* info) {
    Read(&info->header, BGADSize)
    
    CatchError(info->header.magic != BGADMagic)
    CatchError(info->header.name_length > BGADMaxNameLength)
    
    Read(info->name, info->header.name_length)
    BGADDecryptName(info);

    CatchError(info->header.data_size > BGADMaxDataSize)
    CatchError(info->header.decompressed_size > BGADMaxDataSize)
    
    Read(info->data, info->header.data_size)
    BGADDecryptData(info);

    return true;
}

void WriteBGAD(FILE* file, BGADInfo* info) {
    void* ptr = info->header.is_compressed
        ? info->decompressed
        : info->data;
    
    int size  = info->header.is_compressed
        ? info->header.decompressed_size
        : info->header.data_size;
    
    fwrite(ptr, size, 1, file);
}

void CreateDirectories(char** base, char* directories) {
    char* directory = strtok(directories, "/");
    char* next_directory;
    
    mkdir(*base, S_IRWXU | S_IRWXG | S_IROTH | S_IXOTH);
    
    while (directory != NULL) {
        next_directory = strtok(NULL, "/");
    
        strncat(*base, "/", 1);
        strncat(*base, directory, strlen(directory));
        
        if (next_directory != NULL) {
            mkdir(*base, S_IRWXU | S_IRWXG | S_IROTH | S_IXOTH);
        }
        
        directory = next_directory;
    }
}

int main(int argc, const char * argv[]) {
    setbuf(stdout, NULL);
    
    char* in_path = (char*)argv[1];
    char* out_path = (char*)argv[2];
    unsigned long out_path_len = strlen(out_path);
    
    FILE* file = fopen(in_path, "r");
    BGADInfo* info = malloc(sizeof(BGADInfo));
    BGADInfoInit(info);
    
    char* write_path = malloc(0x100);
    
    while (ReadBGAD(file, info)) {
        memset(write_path, 0, 0x100);
        strncat(write_path, out_path, out_path_len);
        
        CreateDirectories(&write_path, info->name);
    
        FILE* out_file = fopen(write_path, "w");
        CatchError(out_file == NULL)
        
        WriteBGAD(out_file, info);
        fclose(out_file);
    }
    
    fclose(file);
    
    return 0;
}

```
## Post #15
- Username: Elric99
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 20, 2016 11:11 pm
- Post datetime: 2016-05-21T07:48:20+00:00
- Post Title: [Mobile] Kingdom Hearts Unchained file archives

Would a compiled version be too much to ask for? I made some quick attempts that didn't work out, so I would be really thankful for one.
## Post #16
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-05-21T09:01:54+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Sorry I'm using a mac at the moment and can't compile for windows. Did you include zlib?
Here's all the files you need to compile if anyone's having trouble: [https://db.tt/6OuMv14j](https://db.tt/6OuMv14j)
## Post #17
- Username: Elric99
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 20, 2016 11:11 pm
- Post datetime: 2016-05-22T17:58:03+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Thanks for the files, unfortunately it doesn't compile either. I even tried switched from Visual Studio to MinGW, maybe it's a Windows specific problem, I really don't know enough about this.
## Post #18
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-05-22T22:52:12+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

I updated it with support for windows but i can't tell if it'll compile, hope it will 
[https://db.tt/6OuMv14j](https://db.tt/6OuMv14j)
## Post #19
- Username: Elric99
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 20, 2016 11:11 pm
- Post datetime: 2016-05-23T09:02:03+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

I was able to compile it after I linked an already compiled zlib library, I'm too much of a noob to understand why including zlib.h wasn't enough to recognize the decompress command, I always got an "undefinied reference error".

Anway, after finally having compiled it, the program still doesn't seem to work. I use it as you described on the last page: khux_decrypt "path to misc.mp4"misc.mp4 "output folder" but absoutely nothing happens.

I probably broke something in the process, hopefully someone more competent than me can chime in.
Edit: After having a deeper look at the resulting exe there really seems to be something wrong with it, so forget what I said above.

Maybe I should just try to split the process, make a script for the decryption (is this possible with QuickBMS?) and decompress the files afterwards.
## Post #20
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2016-06-02T00:47:24+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Yo,

So after a certain someone annoyed me enough so that I fix (and partially reprogram to be able to repack archs) this soft to be able to run on windows
here it is
[http://www.govanify.com/files/khuxdecry ... ypt.tar.gz](http://www.govanify.com/files/khuxdecrypt/khuxdecrypt.tar.gz)

files that cannot be used(so far only / file that is a filelist, present in misc.png) are renamed as @noname. khux can have VERY long filenames so windows user
should have a lite path such as C:\TEST\ pointing to the extracted files.

Here are also compiled versions both for windows and linux, not any for MACs b\c, excepted MayBeePah, who uses macs anyways ;p

[http://www.govanify.com/files/khuxdecry ... ecrypt.elf](http://www.govanify.com/files/khuxdecrypt/khuxdecrypt.elf)
[http://www.govanify.com/files/khuxdecry ... ecrypt.exe](http://www.govanify.com/files/khuxdecrypt/khuxdecrypt.exe)

Not making any diff/patch file but eh you have a makefile and compiled binaries, should be enough.
Not much to say, if you want to see stuff check the source.

On those words me, the white knight of the...what already?
Oh whatever with those endings, I'll just leave on those words.
-GY
## Post #21
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-06-02T03:43:01+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Thanks GovanifY for this 

But try not to be a smart ass next time, I'm sure you didn't know everything when you started programming either.
I got the decryption algorithm though... 
[twitter.png](https://xentaxbackup.github.io/file/10994_twitter.png)
## Post #22
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2016-06-02T10:44:28+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Oh sorry that was not for you xD 
I was trying to port a library for my toolkit(libkirk) and had issues w/ it
I made this port in few hours, I didn't even looked at it when I posted this tweet lol
Tho I DID got mad w/ your code at a point b\c windows is just not constant(the binary
file mode) but you have a constant code style w/ spaces instead of tabs and not lines over
80 chars(just issues w/ the trailing) so tbh it was not bad coded, just few part you were missing
man doc AND windows was missing smartness
## Post #23
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-06-02T11:15:58+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Don't worry, It just seemed coincidental that you ported my code to windows close to the day you posted your tweet

Also I haven't programmed in C in a few years, so I've forgotten a lot of windows specific code
I used C to make the code portable because i'm using Swift at the moment, which only compiles for Mac and Linux
## Post #24
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2016-06-02T12:03:48+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Never used Swift and don't think I'm going to use it soon, kinda old school while talking about languages
(Let's say I surely will not use perl, rails or Go before a while while I'm using Vim Script and editing w/ Neovim :p)

As for portable code I can't blame you, windows is shit and it will stay shit for cross compilation, it deprecates libs
to make """safer""" one, changing names, is the only OS non POSIX-compliant, have its own different integration for about
all and is just badly designed. I can't tell you how much cross compiling can be a pain in the ass sometimes T_T.

As for the rest surely won't work on khux anyways, on other projects and I'm not really hot to work on the kh scene before
a while(I'm already working w/ skynism to make this anyways: [https://www.youtube.com/watch?v=55p8NWp ... tml5=False](https://www.youtube.com/watch?v=55p8NWpLWuQ&nohtml5=False)
old trailer but tbh the best one we've produced, for specs game has been in RMXP, completely in reprogrammation w/ [http://godotengine.org/](http://godotengine.org/)
I made a custom engine out of this and will surely last for next projects, point is it's easy to use even for non devs and way better than unity/UE while
beeing free and open source(I'm kinda a libre fag on that point). By this I meant design, as for the "non dev" you still require a bit of knowledge but not
much, and UI for anims, maps and stuff we made is just awesome.)

So yeah not sure I'll fix any tools more unless someone pokes me but at least you have this one. Will post the repacker when I'll feel like it
(Might sounds like an ass but eh pretty sure it's buggy, we didn't tested it yet after all)
## Post #25
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-06-02T15:52:23+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Thanks for compiling and fixing the windows version GovanifY, you are a godsend.

There is some really interesting stuff in there, unfortunately I can't open any image file. Since the game apparently uses lwf all images should be either lossless png or gif, but that's not the case here, instead the header contains "btf" which I couldn't find any information about that would make sense.

Are they encrypted again?

The files in the attachments should be the same, one is from the browser version, the other from the unpacked Unchained archive, both have the same file name.
[AG_0000_00_00_obj1.zip](https://xentaxbackup.github.io/file/10999_AG_0000_00_00_obj1.zip)
## Post #26
- Username: jacoblumbos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 16, 2016 1:21 pm
- Post datetime: 2016-06-16T06:02:03+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Did you guys ever figure this out? I know the .lwf file refers to [http://gree.github.io/lwf/](http://gree.github.io/lwf/) **NOT** LuraWave image files. So a lot of the animations are made that way (and the game itself is Cocos2D). But I wasn't sure how to view the individual .png files even knowing this...
## Post #27
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-06-16T18:31:15+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

The btf format is most likely linked to Cocos2D, there are some bits to be found in the shared library "libcocos2dcpp.so" in the apk file, but I'm not sure that's helpful. I had no luck opening it with Cocos either.
## Post #28
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-06-29T18:45:58+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

> Reply from stellarren21
>
> You should understand one most important thing right here that 'Kingdom Hearts Unchained' uses these two different gameplay elements:
1st) misc.mp4
2nd) misc.png
Therefore, whenever there is any kind of update then Sizes of original files get enlarged and even sometimes post-installation processes even make your files look even bigger.
That's literally in the OP but thanks I guess.

I fiddled around with Cocos some more, but I can't seem to find such an optional image format. So it's probably built on top, most likely another encryption since compression wouldn't make that much sense for png files (at least I think so).
## Post #29
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-08-07T17:09:01+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Okay so thanks to your amazing work, I've created a SaveFile Extractor. You grab your "Cocos2dxPrefsFile.xml" from your device and place it with the tool, then you run it and the tool will convert the save into a decoded BGAD file. (There are other tools to extract each BGAD alone as well).

Note that you can't modify the save and repack it with this tool, as to what I've understood that it's against the rules of this site.

You will need khuxdecrypt. Link to the tool on my [GitHub Here.](https://github.com/thethiny/Modding-Database/tree/master/KHUx/SaveExtractor)
## Post #30
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-08-08T09:50:13+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Thanks for the tool thethiny, being able to back up your savedata manually is always nice.

In other news reddit user ebaroni83 found out how the so-called PNG files are structured: [https://www.reddit.com/r/KingdomHearts/ ... ta_in_png/](https://www.reddit.com/r/KingdomHearts/comments/4wn0ir/khux_all_medals_currently_in_khux_na_data_in_png/)

The custom header contains the image's width at 0x12 and height at 0x16 while the body of the image (starting at 0x26) is compressed with zlib and consists of a "non-compliant bitmap", as he puts it, which has to be flipped horizontally & vertically and the red & blue color channel have to be switched as well to get the correct result.
## Post #31
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-08-08T22:50:32+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

> Reply from Azurfan
>
> Thanks for the tool thethiny, being able to back up your savedata manually is always nice.

In other news reddit user ebaroni83 found out how the so-called PNG files are structured: https://www.reddit.com/r/KingdomHearts/ ... ta_in_png/

The custom header contains the image's width at 0x12 and height at 0x16 while the body of the image (starting at 0x26) is compressed with zlib and consists of a "non-compliant bitmap", as he puts it, which has to be flipped horizontally & vertically and the red & blue color channel have to be switched as well to get the correct result.
You're welcome ^_^

Edit: I've released a tool that converts the PNGs to BMPs, R/B Issue fixed along with upside down images.
[https://github.com/thethiny/Modding-Dat ... Ux/PNG2BMP](https://github.com/thethiny/Modding-Database/tree/master/KHUx/PNG2BMP)
## Post #32
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-08-09T06:43:34+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Tremendous work thethiny, the converter works really well.
## Post #33
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-08-09T07:30:43+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

I'm really glad it does 
Some images won't convert well, all you have to do is open them with a Hex editor and you're gonna find 0x20 somewhere after FF FF replace it with 0x04.
## Post #34
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-08-11T10:36:43+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

I hadn't any problems with that yet but I've noticed that there are many 4Byte files all around the extracted archives which seem to have the correct file name but not even the beginning of a header and then there are files which seem to be prematurely cut off, but these are far less common. This happens for audio, graphic and text files so maybe there is still some kind of file structure in there that gets in the way of the extraction process.
## Post #35
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-08-11T21:27:05+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

What do you mean exactly? I know that there are very short files which my tool automatically excludes. I think they're headers only and their files are somewhere else. Or they're some sort of counter.
## Post #36
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-08-13T20:19:44+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

It's not your tool that is causing the problem, it already exists after using MayBeePah's khuxdecrypt. Maybe that's a problem on my end but from the roughly 186,000 files that can be extracted from the newest Japanese version around 83,400 are only 4 byte large and headerless despite having a seemingly correct file name. The last two bytes for these files are either 00 00 or FF FF.
## Post #37
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2016-09-09T04:30:04+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

I hope this isn't too much of a necro...

I'm looking for a way to extract the data of the game, such as the avatar parts, keyblades, medal icons etc. Is this at all possible? 

Anyways, thanks for reading!  

EDIT

Solution found! Thanks to thethiny for all the help!
## Post #38
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-09-16T20:48:19+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

> Reply from MayBeePah
>
> Sorry, I've been busy and I forgot to work on Unchained.
I haven't got time at the moment to continue but here's the decryption algorithm if anyone wants to try:
Code: Select all#define BGADMagic 0x44414742

Hi again all 
Based on MayBeePah's code for Decrypting the files, I reverse engineered it and now I made a tool to RePack!
[https://github.com/thethiny/Modding-Dat ... HUxEncrypt](https://github.com/thethiny/Modding-Database/tree/master/KHUx/KHUxEncrypt)
It handles single BGADs, so if you have a BGAD with loads of file, then you will need to manually inject the BGAD back. I still don't know how the png table works, so for now use this tool and make sure that the file sizes remain the same! If it's larger, shrink it. If it's smaller, fill it with Stub Zeros. For the PNG files you will need the MD5 hash of the file which is easy, just extract the BGAD then use HxD to get the MD5 hash and store it in a file and add it back to the PNG. This tool is most useful for the banner files (/data/data/com.square_enix.android_googleplay.khuxww/cache/).

Enjoy 


Edit: I've also updated my tool to allow for even more PNG files to be converted.
## Post #39
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-10-13T13:25:14+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

It's seems the file format was changed, at least for the JP version.

[http://sabercathost.com/H57/2016101305.mp4](http://sabercathost.com/H57/2016101305.mp4)
## Post #40
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-10-14T10:21:13+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

> Reply from Azurfan
>
> It's seems the file format was changed, at least for the JP version.

http://sabercathost.com/H57/2016101305.mp4

The game can load both the previous files and the new files, which means that there's something somewhere that tells the game which method to use to read the names. It has to be in the files themselves.
## Post #41
- Username: nmylogan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 15, 2016 1:41 pm
- Post datetime: 2016-11-15T05:45:31+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

sorry to revive an old topic but is there a way for a layman to use or learn this? maybe a video I could follow to get this working?
## Post #42
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-01-19T04:19:41+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

The new toolsets are now available to download at my github.
[https://github.com/thethiny/Modding-Dat ... /DecryptV2](https://github.com/thethiny/Modding-Database/tree/master/KHUx/DecryptV2) - January 19 2017
## Post #43
- Username: Aredo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 21, 2010 11:42 pm
- Post datetime: 2017-01-28T09:51:12+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Hi, just checked khuxDecryptV2. It can't decrypt *.jpg files in "files/m" folder. I tried on versions of archives from current verison ( 1.2.3 ) of the game. 
Can you please check the decryption of those files? Was the decryption algorithm different before? Or is it different for "mp4" and "jpg"?
By the way, "/files/r/misc.mp4" is decrypted ok.
## Post #44
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-01-28T11:39:15+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Give me time and I'll try. I upgraded to Android 7.1.1 so I can't play anymore.
## Post #45
- Username: Aredo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 21, 2010 11:42 pm
- Post datetime: 2017-01-28T11:59:28+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Ok, thank you for fast answer. I'll wait for update from your side.
## Post #46
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-01-28T12:04:20+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Will do.
## Post #47
- Username: jacoblumbos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 16, 2016 1:21 pm
- Post datetime: 2017-06-27T20:40:51+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

With the recent update, seems we're back to square one :^) Anyone given this a shot lately? Would love to hear some thoughts
## Post #48
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2017-06-30T21:51:06+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

This is getting ridiculous, maybe we should wait until the game shuts down and then take a look at it again.
## Post #49
- Username: jacoblumbos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 16, 2016 1:21 pm
- Post datetime: 2017-07-30T18:23:43+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

Any luck?
## Post #50
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2017-08-29T19:58:55+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

So, the decryptor and extractor software works but I have a question, is it at all possible to have the software output the files from the misc.mp4 file in their folder structure with their listed file names? I mainly ask because im curious to see how the glowing keyblades are set up in terms of their effects and layering, I know they are layered images with some UV scroll and particle effects but im HOPING to be able to understand them enough to re-create them so we have animated GIF's for the KHUx Wiki Keyblades page.
## Post #51
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2017-09-09T09:09:59+00:00
- Post Title: Re: [Mobile] Kingdom Hearts Unchained file archives

The original browser game used swf files which allowed conversation to swf more easily, the mobile port on the other hand uses lwf, leightweight swf.

I packed all files that could be extracted with folders before update 2.0: [http://www49.zippyshare.com/v/uAqUWxSU/file.html](http://www49.zippyshare.com/v/uAqUWxSU/file.html)

The images have yet to be converted, but most of them probably won't since the current method is more trial and error.
