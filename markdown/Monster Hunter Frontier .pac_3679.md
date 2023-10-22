## Post #1
- Username: xhugox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 29, 2009 5:50 am
- Post datetime: 2009-08-29T00:26:37+00:00
- Post Title: Monster Hunter Frontier *.pac

Hello guys, 
I'm atm working on a translation for Monster Hunter Frontier. In order to do this I had to free the game executeables from ASProtect, well this worked pretty well and now I have all files prepared to reverse the game's file formats. Monster Hunter Frontier has been produced by Capcom and then sold to Hangame a korean F2P game hoster.

The game has a launcher (mhf.exe) which contains GameGuard (already killed) and launches the game's dlls, there is a mhl.dll (MonsterHunterLauncher), which is some sort of GUI for the users with which he can configure grafical options etc. and login his character. The mhl.dll induces the launch of the mhfo.dll (MonsterHunterFrontierOnline), this dll contains all functions needed for game play.
(Including reading files, loading them into memory etc.)

I used exestringz to get all strings existing in the dll, you can examine them in the sample I uploaded to netload. Futhermore I used this python snippet;

```

def main(args):
    f = file(args[0], 'rb').read()
    size = len(f)

    i = 0
    while i < size:
        try:
            de = zlib.decompress(f[i:])
        except zlib.error:
            i += 1
            continue

        print 'Found a compressed block starting at', i

        i += 1

if __name__=='__main__':
    sys.exit(main(sys.argv[1:]))

```


It reports that there are few blocks compressed with zlib, however, these zlib blocks do only begin to appear at offset 267780d (st001.pac), so I do not know what the first bytes suppose to mean. 

Well, my questions are;

How can I find the decompress/decryption routine using a debugger? I tried to bp on ReadFile but I was not able to detect the decompress routine.
Is there any other way to find out how the file has been compressed? I already searched for strings in the *.pac files but did not find anything.

Please have a look at the st001.pac file, if needed I can provide you with 309 more samples. 

