## Post #1
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-12T00:25:08+00:00
- Post Title: Loading texture files in Noesis (possible bug?)

So I just learned about the method loadExternalTex, which according to Noesis readme file: "returns a NoeTexture, or None if the texture could not be found." And for its arguments it says it accepts a string as "name/path of texture, without extension."

I'm not sure if I found a bug or something but the only way I can get this function to work is if the texture file is in the same folder as the main file registered with Noesis for previewing (usually a mesh file).

For example, if I'm using Noesis to load some model/mesh at "c:\dir1\dir2\polygon.mesh", and this model requires two textures which are located at "c:\dir1\dir2\tex1.dds", and "c:\dir1\dirA\dirB\tex2.dds",
The following call works and returns a NoeTexture object:
rapi.loadExternalTex("c:\\dir1\\dir2\\tex1")
But the following call mysteriously fails and returns None:
rapi.loadExternalTex("c:\\dir1\\dirA\\dirB\\tex2")

Both files exist, the only difference is that the latter is not in the same folder as the mesh file. If this function can only accept files in the same folder then why does it say it can accept a path in the readme file? Is this a bug or am I missing something here? Can somebody maybe double-check this?

Edit: I forgot to mention I'm of course using the latest version of Noesis (v4.177)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-06-12T18:44:26+00:00
- Post Title: Loading texture files in Noesis (possible bug?)

there is an example of using this correctly in my star wars scripts.
[viewtopic.php?f=16&t=8714](http://forum.xentax.com/viewtopic.php?f=16&t=8714)
## Post #3
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-12T21:46:08+00:00
- Post Title: Loading texture files in Noesis (possible bug?)

That's a great example, which I might have to use if loadExternalTex is in fact broken (as far as I know, loadExternalTex was added to avoid having to parse texture file headers manually). If I'm correct, in that example you are parsing the texture's header to then construct your NoeTexture object? I was hoping I could avoid parsing the texture file's header by just using loadExternalTex. It works fantastic for textures in the same directory but I just can't figure out why it is failing to work with other paths.
## Post #4
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-13T19:18:24+00:00
- Post Title: Loading texture files in Noesis (possible bug?)

I seem to have found a solution for this so I thought I would share it just in case someone else gets the same problem. Apparently loadExternalTex is picky with the path string it receives. I was constructing the path string using '\\' as the directory separator character, and then I was obtaining the absolute path by using os.path.abspath(texPath). I'm not sure which of the two was the problem but I got it to work by using '/' instead of '\\' (works fine under Windows OS's), and also stopped using absolute path and instead made relative paths. I think the latter was the problem.

So for example, if I'm using Noesis to load some model/mesh at "c:\dir1\dir2\polygon.mesh", and this model requires two textures which are located at "c:\dir1\dir2\tex1.dds", and "c:\dir1\dirA\dirB\tex2.dds", then the following calls will work and returns a NoeTexture object:
rapi.loadExternalTex("tex1")
rapi.loadExternalTex("../dirA/dirB/tex2")

Now back to trying to get my key-framed animations to work (sigh)
## Post #5
- Username: errno
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-06-13T21:37:47+00:00
- Post Title: Loading texture files in Noesis (possible bug?)

yeah you can see in the script 
texName = texName.replace("\\","/")
also you can use load by handler

```
		folderName = rapi.getDirForFilePath(rapi.getInputName())
		folderName = folderName.replace('\\', '/')
		folderName = (folderName + "../../../../")
		if (rapi.checkFileExists(folderName + texName)):
			texData = rapi.loadIntoByteArray(folderName + texName)
			texture = rapi.loadTexByHandler(texData, ".dds")
			texture.name = rapi.getExtensionlessName(rapi.getLocalFileName(texName))
			self.texList.append(texture)

```
