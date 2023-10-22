## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-12-21T13:33:59+00:00
- Post Title: luaexpose (3D visualiser)

I know there are many programs which allow model data to be visualized (such as Neosis/python) but I found it took too long to get a basic 3D scene setup if you wanted to mess around with any model data.

Take [this tutorial](http://forum.xentax.com/viewtopic.php?f=29&t=3739) on getting vertex data onscreen. The tutorial may be a little outdated but to even see vertex data you needed to be quite specific.

Anyway, luaexpose is something I've been working on for a few days. It lacks a lot of functionality at the moment, but it makes my point.

It's not ready for download yet, but take a look at the project here: [https://github.com/x1nixmzeng/luaexpose/](https://github.com/x1nixmzeng/luaexpose/)

I posted here because I would love some thoughts or feedback from XeNTaX   

Thanks!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-12-21T13:41:26+00:00
- Post Title: luaexpose (3D visualiser)

I missed one of the main features, so allow this double post to explain it.

Your scripts are automatically reloaded into the program if you save the Lua script file again.

To explore possible 3D vertex data in an unknown model, your script might look something like:

```

function main()
	io.write(file, " has been loaded!\n")
	io.write("It is ", size(), " bytes in size!\n")

	seek(1024)
	vertCount = u32:read() -- reads a single u32 value
	for v=1,vertCount do
		xyz = f32:read(3) -- read 12 bytes as floats
		pushVtx( x[1], y[2], z[3] )
		u32:skip(5) -- skip 20 bytes (5 integers)
	end
end

```
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-12-21T21:35:32+00:00
- Post Title: luaexpose (3D visualiser)

That's cool, and I don't mean to detract from your efforts, but is that really any less complicated than this? 

```
import noesis
import rapi
def registerNoesisTypes():
	handle = noesis.register("Some format", ".someformat")
	noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
	noesis.setHandlerLoadModel(handle, loadSomeFormat)
	return 1
	
def loadSomeFormat(data, mdlList):
	bs = NoeBitStream(data)
	ctx = rapi.rpgCreateContext()
	vcount = bs.readInt()
	rapi.immBegin(noesis.RPGEO_TRIANGLE)
	for i in range(0, vcount):
		rapi.immVertex3([bs.readFloat(), bs.readFloat(), bs.readFloat()])
		bs.seek(20, NOESEEK_REL)
	rapi.immEnd()
	mdlList.append(rapi.rpgConstructModel())
	return 1

```

Noesis also already has all kinds of options for plugin/script reload shortcuts, and you can use tool scripts instead of format scripts if you prefer to just perform automated parsing and loading of a format. Maybe the problem is not so much that it's complicated as people aren't aware of how to use it.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-12-21T22:42:56+00:00
- Post Title: luaexpose (3D visualiser)

I think you may be right - I was put off Neosis by the need to register a file format first, I wasn't aware of the reload capabilities.

Maybe I should have made this a feature request   Being able to automatically run a format script on data (real-time reloading after the script has been updated) would be really cool.
