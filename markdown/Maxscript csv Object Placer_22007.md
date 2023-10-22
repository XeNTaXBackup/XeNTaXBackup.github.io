## Post #1
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-14T02:44:36+00:00
- Post Title: Maxscript csv Object Placer

Looking for help, I have these maxscripts which I'd like to merge into one with a file selection instead of typing the file name.
I have this maxscript open file dialogue but I don't know how to link the other code to operate on the file.

```
types:"Data(*.csv)|*.csv|All|*.*|"
```


csv.txt

```
PreWarGrassClump01004,-77168.7031,91268.8828,7828.1479,-4.4434,-3.7479,318.1284,1.1000
```


```

adata = (dotnetClass "System.IO.File").ReadAllLines "E:csv.txt"

for i = 1 to adata.count do 
(
    pInfo = (filterString adata[i] "|")
    print pInfo
    s = sphere segments:(pInfo[6] as integer)
    s.radius = pInfo[2] as integer 
    s.pos = [pInfo[3] as integer,pInfo[4] as integer, pInfo[5] as integer]
    s.name = pInfo[1]
)
```


```
    file = memStreamMgr.openFile @"E:csv.txt"

    while NOT file.eos() do
    (
        local line = filterString (file.readLine()) ", "
        if line.count == 8 AND isValidNode (local obj = getNodeByName line[1]) do
            obj.scale = [line[8] as float, line[8] as float, line[8] as float]
    )
    memStreamMgr.close file
)
```


```
    file = memStreamMgr.openFile @"E:csv.txt"

    while NOT file.eos() do
    (
        local line = filterString (file.readLine()) ","
        if line.count == 8 AND isValidNode (local obj = getNodeByName line[1]) do
            obj.rotation = eulerAngles (line[5] as float) (line[6] as float) (line[7] as float)
    )
    memStreamMgr.close file
)
```


```
    file = memStreamMgr.openFile @"E:csv.txt"

    while NOT file.eos() do
    (
        local line = filterString (file.readLine()) ","
        if line.count == 8 AND isValidNode (local obj = getNodeByName line[1]) do
            obj.pos = [line[2] as float, line[3] as float, line[4] as float]
    )
    memStreamMgr.close file
)
```
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-19T14:07:43+00:00
- Post Title: Maxscript csv Object Placer

not sure if this is what your looking for? cause the code you posted are doing two separate things, one is creating a sphere, and the others are updating an object by name reference.

Didn't know what you wanted to this just creates a sphere

```
try(destroydialog pinfo_imp)catch()
rollout pinfo_imp "csv_txt" (
	button btn1 "Import" width:130 height:30
	fn ReadAllLines csv_txt = (
		local f = undefined, str = #()
		f = try(openFile csv_txt mode:"rtS")catch(undefined)
		if f != undefined do (
			while not eof f do (
				append str (readline f)
				)
			close f
			)
		str
		)
	fn ImportPrimitive adata = (
		local pInfo = #(), s = undefined
		pInfo = filterString adata ","
		--print pInfo
		s = sphere segments:(try(pInfo[6] as integer)catch(1))
		s.radius = try(pInfo[2] as integer)catch(1)
		if s.radius < 0.0 do s.radius = 1.0
		s.pos = [ \
			(try(pInfo[3] as integer)catch(0.0)), \
			(try(pInfo[4] as integer)catch(0.0)), \
			(try(pInfo[5] as integer)catch(0.0)) \
			]
		s.name = try(pInfo[1] as string)catch(s.name)
		s.scale = [ \
			(try(pInfo[8] as float)catch(1.0)), \
			(try(pInfo[8] as float)catch(1.0)), \
			(try(pInfo[8] as float)catch(1.0)) \
			]
		s.rotation = (
			eulerAngles \
				(try(pInfo[5] as float)catch(1.0)) \
				(try(pInfo[6] as float)catch(1.0)) \
				(try(pInfo[7] as float)catch(1.0))
			)
		s.pos = [ \
			(try(pInfo[2] as float)catch(0.0)), \
			(try(pInfo[3] as float)catch(0.0)), \
			(try(pInfo[4] as float)catch(0.0)) \
			]
		)
	local i = 1
	local adata = #()
	on btn1 pressed do (
		pInfo_Name = ""
		pInfo_Node = undefined
		pInfo_Position = [0.0, 0.0, 0.0]
		pInfo_Rotation = [0.0, 0.0, 0.0]
		pInfo_Scale = 1.0
		adata = ReadAllLines (
			GetOpenFileName \
				types:"Supported Files (*.csv, *.txt)|*.csv;*.txt|All files (*.*)|*.*|"
			)
		for i = 1 to adata.count do (
			ImportPrimitive adata[i]
			)
		)
	) createdialog pinfo_imp


```
