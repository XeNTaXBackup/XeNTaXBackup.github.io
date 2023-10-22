## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2018-09-12T13:45:04+00:00
- Post Title: The Incredibles anim import and Export everything

Hi, i want to get access to all the files to do with the incredibles game. all of it, called anim. the thing is i typed in animationRange = interval 0 and i don't
know what's next after interval 0 and before animationRange = interval 0 so if you can complete the script by comparing these ones with these massive kilobyte 
file size that it goes up to this is the only one of them have. that it goes up to. so if someone can write the script for me a completed one. to do with all the structures
the thing is i'm not very good of doing this so i need help please.
i need a rollout to this so can you complete it.

```
(
	button btn2 "Import anim" pos:[38,17] width:79 height:26
	button btn16 "Export anim" pos:[40,54] width:74 height:25

	on btn2 pressed do
	(
		fname = getopenfilename caption:"Read anim File" types:"anim File (*.anim)|*.anim|"
			if fname != undefined then (
				f = fopen fname "rb"
				
				
				animationRange = interval 0
				
				if f == undefined then ( Messagebox "Can't open the file!" title:"I/O Error" )
			)
			fclose f
			gc()
		)
	on btn16 pressed  do
(
	fname = getsavefilename caption:"Read anim File" types:"anim File (*.anim)|*.anim|"
		if fname != undefined then (
			f = fopen fname "rb"
			
			animationRange = interval 0
			
			if f == undefined then ( Messagebox "Can't save the file!" title:"I/O Error" )
		)
		fclose f
		gc()
	)
)
CreateDialog unnamedRollout
```

[Character Models.zip](https://xentaxbackup.github.io/file/14839_Character Models.zip)
