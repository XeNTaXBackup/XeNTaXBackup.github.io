## Post #1
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2012-03-14T10:00:19+00:00
- Post Title: Array element operation in 3dsmax.

Hi,There is a problem in maxscript.I remember Chrrox told to me about this.
for example, I set an empty array to store some vertex count,,they are random integers,like
50,35,21,,
I set empty array as vertcount_array = #()
after reading vertex count from file,I store those value into array
like 
v1= 50 
append vertcount_array[v1,0],,,,,etc.
okay,,up to now,,all working fine,but when i need to use these values,the problem comes.
like ,,
vert_counter = vert[1][1]
then maxscript listener told me  
-- Type error: Call needs function or class, got: undefined
even i use
vert_counter = vert[1][1] as integer

it still shows the same error
Is there any trick or other syntex of array to solve this?thx~:)
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-03-14T22:30:03+00:00
- Post Title: Array element operation in 3dsmax.

Check the following link -- [http://www.kxcad.net/autodesk/Autodesk_ ... Values.htm](http://www.kxcad.net/autodesk/Autodesk_MAXScript_Reference_9/Array_Values.htm)

Your syntax is incorrect when you are assigning values to and reading the values from the array.

If you provide a larger snippet of your code I may be able to help more, but from what you have there now I am unable to determine what you are trying to accomplish.

MDA
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T01:16:17+00:00
- Post Title: Array element operation in 3dsmax.

I think he is just trying to index into the array.

Or, maybe he's trying to work with a n-by-2 array (eg: append vertcount_array[v1,0])
## Post #4
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-03-15T01:58:31+00:00
- Post Title: Array element operation in 3dsmax.

Don't take this the wrong way, but I can see from your post, you're not sure either   which is why I ask for more info.

MDA
## Post #5
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2012-03-15T04:48:23+00:00
- Post Title: Array element operation in 3dsmax.

Thx for your link MichaelDarkAngel
My script is not finish yet,,just meet this problem again.So i ask here to see if anyone else meet this kind of trouble and have their solution.
I read maxscript help before asking here.
The problem is solved for now.
I use another trick to prevent using array operation in this case.
like using a for loop directly to read those vertex counts,(actually they're face index number in a strip array)
But this problem do happen,,try read some integer values and store them into maxscript's array.
after storing them,,maxscript seems to judge those values as floats automatically.
When you need to use these value and retrieve them from array,,then undefined error happens sometimes..

finale00,,plz check your pm,,i've some information for your project.
## Post #6
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-03-15T06:16:55+00:00
- Post Title: Array element operation in 3dsmax.

> Reply from falconcool
>
> But this problem do happen,,try read some integer values and store them into maxscript's array.
after storing them,,maxscript seems to judge those values as floats automatically.
When you need to use these value and retrieve them from array,,then undefined error happens sometimes..

Just some general help that may be useful

Pre-defining your variables before attempting to assign a value to your variable should solve the undefined error (ex. var a = 0)

MaxScript arrays are single-dimension arrays.  In order to have a multi-dimensional array you need to nest one array inside another array (ex. myArray = #(#(0, 0, 0), #(1, 1, 1), #(2, 3, 4)).
myArray[1][1] would equal 0
myArray[2][2] would equal 1
myArray[3][3] would equal 4

An array in MaxScript is an ordered collection of values. Each element in the array can contain any type of value (ex. myArray = #(1, "string", a * 0.5))

Hope that helps

MDA
