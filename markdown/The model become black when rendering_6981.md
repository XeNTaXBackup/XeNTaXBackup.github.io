## Post #1
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-16T04:34:15+00:00
- Post Title: The model become black when rendering

I try to search on the forum but i dont know what exactly my problem, so i decided to post new thread. If forum already had same topic with me, i apologize :shrug: 
This is some picture of my problem :

This is original picture of model when i view on 3ds max (after i have checked "2 sided" on all texture)

 

This is the picture of model when i render =>>> the model become black (you can see some line of the model). I tried to remove texture from the model, and i got the same result =>>> the texture did not cause problem.

 

I tried to create the sky light and omi  light, i can see the model, but the color of model change to the color of skylight and omi light (ex : when i set sky light to white =>> the model become bright)

 

Anyone can tell me how to fix it ? Thank in advanced  

The model i have attached below


 Kanji.rar
(180.27 KiB) Downloaded 21 times
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-16T05:30:03+00:00
- Post Title: The model become black when rendering

here we go, google is your friend.

[http://www.google.com.ar/search?sclient ... tnG=Buscar](http://www.google.com.ar/search?sclient=psy&hl=es&site=&source=hp&q=how+fix+black+render+in+3d+max&btnG=Buscar)

[http://www.skyscrapercity.com/showthread.php?t=490617](http://www.skyscrapercity.com/showthread.php?t=490617)
[http://forums.tutorialized.com/3ds-max- ... -7307.html](http://forums.tutorialized.com/3ds-max-71/3ds-max-rendering-problem-7307.html)
[http://www.secondpicture.com/tutorials/ ... s_max.html](http://www.secondpicture.com/tutorials/3d/mental_ray_in_3ds_max.html)
[http://www.polycount.com/forum/showthread.php?t=77931](http://www.polycount.com/forum/showthread.php?t=77931)
## Post #3
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-07-16T05:43:23+00:00
- Post Title: The model become black when rendering

Material Editor -> Submaterial -> Maps -> Diffuse Color Map -> Bitmap Parameters -> Alpha Source -> None (Opaque).
Check in all submaterials. Also check "2-Sided".
## Post #4
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-16T09:37:20+00:00
- Post Title: The model become black when rendering

@CriticalError : thank you for the link   

@Nazaroff : it 's work ^^. Thank you so much, but i must use "light" to show the model correctly.