The game can be downloaded at [http://mhfdown.hangame.com/pub/PUBMHF/F ... l_v812.exe](http://mhfdown.hangame.com/pub/PUBMHF/FullPackage/Live/MHF_Setup_Full_v812.exe)

If somebody who looks into this needs the unpacked exe/dll files just pm me I will send them to you. The reason I do not want to make them public is that somebody could use them to cheat at this game (since GameGuard is removed etc.) and this is not something I want.

Thanks for your time.

Here is the sample: [http://netload.in/dateiACAN63XDLn/Sample.rar.htm](http://netload.in/dateiACAN63XDLn/Sample.rar.htm)
## Post #2
- Username: iceS
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-04T00:09:06+00:00
- Post Title: Monster Hunter Frontier *.pac

you should just post them anyway because if someone has the skill to write a gg emulator for this game they could unpack this game themselves anyway.
## Post #3
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-09-04T09:00:41+00:00
- Post Title: Monster Hunter Frontier *.pac

What are you planning to do with them anyways?
st001.pac contains 24 png images and the model(s) they are for I think, same with all other pac files I looked through.
I'd like to have those models though...
## Post #4
- Username: xhugox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-05T00:09:06+00:00
- Post Title: Monster Hunter Frontier *.pac

If I really wanted to unpack the exe I am sure I could find it floating around the internet somewhere.
I will do some scans on the exe and see if I can't find the unpack function to be able to extract the pac files.
## Post #5
- Username: xhugox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 29, 2009 5:50 am
- Post datetime: 2009-09-05T02:23:58+00:00
- Post Title: Monster Hunter Frontier *.pac

The files are asprotect packed, I will send the unpacked executeables to you via pm, thanks for taking your time and having a look at it. 

mhl.dll makes a short crc of all executeables (Only CreateFile Calls), mhfo.dll read all necessary game files.
## Post #6
- Username: xhugox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 29, 2009 5:50 am
- Post datetime: 2009-09-06T16:05:20+00:00
- Post Title: Monster Hunter Frontier *.pac

UPDATE:

The *.snd files at \Capcom\Monster Hunter Frontier Online\dat\sound are uncompressed *.ogg files.

.txb files also seem to be uncompressed (except the zlib compressed pictures in the file)

> st001.pac contains 24 png images and the model(s) they are for I think, same with all other pac files I looked through.
>
> I'd like to have those models though...

Why do you think this? I could not find any signs proving this...

> you should just post them anyway because if someone has the skill to write a gg emulator for this game they could unpack this game themselves anyway.

I'm not certain how GameGuard works, but since the executeable is unpacked, they are able to modify the program before GameGuard loads, right?
## Post #7
- Username: xhugox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-06T19:33:54+00:00
- Post Title: Monster Hunter Frontier *.pac

the pac and image containers you mentioned can be unpacked with a simple script like this

get files long
get NAME filename
for i = 0 < files
math counter += 1
string NAME += COUNTER
get OFFSET long
get SIZE long
log name offset size
next i
then just add the extension of the file normally png or jkr files to the end.
the bin files that start with ecd seem to just be some wierd or encrpted format but does not seem compressed
something like

idstring "ecd\ 1a"
get files long
get NAME filename
for i = 0 < files
math counter += 1
string NAME += COUNTER
get SIZE long
savepos offset
log name offset size
math OFFSET += size
goto OFFSET
next i
## Post #8
- Username: xhugox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 29, 2009 5:50 am
- Post datetime: 2009-09-07T08:36:18+00:00
- Post Title: Monster Hunter Frontier *.pac

I thank you very much for the solution, however, I'm quite more interested into the way you found this out.
Did you search and found the decode function in the executeables, or did you find it out another way?

Please tell me.
## Post #9
- Username: xhugox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-07T15:04:45+00:00
- Post Title: Monster Hunter Frontier *.pac

The file table starts at the begging of the file so it was not very hard to just experiment with these few values to see what did what.
it was already stated that there were png files inside the archives so it was a simple search for PNG lead me to their offsets and then I could verify this worked with the file table offsets.
## Post #10
- Username: xhugox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 29, 2009 5:50 am
- Post datetime: 2009-09-08T17:47:42+00:00
- Post Title: Monster Hunter Frontier *.pac

Since QuickBMS creates many files with a wierd file extension, I wrote a Java Snippet which changes all files in a specific directory to x.extension. Please make sure, that there is no directory in the specified folder.

```
import java.io.IOException;

public class dateinam {
	public static void main(String[] argv) throws IOException {
		String Ordner = new String("D:/Your/Folder/Path/x80/");
		File folder = new File(Ordner);
		File[] listfiles = folder.listFiles();
		for (int i = 0; i < listfiles.length; i++) {
			String foo = new String(Ordner + i + ".extension");
			System.out.println(foo);
			listfiles[i].renameTo(new File(foo));
		}
	}
}

```
## Post #11
- Username: tastyxentax
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 01, 2012 4:03 am
- Post datetime: 2012-11-01T02:37:32+00:00
- Post Title: Monster Hunter Frontier *.pac

Hi. I've been lurking, since this morning, and decided to join the forum and pay the admission fee. 

I'm hoping you can help me. I'm trying to access the textures from Monster Hunter Frontier.

Do I need to bypass GameGuard, as did xhugox to get at the textures?
I tried QuickBMS script cchrox included in his post, but ended up with a zero byte file:

```
get NAME filename
for i = 0 < files
math counter += 1
string NAME += COUNTER
get OFFSET long
get SIZE long
log name offset size
next i
```


```
------------------------------
  e8930004 1554426    st001.pac1

Error: incomplete input file number 0, can't read 1048576 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted
```


I'm pretty new to this. I successfully extracted the textures and such from the psp version of MHF2 using [https://github.com/codestation/mhtools](https://github.com/codestation/mhtools) 
I'm needed higher resolution textures than the psp provides.
I've tried the PS3 version of Monster Hunter Portable HD, but apparently its encrypted, and not possible [viewtopic.php?f=21&t=7244](http://forum.xentax.com/viewtopic.php?f=21&t=7244)

As you can see, i've spent a bit of timing at this. I'm pretty much out of ideas, and looking for help from you guys.
## Post #12
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2023-04-28T05:53:44+00:00
- Post Title: Monster Hunter Frontier *.pac

Hey, sorry to necro an old thread, but I have the same problem as the user above.

```
- open script E:\Downloads\quickbms\mhf.bms
- set output folder J:\Monster

  offset   filesize   filename
--------------------------------------
  e09a0004 3568733    em001_b-hd.pac1

Error: incomplete input file 0: I:\MHFCT4.1\dat\emmodel-hd\em001_b-hd.pac
       Can't read 524288 bytes from offset e09a0004.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0     0%   12         3568749    . offset e09a0004

Last script line before the error or that produced the error:
  8   log name offset size

- OFFSET       0xe09a0004
- SIZE         0x0036745d
  coverage file 0     0%   12         3568749    . offset e09a0004

Press ENTER or close the window to quit
```


```
get NAME filename
for i = 0 < files
math counter += 1
string NAME += COUNTER
get OFFSET long
get SIZE long
log name offset size
next i
```


I think I'm supposed to append file extension, right? But where and how?
## Post #13
- Username: monuneha
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 15, 2023 3:07 am
- Post datetime: 2023-10-14T19:30:57+00:00
- Post Title: Monster Hunter Frontier *.pac

Yes, you're correct. To resolve the issue, you should append the appropriate file extension to the file names. In your script, you can modify the log command to include the desired file extension. Assuming the files are of a specific format like .png, .jpg, or .txt, you can append the corresponding file extension. For example

```
get NAME filename
for i = 0 < files
    math counter += 1
    string NAME += COUNTER
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i

```


Assuming the files are of the PNG format, your script could be modified like this

```
get NAME filename
for i = 0 < files
    math counter += 1
    string NAME += COUNTER
    get OFFSET long
    get SIZE long
    string NAME += ".png"
    log NAME OFFSET SIZE
next i

```
