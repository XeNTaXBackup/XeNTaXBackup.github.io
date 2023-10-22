## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-19T08:57:41+00:00
- Post Title: i3d (xml) to obj

here's a short&tiny crash course on
how to convert i3ds from Farming Simulator into wavefront objs.

(There might be other and better i3d importers but this approach should help you to do it on your own).
The proceeding is a little bit awkward so feel free to code your own i3d_2obj convertor...  

This is the i3d version I tested
<?xml version="1.0" encoding="iso-8859-1"?>
<i3D name="scaniaR730_TOPLINE" version="1.6" 

(remark: uvs not handled, from the following line I would guess it's the two values after t0: tx ty
<v p="-0.158791 0.180895 -0.00998497" n="0 1.07405e-007 -1" t0="0.538085 0.65077"/>)

open i3d with a text editor
search for 'vertices count'
search for '/Triangles'
copy/paste the lines between these two into a new text file

do some text replacements: (without ')

```
'" n="' -> ' # n="' (normals commented out, blank before # is important)
```

comment out
      </Vertices>
      <Triangles count="2104">
by adding a preceding #

replace

```
'"/>' -> nothing
```

save the text file as an *.obj file

one problem left:

face indices start from 0 but for wavefront obj they are required to start from 1 
so copy the f 0 1 2 lines into a new file faceind.txt and use IncFaceInd.exe on it.

Reimport the contents of the created faceind_out.txt back into your obj (overwriting the existing f - lines)

this is the code for IncFaceInd (to be compiled as console application):

```
#include <windows.h>
#include <conio.h>
#include <stdio.h>

using namespace std;

bool inc_faceInd()
{
	FILE * stream, * stream1 ;  // resulting file is faceind_out.txt

	BYTE wahl= 0 ;		        // 0,1,2: faces, vertices, uvs?
	char ch ;
	int a,b,c ;

    stream = fopen( "faceind_out.txt", "w" );
    if( stream == NULL ) {
        printf("<faceind_out.txt> open error!\n") ;
        return (FALSE) ;
    }
	switch (wahl) {
		case 0: stream1 = fopen( "faceindices.txt", "r" ); break ;
	}
	if( stream1 == NULL ) {
		printf(" The file faceindices.txt could not be opened!\n");
		//chMB(" The file faceindices.txt could not be opened!\n");
		fclose (stream) ;
		return (FALSE) ;
	}

	while (fscanf( stream1, "%c", &ch ) != EOF)	{
        if (ch != 'f') {
            printf(" expected 'f' at linestart!\n>>> break\n");
            fclose (stream) ; fclose (stream1) ;
            return false ;
        }
	fscanf( stream1, "%d %d %d ", &a,&b,&c) ;
        fprintf(stream, "f %d %d %d\n", a+1,b+1,c+1) ;
	}
	fclose (stream) ; fclose (stream1) ;
	return true ;
}

int main()
{
    char ch ;

    //cout << "Hello world!" << endl;
    printf("<faceindices.txt> must exist in exe folder.\n") ;
    printf(" format: f 0 1 2\n") ;
    if (inc_faceInd()) printf("\n faceind_out.txt was created.\n") ;
    printf("\n Press any key ") ;
    ch= _getch() ;
    return 0;
}
```


the result:



wheel.jpg (153.36 KiB) Viewed 110 times
