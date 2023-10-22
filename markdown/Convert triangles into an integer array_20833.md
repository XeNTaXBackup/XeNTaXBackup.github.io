## Post #1
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2019-07-19T16:06:28+00:00
- Post Title: Convert triangles into an integer array

Convert triangles to an integer array

We have this array of integer:

```

```

Using code we can transfer it into array of triangles:

```

```

- The code works like this:
+ Item 0: The first 3 items are in 
[27,68,72]
f1 = 27, f2=68,f3=72

Everytime
f1 = f2 = 68
f2 = f3 = 72
+ Item 1: Replace f3 with the next item of the integer list
f1 = 68, f2=72,f3=74
[[27, 68, 72], [68, 72, 74]
f1 = f2 = 72
f2 = f3 = 74
+ Item 2 and on: Just replace f3 with the next item of the integer list, and shift f2 to f1 and f3 to f2

*** What we want is to convert the triangle array back into an integer array
*** However, Blender gives us the triangle array that might not follow the rule of the integer unpacking, user might edit and alert the triangle array so we can't depend on the unpacking rule of the array and we need to convert that triangle array to integer array.
*** If not possible, split them in group
For example
[[4,5,9], [5,9,6], [3,8,2]]
the third items cannot be fit into the integer array, so they will be move into another group
we will get 2 group
group 0: [4,5,9,6]
group 1: [3,8,2]
My current algorithm is like this:
Turn the 3D array into a dict with 2D keys
{4: [[5,9]], 5: [[4,9] , [9,6]], 6: [[5,9]], 9: [[4,5], [5,6]], 3: [[8,2]], 8: [3,2], 2:[[8,3]]}

We will get the first key 4 and write out the 3 items in position 0
[4, 5, 9]
next we will decide if we want to use 5 or 9, this part I don't know how to efficient pick choose the next key to follow. 
+ Path 1: In this sitation I will go first with 5
[[4,9], [9,6]], since 4 and 9 is already in the list we will skip it, we get [9,6] , 9 is already in so we pick 6
our output will be
[4,5,9,6]
+ Path 2: I will go with 9
in 9 we get [[4,5], [5,6]]
Using the same procedure we will get
[4,5,9,6]
* In this case we can choose either one, my algorithm is programmed to select the list with the highest length

Problem with my algorithm:
- It is dependent on the position, it has to be exactly unpacked the way I said above.
- It cannot work on the integer array which has duplicates since I have coded it to ignore duplicate
[27, 68, 72, 74, 76, 96, 114, 113, 64, 9, 98, 0, 20, 106, 1, 128, 86, 32, 131, 53, 58, 1, 121, 49, 143, 99, 62, 28, 26, 7, 76, 71, 44, 146, 18, 68, 42, 135, 154, 156, 70, 24, 5]
You can see in this array the number 1 appears in 2 places. - I don't know how to specify the end condition, I would go on until I meet a key with only 1 element of 2D arrays. However not all situation works with this condition. Especially when multiple groups are involved
- It seems wasteful and redundant way to use data structure.
Example Blender data:

```

```

If anyone can help me or can tell me what this problem is called and how can I search for it I would be appreciated.
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-21T08:00:09+00:00
- Post Title: Convert triangles into an integer array

What you are talking is converting stripped indices into a triangle array and back.
Converting stripped triangles to triangles is easy, but it's much harder to do the other way.

Here is a theory behind it: [http://www.learnopengles.com/tag/triangle-strips/](http://www.learnopengles.com/tag/triangle-strips/)
And here is a library written in C++ that I use: [https://github.com/spoonless/tristripper](https://github.com/spoonless/tristripper)

Also you didn't wrote, what format are you using to store these values.
int is 32bit, and is never used to store index data, unless its an very old non-standard format.
API's supports int index buffers, however this does not mean it should be used.
## Post #3
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2019-07-21T15:23:53+00:00
- Post Title: Convert triangles into an integer array

I sort of solved the problem.
It turns out that Blender sorts the triangles in the right order that I want for converting it back into an integer array
For example:
[0]: 0,1, 2,
[1]: 1,2,3
[2]: 4,2,3,
[3]: 4,6,7
[4]: 6,7,9
I take the first 3 items 0,1,2 into the list
list = [0,1,2]
So
last_f1 = 0
last_f2 = 1
last_f3 = 2
Now for the next items, we will see if it contains at least 2 vertices of the last processed , so
if at least 2 items in (f1,f2,f3) is in (last_f1,last_f2, last_f3)
so 0,1,2 we see 1 = last_f2, 2 = last_f3 so list = [0,1,2,3]
then 
last_f1 = 1
last_f2 = 2
last_f3 = 3
...
Keep doing that we get 
[0,1,2,3,4] after processing index 2
So the algorithm keeps running in a loop and now the same process but the function will starts at index 3
So the function returns new_int_array, next_index
If there is no more items to read,next_index = -1 and specify the stop condition

So I got
[0,1,2,3,4]
[4,6,7,9]
as output

And about data type, I have been using to python so it is not necessary to define a type for that. But it uses 32bit integer. The game I am working for pack the triangles as integer array , and each integer in the array also comes with 2D UV coordinate. It uses non-standard format for sure but I have solved that problem as well.
