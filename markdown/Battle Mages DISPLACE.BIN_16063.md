## Post #1
- Username: ermaccer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 25, 2016 4:14 am
- Post datetime: 2017-03-28T13:10:18+00:00
- Post Title: Battle Mages DISPLACE.BIN

The most i could decode of it:


Seems to be some float array.
[displace.zip](https://xentaxbackup.github.io/file/12708_displace.zip)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-04-05T00:22:00+00:00
- Post Title: Battle Mages DISPLACE.BIN

Hi, the file is not a usual image file. It's an array of 128 x 128 floating point numbers (IEEE 754).

I see 3 possibilites here for converting the .bin files into a format that you can work with.

1) Convert it to an 8-bit grayscale bitmap. Pros: you can edit it with many programs, cons: you would lose precision.
The minimum value in displace.bin is 193.0 the maximum is 759.0, for a grayscale bitmap, the values need to streteched so they fit into a [0,255] interval. This leads to a loss in precision.

2) Convert it to a 16-bit grayscale bitmap. Pros: No precision loss, cons: you need a program that can handle 16-bit images.

3) Convert it to an .OBJ file. Pros: No precision loss, cons: you need a 3D program to edit the file.

Here's the file converted to a 8-bit grayscale bmp:



displace_193_759.bmp (17.05 KiB) Viewed 42 times
## Post #3
- Username: ermaccer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 25, 2016 4:14 am
- Post datetime: 2017-04-05T20:48:23+00:00
- Post Title: Battle Mages DISPLACE.BIN

Thanks.
How did you generate it?
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-04-05T23:25:37+00:00
- Post Title: Battle Mages DISPLACE.BIN

I used MATLAB to convert the binary file into an image.
Don't know if that's the best method, but here's the code I used:

```
file = fopen('displace.bin');

% read content of file into a 128x128 float matrix
A = fread(file, [128,128], 'float');

% transpose matrix
A = A';

% close file
fclose(file);

% get minimum and maximum value
amin = min(min(A));
amax = max(max(A));

% convert matrix to grayscale image
I = mat2gray(A, [amin amax]);

% convert image to 16-bit, without the conversion the output image would only be 8-bit
I =  uint16(I * 65535);

% show image in Matlab
imshow(I);

% write image to file
imwrite(I, 'displace.png');
```
