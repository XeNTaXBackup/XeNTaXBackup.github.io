## Post #1
- Username: johnk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 03, 2019 2:14 am
- Post datetime: 2020-02-13T12:22:11+00:00
- Post Title: PES2014 Head Models [PS3]

Hi,

I'm trying to open the head & hair .model files from Pro Evo Soccer 2014 on the PS3 for editing but have had no success.

The PC versions have been successfully decrypted but the PS3 versions are a completely different structure.

If someone can have a look at the attached (same player in PC & PS3 versions) and help in any way, it would be hugely appreciated.

Thanks

link: [https://easyupload.io/juztis](https://easyupload.io/juztis)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-14T07:46:20+00:00
- Post Title: PES2014 Head Models [PS3]

Using AMR on \WE2014 PS3\2586\hair_high_win32.model



All 3 submeshes:


There're no polygon indices in the other 3 files while implicit indices don't work either.
## Post #3
- Username: johnk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 03, 2019 2:14 am
- Post datetime: 2020-02-14T08:44:25+00:00
- Post Title: PES2014 Head Models [PS3]

Thanks for looking into the models.

Are there any obvious changes that could be made to the other 3 models to make them work?

It is the heads in particular I’m needing.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-14T12:22:16+00:00
- Post Title: PES2014 Head Models [PS3]

> Reply from johnk ↑Fri Feb 14, 2020 4:44 pm at Fri Feb 14, 2020 4:44 pm
>
> 
Are there any obvious changes that could be made to the other 3 models to make them work?
Sadly there's not. But there's indeed some suspect data before the vertex section which probably is compressed since it'd be too short for that amount of vertices.
## Post #5
- Username: johnk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 03, 2019 2:14 am
- Post datetime: 2020-02-14T17:30:40+00:00
- Post Title: PES2014 Head Models [PS3]

There was some research done when the game first came out but I can't get in touch with the author.

The research related to the below models and they came up with these findings:

"I've found a lot of sections in the file, propably some face indices
But no profinite pointer to any vertex or uv data.
I've no experience of the past face files, so i really don't know what i am searching here.

With trial and error i think i've found the vertex offsets.
And there are 5 of them because of the 5 different face parts ( nose+mouth+cheeks, ears+neck, forehead and 2 parts for the eyes.

Here you can see the vertices and from what blender says (and of course if i've not made any massive mistake), there are 2253 of them."

[http://i250.photobucket.com/albums/gg26 ... c41ace.png](http://i250.photobucket.com/albums/gg264/arianos10/pes2014_face_zpse9c41ace.png)

[http://www.mediafire.com/download/q82dm ... /Faces.rar](http://www.mediafire.com/download/q82dm4szw5j57vf/Faces.rar)

I think if you are able to produce the point cloud on the problem files, I might be able to work with them.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-15T05:28:35+00:00
- Post Title: PES2014 Head Models [PS3]

> Reply from johnk ↑Sat Feb 15, 2020 1:30 am at Sat Feb 15, 2020 1:30 am
>
> 
I think if you are able to produce the point cloud on the problem files, I might be able to work with them.
Point cloud is not the real problem. Example on the decompressed data of face_high_ps3.model:


Piont cloud preview of all 4 objects:
## Post #7
- Username: johnk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 03, 2019 2:14 am
- Post datetime: 2020-02-17T11:47:03+00:00
- Post Title: PES2014 Head Models [PS3]

Thanks for the overview.

Are there any other settings you used to get the preview of all 4 objects as I can't seem to reproduce what you did?

The last bit of info I could find that could help with the normals is the following (not sure if it helps)...

"We can not see face index data clearly, firstly need to convert indices data to understandable format

http://s10.postimg.cc/voy2p0e9h/zzz11.jpg

http://s9.postimg.cc/n2ghauh4r/zzz2.jpg

can you see triangle indices right now ??"

In your opinion, what is the difference between the "face_edithair_high" & "face_high" models and the "hair_d" & "hair_high" models?

I'm also trying to understand the sturcture of the PC models I originally uploaded so if you could provide the normals & polygon indices addresses/counts for both the face & hair models, I would appreciate it. I think I found the position & texcoords addresses.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-17T13:09:22+00:00
- Post Title: PES2014 Head Models [PS3]

> Reply from johnk ↑Mon Feb 17, 2020 7:47 pm at Mon Feb 17, 2020 7:47 pm
>
> 
Are there any other settings you used to get the preview of all 4 objects as I can't seem to reproduce what you did?
No. I exported them and luanched the viewer outside AMR.

> Reply from johnk ↑Mon Feb 17, 2020 7:47 pm at Mon Feb 17, 2020 7:47 pm
>
> 
The last bit of info I could find that could help with the normals is the following (not sure if it helps)...

"We can not see face index data clearly, firstly need to convert indices data to understandable format

http://s10.postimg.cc/voy2p0e9h/zzz11.jpg

http://s9.postimg.cc/n2ghauh4r/zzz2.jpg

can you see triangle indices right now ??"
I don't see the connection between these two images. The data in the 1st pic seems to be half-float UVs. What does it have to do with Normals or indices?

> Reply from johnk ↑Mon Feb 17, 2020 7:47 pm at Mon Feb 17, 2020 7:47 pm
>
> 
In your opinion, what is the difference between the "face_edithair_high" & "face_high" models and the "hair_d" & "hair_high" models?
Frankly speaking, there's no difference in data structure among "face_edithair_high", "face_high" and  "hair_d" of the PS3 version. As for "hair_d" vs "hair_high":



Seems that "hair_d" is just a low level LOD of "hair_high".

> Reply from johnk ↑Mon Feb 17, 2020 7:47 pm at Mon Feb 17, 2020 7:47 pm
>
> 
I'm also trying to understand the sturcture of the PC models I originally uploaded so if you could provide the normals & polygon indices addresses/counts for both the face & hair models, I would appreciate it. I think I found the position & texcoords addresses.
face_high_win32.model




hair_high_win32.model
## Post #9
- Username: johnk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 03, 2019 2:14 am
- Post datetime: 2020-02-17T21:01:10+00:00
- Post Title: PES2014 Head Models [PS3]

> No. I exported them and luanched the viewer outside AMR.
How do you export submeshes from AMR without polygon indicies?

When I try to export, I get an error message "invalid polygon index count"
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-18T02:51:34+00:00
- Post Title: PES2014 Head Models [PS3]

> Reply from johnk ↑Tue Feb 18, 2020 5:01 am at Tue Feb 18, 2020 5:01 am
>
> How do you export submeshes from AMR without polygon indicies?
You can't. Just choose Triangle Strip and check the Implicit Storage. Then you can import the fbx into your 3d app and inspect it under the vertex level.
