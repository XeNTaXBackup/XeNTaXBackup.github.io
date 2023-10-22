## Post #1
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2009-01-06T15:31:41+00:00
- Post Title: Buzz TEX files

Hi, i want to change some images in the game "Buzz Master Quiz". I think i´ve located the TEX files where those images are.

Those TEX files appears to be Zlib compressed, so i uncompress one but i dont know what kind of data is stored. Any help will be appreciated
[TEX.zip](https://xentaxbackup.github.io/file/1801_TEX.zip)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2009-01-06T18:35:59+00:00
- Post Title: Buzz TEX files

8-Bit Bitmap without header. the first 1024 bytes contains 256 Palette entries.
after that is pixeldata in 256x256 resolution. I could easly make a Converter for these types of files.
## Post #3
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2009-01-10T12:24:29+00:00
- Post Title: Buzz TEX files

Thanks Strobe. If you could code a tool, i would be grateful for
## Post #4
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2009-01-19T03:40:04+00:00
- Post Title: Buzz TEX files

If you still need this, I've made one for you.

1. Download Wombat Game Tools from [http://www.szevvy.com/download/wombat-1.0a-setup.exe](http://www.szevvy.com/download/wombat-1.0a-setup.exe)
2. Notice it doesn't create a Start Menu icon - only just noticed this, sorry.  The default install folder is c:\Program Files\Wombat.  Go there, go into the viewers folder, and create a file called "Buzz Master Quiz.viewer.txt" (without quotes, of course)
3. Open that file, and paste the following script into it:

```

file name = "*.tex" is (
	compressed zlib

	palette RGBA

	image VGA (
		width: 256
		height: 256
	)
)
```

4. Fire up Wombat, load up as many tex files as you want, and export away.

One thing to note is that transparency doesn't work yet - indexed images don't support 8-bit alpha yet.  I'll try to fix this up ASAP.

The script also relies on the textures being compressed - if you've gone ahead and decompressed them, remove the "compressed ZLIB" line from the script.

If you give me the format of the packed file from whence you got the tex files, I'd be happy to update the script to handle the packed files as well.  Ket me know how it goes.
## Post #5
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2009-01-19T18:44:42+00:00
- Post Title: Buzz TEX files

Thank you very much szevvy, it works fine!



One question; every TEX files have the same first 16 bytes "54455800000100000001000005400000"

To view the images, i have to open every TEX with a HEX editor, remove this 16 bytes and save them. Any chance to automatice with Wombat?

And the top question: how can i replace those images?  
[00001295.rar](https://xentaxbackup.github.io/file/1831_00001295.rar)
## Post #6
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2009-01-20T01:47:56+00:00
- Post Title: Buzz TEX files

Change the script to

```

file name = "*.tex" is (
   data(16) unknown

   compressedData zlib[bytesRemaining] (
      palette RGBA

      image VGA (
         width: 256
         height: 256
      )
   )
)
```
 so you don't have to get rid of the first 16 bytes.  You can't replace at the moment, sorry - Wombat doesn't support any sort of modification.  It's a plan for the future, if I have some spare time I might be able to code you up a tool to covert images back to TEX.
