## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-13T03:58:38+00:00
- Post Title: Fable Texture Help (Xbox)

Was wondering if anyone would be willing to take a look at the first chunk of this image stream. Seems to be split into a High & Low resolution file. The low is easy to pull from this file. For this one it will be DXT1 128x128 for the low. The high should be 256 x 256 I'd think.

Anyways I've included the entire stream as well as the post header if anyone would be kind enough to look at it. The image stream seems to have a header where first 2 bytes will give a value that is 5 bytes less than value I have down below for offset.

\Dev\BBBProjects\ReleaseBranch\Fable\Resources\art3\Regions\ Bowerstone\Villagers\Texture_Special\Bard_face_24.tga
2200
0000
0001 
0001 
0000
0001
0001
0100
1800 -1800 After examining multiple files determined (1800 = DXT1 & 1900 = DXT3)
0000
0007
4401
0080
0000 -watch for value 
186C -Offset of low resolution in file

Any help would be appreciated, or a simple smack upside the head or anything else.

Sorry did a Yousendit link for file 
[http://s51.yousendit.com/d.aspx?id=060U ... X49ICMO4CK](http://s51.yousendit.com/d.aspx?id=060US8JFW4RC12PHX49ICMO4CK)
## Post #2
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-04-13T04:43:47+00:00
- Post Title: Fable Texture Help (Xbox)

Yes this is a problem from Fable for xbox.

The Archive was wierdly built and is similar to the catwoman pcs archive I saw on here some time ago. We're able to extract the files. But we have no idea what some of the data is. As the actual file headers have been stripped in favor of these post headers. And the files are stored as engine enums.

attached example archive of pixel and vertex shaders.

And the textures aren't tga. 
They included development names.
[XSHADERS.rar](https://xentaxbackup.github.io/file/174_XSHADERS.rar)
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-13T07:15:16+00:00
- Post Title: Fable Texture Help (Xbox)

DXT means they are DirextX .DDS files. These image files can contain multiple versions (resolutions) of the same image, for texture-mapping purposes. 

Read this:
[http://msdn.microsoft.com/library/defau ... extool.asp](http://msdn.microsoft.com/library/default.asp?url=/archive/en-us/directx9_c_Summer_03/directx/graphics/tools/dxtextool.asp)

For the format of the DDS files:
[http://msdn.microsoft.com/library/defau ... format.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/directx9_c/directx/graphics/reference/DDSFileReference/ddsfileformat.asp)

The tool is included in the DirectX SDK:
[http://www.microsoft.com/downloads/deta ... layLang=en](http://www.microsoft.com/downloads/details.aspx?FamilyID=4e825a37-0c94-4421-9ec8-156e52525d11&DisplayLang=en)

Get the Photoshop plugin to work with DDS files here:
[http://developer.nvidia.com/object/nv_t ... tools.html](http://developer.nvidia.com/object/nv_texture_tools.html)
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-13T08:00:54+00:00
- Post Title: Fable Texture Help (Xbox)

It seems the upper portion is mixed with something. I was just wondering if anyone had an idea. Here is example:

[http://img101.exs.cx/img101/7342/dragon02torso245qu.jpg](http://img101.exs.cx/img101/7342/dragon02torso245qu.jpg)    low res or mip map

[http://img101.exs.cx/img101/2376/hirestestcopy5hr.jpg](http://img101.exs.cx/img101/2376/hirestestcopy5hr.jpg)    upper portion with extra data in it. Photo was cleaned to show like data.

Any idea what would be causing this extra garbage was my question I guess.
## Post #5
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-04-13T08:16:33+00:00
- Post Title: Fable Texture Help (Xbox)

Here is an extracted file.

The data is in two sections. The second part is a standard DDS.

We can't find the format of the first part which we assume is hi-res.
[Texture_Stream.rar](https://xentaxbackup.github.io/file/175_Texture_Stream.rar)
## Post #6
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-05-05T00:11:29+00:00
- Post Title: Fable Texture Help (Xbox)

I guess I should of added that when I was messing with the level files some had non-dxt friendly dimensions. In the level mess archives I also discovered that the images for the mesh also resemble the hi-res textures. 

I'm not very much into textures and such, is it possible to have such a thing? Perhaps an image format similar to dxt? Still clueless
## Post #7
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-07-16T16:59:59+00:00
- Post Title: Fable Texture Help (Xbox)

I guess the game dumps character Hi-res into dat files in the cache. It only does a few and mixes some of the textures. There are a few that don't get mixed at all.  Keshire also has good information that files are compressed. The archive itself is compressed with zlib but in the credits it also credits LZO.

[](http://img127.imageshack.us/my.php?image=testimportcopy4dx.jpg) This was file I grabbed out of the cache.

[](http://img127.imageshack.us/my.php?image=highstreamcopy1re.jpg)This is how file appears in archive. You can see tiny parts of data still there.

I downloaded a LZO compression program to see if I could get similar texture with a light lzo compression.
[](http://img127.imageshack.us/my.php?image=testimportlzo4fm.jpg)
It didn't turn out to be close to arhive texture. I know they have a few different LZO schemes.

I know trying to decompress archive file and testing would be easy. My programming skills still kind of suck, just wondering if I'm looking in the right direction or not.
## Post #8
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-03-13T05:09:09+00:00
- Post Title: Fable Texture Help (Xbox)

This has been resolved. 

[http://fabletlcmod.com/wiki/doku.php?id ... ormats:big](http://fabletlcmod.com/wiki/doku.php?id=file_formats:big)
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-13T08:40:58+00:00
- Post Title: Fable Texture Help (Xbox)

Thanks!
