## Post #1
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2020-09-21T13:46:21+00:00
- Post Title: Help with the Smackdown VS RAW Series Collision (PS2)

I am trying to decode the collision files from the game SVR. Those games use the HMD format. 
Here is an example data: 
- Each collision has 0x60 bytes block each and is a float (except the last 4 bytes at the end which is the binary flag of the collision object)
Here are the properties of the collision of the game.
+ Collisions are one-sided, for example, you can't walk through the barricade to go out of bound, but when you are out of bound you can just walk through the barricade in the other side to go inbound again
+ Collisions seem to ignore the Z position, I set my wrestler at a very high attitude and he still can't go throught the object at a lower attitude than him which he can no longer touch.
+ However when the wrestlers get to the ramp because the ramp is higher near the stage our Z coordinate still get adds up correctly (!!!)
+ In this games they used XZY or YZX positions scheme, whatever it is the Z is always in the middle
+ Collisions format also handles 'respawn point', when I randomly tweak them around my characters got transported into different places randomly every seconds.
I try to picture collision as a structure of having (x_min, y_min) to (x_max, y_max), however this game's file storage just surprise me. There are 23 floats in the game resembling a matrix.
Here is the collision files for the barricade in the lower section of the arena. (I will upload picture later seems right now there is a javascript bug which prevents me to attach more than 1 file)

```
00 | 0.000000 -1.000000 0.000000 -67.999001,
10 | -0.000000 -0.000000 -1.000000 -67.998955,
20 | 1.000000 0.000000 -0.000000 0.000000,
30 | -0.000999 -67.999001 -82.000984 1.000000,
40 | 60.000000 -82.000000 -60.000000 -82.000000,
50 | -60.000000 82.000008 82.000000 0.000000

```

If we look at the data in the upper left it seems like a 3x3 rotation matrix.
I ran some debugging in the game and found some detail:
- This piece of data get read when my character begins at this position (we call this vf08)
vf08 = Vector4(-64.4989776611328, -3.50099992752075, 0.14, 1.0)
- The first 0x40 bytes are used for something that looks like some geometry math when my character steps in: (we assume ACC, vf04, and vf08 each is 4D vector having x,y,z,w as its 0x00,0x04,0x08,0x0C offset, we have a vector multiply with a float with multiple all of its x,y,z,w from this float. And we have vector addition which adds up their x,y,z,w with the other.
vf04 = 4 floats in the 1st row
vf05 = 4 floats in the 2nd row
vf06 = 4 floats in the 3rd row
vf07 = 4 floats in the 4th row
vf08 = wrestler position (x,y,z,w) with w = 1.0 all the time

```
ACC = ACC  + (vf05 * vf08.y)
ACC = ACC  + (vf06 * vf08.z)
vf12 = ACC + (vf07 * vf08.w)

```

After going through those operation vf12 is:
vf12 = Vector4(0.023880, -3.500022, -78.500002, 4624.930353)
then the w part is being assigned 1.0 in it
vf12 = Vector4(0.023880, -3.500022, -78.500002, 1.0)
Now the next part only the x and z part of the vf12 is used (0.023880 and -78.500002) and they are being assigned as f05 and f09.
This Python code return a boolean value on whether the current 0x60 collision elements should be read by the game or not, if I force it to return a 0 then all collisions will stop working.
so vector_c = [60.000000,-82.000000, -60.000000, -82.000000,-60.000000, 82.000008, 82.000000]

```
    f05 = vf12.x    
    f09 = vf12.z
    f12 = vector_c[1]
    f11 = vector_c[3]
    f04 = vector_c[2]
    f10 = vector_c[0]    
    f07 = vector_c[5]
    
    #print("f12: %.6f, f09: %.6f, f10: %.6f,\nf04: %.6f, f05: %.6f, f11: %.6f, f07: %.6f" % \
    #(f12, f09, f10, f04, f05, f11, f07))
    f01 = f09 - f12  
    #print("after 001092DC: f01: %f" % f01)
    f00 = f04 - f10 
    #print("after 001092E0: f00: %f" % f00)    
    ACC = f01 * f00
    #print("after 001092E4: ACC: %f" % ACC)    
    f00 = vector_c[4]    
    #print("after 001092E8: f00: %f" % (f00))
    f02 = f11 - f12
    #print("after 001092EC: f02: %f" % f02)        
    f03 = f05 - f10 
    #print("after 001092F0: f03: %f" % f03)        
    f13 = ACC - (f03*f02)    
    #print("after 001092F4: f13: %f" % f13)            
    f06 = f05               - f04 
    #print("after 001092F8: f06: %f" % f06)
    f01 = f00               - f04 
    #print("after 001092FC: f01: %f" % f01)
    f03 = f05               - f00 
    #print("after 00109300: f03: %f" % f03)
    f04 = f09               - f11
    #print("after 00109304: f04: %f" % f04)
    ACC = f04 * f01
    #print("after 00109308: ACC: %f" % ACC)
    f05 = f07               - f11
    #print("after 0010930C: f05: %f" % f05)
    f08 = 0.0
    f00 = f10               - f00 
    f01 = f09               - f07 
    #print("0010931C: ACC: %f, f06: %f, f05: %f" % (ACC, f06, f05))    
    f04 = ACC - (f06*f05)
    #print("f04: %f" % f04)
    f02 = f12               - f07 
    ACC = f01*f00
    f01 = ACC - (f03*f02)
    if (f13 >= 0 and f04 < 0) or (f13 >= 0 and f01 < 0) or f13 < 0:
        if f13 > 0:
            print("1.", f13)
            return 0
        elif f04 > 0:
            print("2.", f04)         
            return 0
        elif f01 > 0:
            print("3.", f01)
            return 0   
        else:
            print("4. ")
            return 1
    elif f13 >= 0 and f01 >= 0:
        print("5. ")
        return 1
    print("6. ")
    return 0

```

Why do I call this checksum? Because this is like the optimization made by a game developer, if the wrestler is standing far enough then it will not read the collision files, saving processing speed, however when I force them all to 1 collision stills work. In fact if I just return 1 at this function right 
before it starts the collision still works normally. So they are like the data necessary for checking if the collision is valid or not
The problem is that I have no idea what those operations could mean. Even though when standing at that spot I got a 'true' values on the "4. " codepath.
Also the developers made it (on purpose?) so that when you change a single values of those 23 floats the collision block will stop working. Which prevents me from changing one of them and figure out each properties.
If anyone know how to decode these data I would be very appreciated
Attached below is a collision file for all of the arena in the RAW Arena. Unfortunately I can't seem to add the picture to better illustrate my problem due to having a Javascript bug
[03E7.hmd.txt.zip](https://xentaxbackup.github.io/file/18773_03E7.hmd.txt.zip)
