## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-01T14:22:50+00:00
- Post Title: [MaxScript] Depth-first bone traversal

So I'm dealing with this model format that has the weight indices stored in a way that you need to traverse the bone hierarchy depth first, instead of breadth first.
Any help on getting the right bones through some algorithm?

EG:
The bone index is 6, but the actual bone's index is 9.



hbS1s[1].png (101.21 KiB) Viewed 99 times
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-02T00:36:48+00:00
- Post Title: [MaxScript] Depth-first bone traversal

I happened to stumble upon something that just so happened to do what I wanted.

```
struct hNode (
	object, 
	children
)


fn traverseDownBranches root DFSBoneArray =(
	for child in root.children do(
		append DFSBoneArray child
		traverseDownBranches child DFSBoneArray
	)
)

fn hTreeFromArray root objectArray =(
	-- create a bag of unlinked hNodes
	hNodeArray = #()
	for obj in objectArray do(
		append hNodeArray (hNode object:obj children:#())
	) 
	--link them up, treewise
	for candidateChild in hNodeArray do(	
		soughtParent = candidateChild.object.parent 
		noParent = true
		for candidateParent in hNodeArray while noParent do(	
			if (candidateParent.object == soughtParent) then (
				append candidateParent.children candidateChild 
				noParent = false	
			)
		)
		--if no parent found in array then root is parent
		if noParent then append root.children candidateChild
	)
	
	DFSBoneArray = #()
	for child in root.children do(
		append DFSBoneArray child
		traverseDownBranches child DFSBoneArray
	)
	return DFSBoneArray
)

```
## Post #3
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2015-05-08T02:04:00+00:00
- Post Title: [MaxScript] Depth-first bone traversal

Depth first or Breath first is just algorithmic problem.
Let's assume "Read a Index" means you count index and name it etc.
you may need global count index in c or c++ save locatin is passed as a argument.

Fn DepthFirstSubcall Index Position .. (
  Do (
    Read a Index.
    Check Sub System Exist at Index
    If Exist Get Sub Index Position; Call DepthFirstSubCall Index Position
    goto Next Index
  ) While Index exist
)

You may nees some DepthFirstMainCall for header stuffs.
There is a algorithem which does not use call stacks.

BreathFirst requires some stack or list

Fn BreathFirstSubCall Index Position.. (
  Do (
    Read a Index
    Check Sub System Exist at Index
    If Exist Get Sub Index Position; Append Index Position at a list
    goto Next Index
  ) While Index exist

  for i = 1 to list Position.count do (
   get index Position from list Position
    call BreathFirstSubCall Index Position
  )
)
