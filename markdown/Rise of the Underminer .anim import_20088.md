## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-04-21T11:58:57+00:00
- Post Title: Rise of the Underminer *.anim import

hi i am having troubles with rise of the underminer file format and for some reason i followed every structures and 2 keyframecounts for this Rise of the Underminer *.anim and all i do is get an error of inverse rotation called =No "Inverse" Function for [0, 0, 0] i followed every coordinates and it's not working. all i want to do is put a float on there, but i can't find rotationw anywhere. and now when i switch it around and get keyframes showed up and rotation is going weird. then i'm putting readshort on the timemaps and i'm trying to make it follow this 01 00 02 00 03 00 etc CD CD and make it follow the second one in to do with there coordinates i tried doing this by modifying someone script but it's a different file format and it's not working.

i have to modify it someone script but it's not working when i modify it can someone help me, what did i do wrong.

```

struct AnimationAsset
(
	public BoneCount,
	public FrameCount,
	public KeyframeCount,
	public KeyframeCount2,
	public Keyframes = #(),
	public TimeMap = #(),
	public KeyframeMap = #()
)

struct Keyframe
(
    public Frame,
    public Rotation,
	public Translation
)

global glAsset = undefined
global bitConverter = dotNetClass "System.BitConverter"

rollout unnamedRollout "ROTU ANIM ASSET IMPORTER" width:162 height:206
(
	button btn1 "import" pos:[30,108] width:100 height:45
	label lbl1 "rise of the underminer anim asset importer" pos:[26,44] width:114 height:58
	

function ReadAnimationsFromFile filePath =
	(
		local reader = fopen filePath "rb"
		
		local asset = AnimationAsset()
		
		local magic = readLong reader
		
		local unkInt1 = ReadLong reader
		
		asset.BoneCount = ReadShort reader
		asset.FrameCount = ReadShort reader		
		asset.KeyframeCount =  Readshort reader
		asset.KeyframeCount2 = ReadShort reader
		
		local unkInt2 = ReadLong reader
		local unkInt3 = ReadLong reader
		local unkInt4 = ReadLong reader
				
		for i = 1 to asset.KeyframeCount do
		(
			local kf = Keyframe()
			
			kf.Frame = Readshort reader
			
			local TranslationY = readShort reader	
			local RotationX = Readshort reader
			local RotationY = Readshort reader
			local RotationZ = Readshort reader
			
			kf.Translation =  TranslationY
			kf.Rotation = ([RotationX, RotationY, RotationZ])
			
				
			append asset.Keyframes kf
		)
		
		for i = 1 to asset.FrameCount do
		(
			append asset.TimeMap (Readshort reader)
		)
		
		for i = 1 to asset.KeyframeCount2 do
		(
			local kf = Keyframe()
			
			kf.Frame = Readshort reader
			
			local TranslationX = readShort reader
			local TranslationY = ReadShort reader
			local TranslationZ = ReadShort reader
			
			kf.Translation =  [ ( float TranslationX), ( float TranslationY), (float TranslationZ)]
			
				
			append asset.Keyframes kf
		)
		
		for i = 1 to (asset.FrameCount - 1) do
		(
			local frameList = #()
			
			for j = 1 to asset.BoneCount do
			(
				local frameIndex = Readshort reader
				append framelist frameIndex
			)
			append asset.KeyframeMap framelist
		)
		
		fclose reader
		
		glAsset = asset
	)
    
    function TraverseNode curNode &nodes =
    (
        append nodes curNode
        for childNode in curNode.Children do
            TraverseNode childNode &nodes
    )
    
    function GetAnimationNodes =
    (		
        local nodes = #()
		 
        
        if ( nodes.Count == 0 ) then
        (
            local animRootNode = GetNodeByName "Dummy002"
			
            
            TraverseNode animRootNode &nodes
        )
        
        return nodes
    )
    
    function LoadAnimation =
	(
		
		local mAnimationNodes = GetAnimationNodes()
		
		animationRange = interval 0 (glAsset.FrameCount)
		
		with animate on
		(
			for frameIndex = 1 to (glAsset.FrameCount - 1) do
			(
				local keyframeList = glAsset.KeyframeMap[frameIndex]
				for boneIndex = 1 to glAsset.BoneCount do
				(
					local keyframeIndex = keyframeList[boneIndex] + 1
					local kf = glAsset.Keyframes[keyframeIndex]
					at time (kf.Frame)
					(
						mAnimationNodes[BoneIndex].Controller.Rotation = inverse kf.Rotation
					)
				)
			)
		)
	)

	on btn1 pressed  do
	(
		local filePath = getOpenFileName caption:"Import VColor OBJ" \
					types:"All Files (*.*)|*.*|"
	
		ReadAnimationsFromFile(filePath)
		LoadAnimation()
	)
)

createDialog unnamedRollout
```


[mr_i_nuke.zip](https://xentaxbackup.github.io/file/16063_mr_i_nuke.zip)
## Post #2
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-04-21T12:00:51+00:00
- Post Title: Rise of the Underminer *.anim import

a bit of a problem
[mr_i_nuke_problem.png](https://xentaxbackup.github.io/file/16064_mr_i_nuke_problem.png)
