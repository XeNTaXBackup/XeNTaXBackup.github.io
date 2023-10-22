## Post #1
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-09-21T20:14:19+00:00
- Post Title: Free Realms DME format

I guess the DME files (header DMOD) contain the model data.

I see some things at the end of the file that look like uncompressed vertex lists but I'm unable to find handy stuff like size/number-of-variables to make sense of the whole thing... Anybody more experienced wants to take a crack at it?

Here are a bunch of DME files of different sizes as sample: [http://www.filefactory.com/file/a0a76f3 ... ms_dme_rar](http://www.filefactory.com/file/a0a76f3/n/freerealms_dme_rar) 

Thanks!
## Post #2
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-09-25T12:45:37+00:00
- Post Title: Free Realms DME format

> Reply from Zipslow
>
> I guess the DME files (header DMOD) contain the model data.

I see some things at the end of the file that look like uncompressed vertex lists but I'm unable to find handy stuff like size/number-of-variables to make sense of the whole thing... Anybody more experienced wants to take a crack at it?

Here are a bunch of DME files of different sizes as sample: http://www.filefactory.com/file/a0a76f3 ... ms_dme_rar 

Thanks!

Nobody interested or is it too difficult?
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-09-26T17:10:59+00:00
- Post Title: Free Realms DME format

Oh, no.. Did you think for that ?  

[http://web.t-online.hu/karpo/dme_to_obj.zip](http://web.t-online.hu/karpo/dme_to_obj.zip)
## Post #4
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-09-27T15:45:03+00:00
- Post Title: Free Realms DME format

Nice work 

Is it an existing format? Or can you post your format findings?

Maybe with some more digging the normals and UVs can also be found...

> Reply from Karpati
>
> Oh, no.. Did you think for that ?  

http://web.t-online.hu/karpo/dme_to_obj.zip
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-10-04T07:17:13+00:00
- Post Title: Free Realms DME format

Here is my version of the format! 

char[4]		headerID	//DMOD
dword		version
dword		ofsMesh
char[4]		MaterialID??	//DMAT
dword		??		//always 1
dword		cLen
char[cLen]	texString	//conatins Texture names
...

right in the ofsMesh
dword		??
dword		??
dword		??
float_6		BBox
dword		??
dword		??
dword		??
dword		??
dword		??
dword		VTsize
dword		numVert
dword		FaceType??
dword		numFaceIndices
struct Vert {
 float_3	coordXYZ
 float_3	normalXYZ
 *byte_4	boneID		//only on skinned models
 *float_3	weight		//??with -ve value??
}
struct face {
 word_3		index123
}

and some meshes might have another part of face and might even use triangle-strips as well!

Good Luck!
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-08-28T18:48:30+00:00
- Post Title: Free Realms DME format

Zipslow,

Can you tell me how can I extract the Assets_000.dat - Assets_005.dat files ?

I received any information now about the vertex structures and I would like to test it.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-28T23:12:13+00:00
- Post Title: Free Realms DME format

2 year topic. Think he's still around?
## Post #8
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-29T02:36:43+00:00
- Post Title: Free Realms DME format

LOL, do you really have to reply, why not let him do what he wants?
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-09-10T15:34:15+00:00
- Post Title: Free Realms DME format

Zipslow,

I released the 3D Object Converter v4.80 full/portable and update package now (with the improved .dme loader module).

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…).
