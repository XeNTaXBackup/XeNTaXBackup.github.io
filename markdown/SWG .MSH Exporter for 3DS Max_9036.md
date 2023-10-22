## Post #1
- Username: arkanic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 22, 2012 7:42 am
- Post datetime: 2012-06-04T19:16:49+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

I recently found a script by fatduck [download/file.php?id=1203](http://forum.xentax.com/download/file.php?id=1203) that imports .msh files into 3d max and I would like to be able to reverse it so I can export models into .msh.  I'm a noob when it comes to maxscript, so I just wrote a simple script to export the model data from 3ds max. Problem is the data I imported does not match the data I exported. So if someone could tell me that I am doing x wrong, or that I need to do the y to complete the conversion, that would be very helpful. Thanks.

My code

```
 --GUI-- 
 spinner fscale "Scale : " fieldwidth:60 range:[0.001, 1000, 1]
 button expMSH "Export   MSH" width:150 Height:25 align:#center
 label lbl1 ""
 label lbl2 "Based off Fatduck Importer" align:#right
 
 on expMSH pressed do ( 
  fname = getSaveFileName caption:"Select Star Wars Galaxies Model file" types:"MSH File (*.msh)|*.msh|All Files (*.*)|*.*|" 
  if fname != undefined then (
      f = createfile fname
      close f
      stream = fopen fname "wb"
	  
	  for iObIndex = 1 to $objects.count do (
		obj = selection
		tmesh = snapshotAsMesh selection[1]
		num_faces = getNumFaces tmesh
		  vertDupx = #(5.2)
		  vertDupy = #(5.2)
		  vertDupz = #(5.2)
		  for f=1 to num_faces do(
			  faceVertIndex = getFace tmesh f
			  tVertIndex = getTVFace tmesh f
			  for i=1 to 3 do(
				  check = false
				  vpos = getVert tmesh faceVertIndex[i]
				  for leng = 1 to vertDupx.count do (
					  if ((vpos.x == vertDupx[leng]) and (vpos.y == vertDupy[leng]) and (vpos.z == vertDupz[leng])) then (
						  check = true
						  continue
					  )
				  )
				  if (not check) then (
					  append vertDupx vpos.x
					  append vertDupy vpos.y
					  append vertDupz vpos.z
					  
					  writeFloat stream vpos.x
					  writeFloat stream vpos.y
					  writeFloat stream vpos.z
								  
					  normals = getNormal tmesh faceVertIndex[i]
					  n1 = sqrt(normals.x^2 + normals.y^2 + normals.z^2)
					  
					  if (n1 == 0) then (
						  nx = 0
						  ny = 0
						  nz = 0
					  ) else (
						nx = (normals.x/n1)
						ny = (normals.y/n1)
						nz = (normals.z/n1)
					  )
					  writeFloat stream nx
					  writeFloat stream ny
					  WriteFloat stream nz
					  
					  vuvpos = getTVert tmesh tVertIndex[i]
					  writeFloat stream vuvpos.x
					  writeFloat stream vuvpos.y
				  )
			  )
		  )
		  
	  )
	  fclose stream
	  
  )--end if fname
 )--end on impMGN
 
)--end rollout SWG_roll


floater = newRolloutFloater "Star Wars Galaxies" 200 175 10 70
addRollout SWG_roll floater
```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-04T20:48:24+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

Just pastebin it or something.
I'm not downloading a file to see a script.
## Post #3
- Username: arkanic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 22, 2012 7:42 am
- Post datetime: 2012-06-05T00:08:21+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

Ok, I pastebin the import script
[http://pastebin.com/UuEskqAv](http://pastebin.com/UuEskqAv)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-05T05:05:04+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

The data your write out definitely would be different from the original format because you don't seem to be writing out the file the way it is read.

A complete import script can simply be flipped around to become a complete export script, writing the same data at the same places.

For example, I'm looking at the import script and see a lot of different cases for the different vertex formats but it doesn't seem like you're writing that information out in your export script.

Similarly, there are a lot of other pieces of data that are read to check which branch to execute, but you haven't included those in your export script either.

```
  FCary = #()
  datasize = readInvLong f
  numIndex = readlong f
  sizeElement = datasize / numIndex
  for i = 1 to (numIndex/3) do (
   if sizeElement == 2 then (
    f1 = 1 + (readshort f #unsigned)
    f2 = 1 + (readshort f #unsigned)
    f3 = 1 + (readshort f #unsigned)
   ) else if sizeElement == 4 then (
    f1 = 1 + (readlong f #unsigned)
    f2 = 1 + (readlong f #unsigned)
    f3 = 1 + (readlong f #unsigned)
   ) else messagebox "error in face index"
   append FCary [f1,f2,f3]
  )
  return FCary
 )

```


You should be doing something similar here as well in your export script, except instead of reading you're writing.

I'm not sure where you are writing out the face indices either.
## Post #5
- Username: arkanic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 22, 2012 7:42 am
- Post datetime: 2012-06-05T16:15:05+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

I didn't think I could just flip it around, but will give that a shot. Thanks
## Post #6
- Username: arkanic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 22, 2012 7:42 am
- Post datetime: 2012-06-10T01:44:42+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

I've got quite a bit of the basics completed but am mainly having trouble with two things right now. If someone could help me figure them out, that would be great.

My normals do not match up. Sometimes they are flipped, most of the time they are missing or way out of place. 


```
		vpos = getVert tmesh f
		append vertArray [vpos.x, vpos.z, -vpos.y]
		normals = getNormal tmesh f
		append normArray [normals.x, normals.z, -normals.y]
		uvpos = getTVert tmesh f
		uvY = uvpos.y
		append uvArray [uvpos.x, (uvY-1) * -1]
		--find min and max points for the bounding boxes
		if f == 1 or vpos.x > maxX then (maxX = vpos.x)
		if f == 1 or vpos.x < minX then (minX = vpos.x)
		if f == 1 or vpos.z > maxY then (maxY = vpos.z)
		if f == 1 or vpos.z < minY then (minY = vpos.z)
		if f == 1 or (-vpos.y) > maxZ then (maxZ = -vpos.y)
		if f == 1 or (-vpos.y) < minZ then (minZ = -vpos.y)
	)
```


The second being the spherical bounding box radius. Whatever I am doing to compute this is wrong. The center is correct and so are the max and min points, but the radius is either to small or to large.

```
	difY = maxY - minY
	difZ = maxZ - minZ
	writeFloat stream (maxX - difX/2)
	writeFloat stream (maxY - difY/2)
	writeFloat stream (maxZ - difZ/2)
	absX = abs(difX) -- calculate radius
	absY = abs(difY)
	absZ = abs(difZ)
	if absX > absY and absX > absZ then (
		writeFloat stream (absX*0.625)
	) else if absY > absX and absY > absZ then (
		writeFloat stream (absY*0.625)
	) else (
		writeFloat stream (absZ*0.625)
	)
```
## Post #7
- Username: arkanic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 22, 2012 7:42 am
- Post datetime: 2012-06-10T04:05:38+00:00
- Post Title: SWG .MSH Exporter for 3DS Max

Here is some raw data comparisions from a file that I imported and then exported without making any changes. Vertex points and UV points are a perfect match, but the normals are off on every axis.

```
VX:  79 B0 45 30     79 B0 45 30      
VY:  9A 99 79 3F     9A 99 79 3F      
VZ:  7D 56 74 BD     7D 56 74 BD
NX:  0B EE 0B 3E     74 3D 32 B3
NY:  5E EA 2D BD     F8 8F 2F BD
NZ:  91 5D 7D BF     C6 C3 7F BF
U:   00 00 00 3E     00 00 00 3E
V:   00 D8 72 3A     00 D8 72 3A
```
