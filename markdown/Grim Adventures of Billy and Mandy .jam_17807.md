## Post #1
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-11T12:47:37+00:00
- Post Title: Grim Adventures of Billy and Mandy .jam

I didn't give a great deal of research to this but I assume it's a container for character extents as it is chock full of information in text from shaders, bones, coordinates and all the typical settings one would find in a character container including particle emitters. Game is the Gamecube version and produced by High Voltage Software.

[https://onedrive.live.com/?authkey=%21A ... 051B80B2EF](https://onedrive.live.com/?authkey=%21AIGLqx2qruSGbVk&id=756B9A051B80B2EF%21687&cid=756B9A051B80B2EF)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T12:04:07+00:00
- Post Title: Grim Adventures of Billy and Mandy .jam

> Reply from SickAlice
>
> I didn't give a great deal of research to thisyeah. I know.   But don't expect others to do it, then.

There's interesting ASCII in the Billy.jam, though. Should not be too hard to transform it to smd or .x to get the skeleton:

```
LocalDrawingTransform[28]
CoordSys
{
	RotTransCoordSys "rootR"
	{
		Position -0.000000 -0.851551 19.275238
		Orientation 0.000000 0.000000 0.707106 0.707107
		LocalDrawingTransform 1.000000 0.000000 0.000000 0.000000  0.000000 1.000000 0.000000 0.000000  0.000000 0.000000 1.000000 0.000000  0.000000 0.000000 0.000000 1.000000
	}
	RotTransCoordSys "pelvisR"
	{
		Position -0.000000 0.000000 0.000000
		Orientation 0.499999 0.500000 0.500000 0.500001
		Parent "rootR"
		LocalDrawingTransform 0.000000 1.000000 -0.000001 0.000000  -0.000001 0.000001 1.000000 0.000000  1.000000 -0.000000 0.000001 0.000000  0.000000 0.000000 -0.000000 1.000000
	}
	RotTransCoordSys "rthighR"
	{
		Position 0.000013 -0.000013 -9.775564
		Orientation 0.049965 0.998473 -0.001178 -0.023537
		Parent "pelvisR"
		LocalDrawingTransform 0.099721 0.995004 -0.004704 0.000000  -0.047119 0.000000 -0.998889 0.000000  -0.993899 0.099832 0.046884 0.000000  -0.460615 -0.000000 -9.764707 1.000000
	}
	RotTransCoordSys "rcalfR"
	{
		Position 6.343868 -0.000000 0.000001
		Orientation 0.000000 0.000000 0.099832 0.995004
		Parent "rthighR"
		LocalDrawingTransform -0.099941 0.994982 -0.004704 0.000000  -0.046180 -0.009361 -0.998889 0.000000  -0.993921 -0.099613 0.046884 0.000000  -6.668849 -1.351827 -9.764709 1.000000
	}
	RotTransCoordSys "rfootR"
	{
		Position 8.023998 0.000000 -0.000001
		Orientation 0.003522 -0.023301 -0.049965 0.998473
		Parent "rcalfR"
		LocalDrawingTransform -0.000000 1.000000 0.000000 0.000000  -0.000000 0.000000 -1.000000 0.000000  -1.000000 0.000000 0.000000 0.000000  -14.280386 0.169311 -10.445029 1.000000
	}
	RotTransCoordSys "rtoeR"
	{
		Position 4.812387 6.846439 0.000000
		Orientation 0.000000 -0.000000 -0.707107 0.707107
		Parent "rfootR"
		LocalDrawingTransform 1.000000 0.000000 0.000000 0.000000  0.000000 0.000000 -1.000000 0.000000  -0.000000 1.000000 0.000000 0.000000  -6.677128 19.092777 -10.445030 1.000000
	}
	RotTransCoordSys "lthighR"
	{
		Position -0.000013 0.000014 9.775564
		Orientation 0.049965 0.998473 0.001177 0.023536
		Parent "pelvisR"
		LocalDrawingTransform 0.099721 0.995004 0.004704 0.000000  0.047119 0.000000 -0.998889 0.000000  -0.993899 0.099832 -0.046884 0.000000  -0.460615 -0.000002 9.764707 1.000000
	}
	RotTransCoordSys "lcalfR"
	{
		Position 6.343867 -0.000001 -0.000000
		Orientation 0.000000 -0.000000 0.099832 0.995004
		Parent "lthighR"
		LocalDrawingTransform -0.099941 0.994982 0.004704 0.000000  0.046180 0.009361 -0.998889 0.000000  -0.993921 -0.099613 -0.046884 0.000000  -6.668848 -1.351827 9.764707 1.000000
	}
	RotTransCoordSys "lfootR"
	{
		Position 8.023996 0.000001 0.000001
		Orientation -0.003522 0.023301 -0.049965 0.998473
		Parent "lcalfR"
		LocalDrawingTransform 0.000000 1.000000 0.000000 0.000000  -0.000000 0.000000 -1.000000 0.000000  -1.000000 -0.000000 0.000000 0.000000  -14.280383 0.169311 10.445026 1.000000
	}
	RotTransCoordSys "ltoeR"
	{
		Position 4.812387 6.846440 0.000002
		Orientation -0.000000 -0.000000 -0.707107 0.707107
		Parent "lfootR"
		LocalDrawingTransform 1.000000 0.000000 -0.000000 0.000000  -0.000000 -0.000000 -1.000000 0.000000  -0.000000 1.000000 -0.000000 0.000000  -6.677129 19.092770 10.445024 1.000000
	}
	RotTransCoordSys "spineR"
	{
		Position 7.723082 -0.016245 0.000010
		Orientation 0.000002 0.000001 -0.000398 1.000000
		Parent "pelvisR"
		LocalDrawingTransform 0.000796 1.000000 0.000003 0.000000  -0.000000 -0.000003 1.000000 0.000000  1.000000 -0.000796 -0.000000 0.000000  -7.723066 0.022395 0.000001 1.000000
	}
	RotTransCoordSys "ruparmR"
	{
		Position 14.368691 -1.035882 -24.280302
		Orientation 0.744994 -0.110538 -0.653319 0.077065
		Parent "spineR"
		LocalDrawingTransform -0.063909 -0.963896 0.258498 0.000000  -0.990475 0.029610 -0.134470 0.000000  0.121961 -0.264630 -0.956607 0.000000  -26.809986 5.562109 18.137981 1.000000
	}
	RotTransCoordSys "rforarmR"
	{
		Position 10.496004 0.000001 -0.000001
		Orientation -0.000000 -0.000000 0.021277 0.999774
		Parent "ruparmR"
		LocalDrawingTransform -0.022844 -0.965742 0.258498 0.000000  -0.990838 -0.012556 -0.134470 0.000000  0.133109 -0.259201 -0.956607 0.000000  -37.508854 3.969931 18.137985 1.000000
	}
	RotTransCoordSys "rhandR"
	{
		Position 4.606472 -0.000001 -0.000002
		Orientation -0.798992 -0.005915 -0.097785 0.593308
		Parent "rforarmR"
		LocalDrawingTransform -0.105012 0.533579 0.839206 0.000000  -0.993464 -0.018326 -0.112664 0.000000  -0.044736 -0.845552 0.532016 0.000000  -38.101891 20.531567 -15.657202 1.000000
	}
	RotTransCoordSys "rfingrR"
	{
		Position 7.433527 0.633179 -0.257910
		Orientation -0.000398 0.000000 0.000000 1.000000
		Parent "rhandR"
		LocalDrawingTransform -0.105012 0.534247 0.838780 0.000000  -0.993464 -0.018415 -0.112649 0.000000  -0.044736 -0.845128 0.532689 0.000000  -45.535419 19.886118 -15.415130 1.000000
	}
	RotTransCoordSys "rfingr1R"
	{
		Position 3.817261 -0.000002 -0.000000
		Orientation 0.000000 -0.000000 -0.087156 0.996195
		Parent "rfingrR"
		LocalDrawingTransform -0.010646 0.544366 0.838780 0.000000  -0.981569 0.154378 -0.112649 0.000000  -0.190811 -0.824520 0.532689 0.000000  -45.149712 28.154007 -15.415124 1.000000
	}
	RotTransCoordSys "rthumbR"
	{
		Position 3.264932 -0.060288 4.544804
		Orientation 0.507937 0.544896 0.399982 0.533951
		Parent "rhandR"
		LocalDrawingTransform 0.887718 -0.104863 0.448285 0.000000  -0.199297 -0.965280 0.168860 0.000000  0.415014 -0.239242 -0.877797 0.000000  -20.927341 -35.038082 29.626635 1.000000
	}
	RotTransCoordSys "rthumb1R"
	{
		Position 3.159058 0.000002 0.000002
		Orientation -0.000000 -0.000000 0.013849 0.999904
		Parent "rthumbR"
		LocalDrawingTransform 0.890282 -0.080236 0.448285 0.000000  -0.172486 -0.970430 0.168860 0.000000  0.421481 -0.227656 -0.877796 0.000000  -23.106749 -35.691738 29.626631 1.000000
	}
	RotTransCoordSys "luparmR"
	{
		Position 14.368691 -1.036016 24.280298
		Orientation 0.744994 -0.110540 0.653319 -0.077063
		Parent "spineR"
		LocalDrawingTransform -0.063910 -0.963895 -0.258498 0.000000  0.990475 -0.029610 -0.134470 0.000000  0.121961 -0.264630 0.956607 0.000000  -26.809986 5.562115 -18.137981 1.000000
	}
	RotTransCoordSys "lforarmR"
	{
		Position 10.495999 0.000000 0.000002
		Orientation 0.000000 -0.000000 0.021277 0.999774
		Parent "luparmR"
		LocalDrawingTransform -0.022844 -0.965742 -0.258498 0.000000  0.990838 0.012556 -0.134470 0.000000  0.133109 -0.259201 0.956607 0.000000  -37.508846 3.969937 -18.137985 1.000000
	}
	RotTransCoordSys "lhandR"
	{
		Position 4.606473 -0.000000 0.000000
		Orientation 0.798992 0.005915 -0.097785 0.593308
		Parent "lforarmR"
		LocalDrawingTransform -0.105013 0.533579 -0.839205 0.000000  0.993464 0.018326 -0.112664 0.000000  -0.044736 -0.845552 -0.532016 0.000000  -38.101891 20.531565 15.657206 1.000000
	}
	RotTransCoordSys "lfingrR"
	{
		Position 7.433530 0.633180 0.257909
		Orientation 0.000398 0.000000 0.000000 1.000000
		Parent "lhandR"
		LocalDrawingTransform -0.105013 0.534247 -0.838780 0.000000  0.993464 0.018416 -0.112649 0.000000  -0.044736 -0.845128 -0.532689 0.000000  -45.535427 19.886114 15.415137 1.000000
	}
	RotTransCoordSys "lfingr1R"
	{
		Position 3.817263 0.000002 0.000000
		Orientation 0.000000 -0.000000 -0.087156 0.996195
		Parent "lfingrR"
		LocalDrawingTransform -0.010646 0.544366 -0.838780 0.000000  0.981569 -0.154377 -0.112649 0.000000  -0.190811 -0.824520 -0.532689 0.000000  -45.149727 28.153997 15.415138 1.000000
	}
	RotTransCoordSys "lthumbR"
	{
		Position 3.264928 -0.060294 -4.544800
		Orientation -0.507937 -0.544896 0.399982 0.533951
		Parent "lhandR"
		LocalDrawingTransform 0.887718 -0.104863 -0.448285 0.000000  0.199297 0.965281 0.168860 0.000000  0.415014 -0.239242 0.877797 0.000000  -20.927347 -35.038090 -29.626635 1.000000
	}
	RotTransCoordSys "lthumb1R"
	{
		Position 3.159059 -0.000003 -0.000003
		Orientation 0.000000 0.000000 0.013849 0.999904
		Parent "lthumbR"
		LocalDrawingTransform 0.890282 -0.080236 -0.448285 0.000000  0.172486 0.970430 0.168860 0.000000  0.421481 -0.227656 0.877796 0.000000  -23.106749 -35.691742 -29.626627 1.000000
	}
	RotTransCoordSys "headR"
	{
		Position 15.397152 -0.294616 -0.000000
		Orientation -0.000000 -0.000000 0.000399 1.000000
		Parent "spineR"
		LocalDrawingTransform -0.000001 1.000000 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  1.000000 0.000001 0.000000 0.000000  -23.120462 0.298569 0.000001 1.000000
	}
	RotTransCoordSys "noseDR"
	{
		Position 26.893032 21.993504 0.000031
		Orientation 0.687352 -0.165975 0.687352 -0.165974
		Parent "headR"
		LocalDrawingTransform 0.000001 -0.889809 -0.456334 0.000000  1.000000 0.000001 0.000001 0.000000  -0.000000 -0.456334 0.889809 0.000000  -0.000002 42.127136 -34.602375 1.000000
	}
	RotTransCoordSys "brimR"
	{
		Position 56.720314 7.644106 0.000006
		Orientation -0.000000 0.000001 -0.418877 0.908043
		Parent "headR"
		LocalDrawingTransform 0.760715 0.649086 0.000002 0.000000  0.000000 -0.000003 1.000000 0.000000  0.649086 -0.760715 -0.000002 0.000000  -57.411297 55.968285 0.000173 1.000000
	}
}
```
Start building the hierarchy using the 'Parent' line.
## Post #3
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-18T15:56:53+00:00
- Post Title: Grim Adventures of Billy and Mandy .jam

No to be cheeky but I sort of thought this was a team effort and the understanding that time is limited is out? I mean I'm working on other things when available from other stuff in life is all, requested not expectation. And thanks but you know that isn't useful to me, nor is your scripting useful to most noobs, myself already telling you I'm weak in the coding department and struggling with polynomials as it is in school, round two in fact, and most are only at or about the level of modifying bms or py scripts. This kind of response was why I apologized in advance and have been so timid about even asking but I figured after giving it a go for a year on my own and hitting a wall there wasn't many other options. And tit for that if it displeases you you could always opt to not burden yourself with it? Either way it isn't really cool or entertaining to bag on people for having learning disorders. I just do try and do this to help out modders that made long standing requests, it isn't my job or something. This is a forum to ask for help in decoding game assets specifically is it not?
