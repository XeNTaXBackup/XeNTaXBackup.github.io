## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2018-10-08T14:07:58+00:00
- Post Title: The incredibles: animation controller problems

hi i downloaded someone script and the problem is the animation is still glitching, and i need help to stop it glitching in 3ds max. the problem is it's on the wrong side and it only works with 1 Dummy and that's it and not more so i can't see what's going on.

```

struct AnimationAsset
(
	public BoneCount,
	public FrameCount,
	public KeyframeCount,
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

rollout animLoader "animLoader"
(
	group "About"
	(
		label lab1 "ANIM Asset Importer"
		label lab2 "Script by igorseabra4"
	)
	group "Import"
	(
		button importButton "Import..."
	)
	
    function DecompressFloat compressed =
    (
        local floatInt = bit.shift (bit.and compressed 0x8000) 16
        if ((bit.and compressed 0x7fff) != 0) then
        (
            floatInt = bit.or floatInt ((bit.shift (bit.and compressed 0x7800) 12) + 0x38000000)
            floatInt = bit.or floatInt (bit.shift (bit.and compressed 0x07ff) 12)
        )

        bit.intasfloat floatInt
    )
		
	function ReadAnimationsFromFile filePath =
	(
		local reader = fopen filePath "rb"
		
		local asset = AnimationAsset()
		
		local magic = ReadLong reader
		
		local unkInt1 = ReadLong reader
		
		asset.BoneCount = ReadShort reader		
		asset.FrameCount = ReadShort reader		
		asset.KeyframeCount =  ReadLong reader
		
		local unkInt2 = ReadLong reader
		local unkInt3 = ReadLong reader
		local unkInt4 = ReadLong reader
				
		for i = 1 to asset.KeyframeCount do
		(
			local kf = Keyframe()
			
			kf.Frame = ReadShort reader
				
			local RotationX = ReadShort reader
			local RotationY = ReadShort reader
			local RotationZ = ReadShort reader
			local RotationW = ReadShort reader
			local TranslationX = ReadShort reader
			local TranslationY = ReadShort reader
			local TranslationZ = ReadShort reader
			
			kf.Rotation = quat (DecompressFloat(RotationX)) (DecompressFloat(RotationY)) (DecompressFloat(RotationZ)) (DecompressFloat(RotationW))
			kf.Translation = [ DecompressFloat(TranslationX), DecompressFloat(TranslationY), DecompressFloat(TranslationZ) ]
			
			append asset.Keyframes kf
		)
		
		for i = 1 to asset.FrameCount do
		(
			append asset.TimeMap (ReadFloat reader)
		)
		
		for i = 1 to (asset.FrameCount - 1) do
		(
			local frameList = #()
			
			for j = 1 to asset.BoneCount do
			(
				local frameIndex = ReadShort reader				
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
						mAnimationNodes[boneIndex].Controller.Rotation = kf.Rotation
						mAnimationNodes[boneIndex].Controller.Position = kf.Translation
					)
				)
			)
		)
	)

	on importButton pressed do
	(
		local filePath = getOpenFileName caption:"Import VColor OBJ" \
					types:"All Files (*.*)|*.*|"
	
		ReadAnimationsFromFile(filePath)
		LoadAnimation()
	)
)

createDialog animLoader 160 160
```
 so something happening to this [https://gyazo.com/1ef12d671a2cc0b8547e16e710b89dd4](https://gyazo.com/1ef12d671a2cc0b8547e16e710b89dd4)
[Animation Controller2.rar](https://xentaxbackup.github.io/file/14987_Animation Controller2.rar)
## Post #2
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2018-10-13T21:34:13+00:00
- Post Title: The incredibles: animation controller problems

So i tried compressing it and it does not get the same size as the original model while using the animation controller, i typed in ckf.RotationX and other ckf and typed in ckf next to decompressfloats and it still give me a codeblock, which i want to get the original same size as the model as that animation controller that file format. but the thing is the bones are messed up it's going on the wrong coordinates and it's stretching out and it's going on the x axis which i want it to stand still and do it's animation pose. so i need help to get it fix. like all i want to do is get the same size without the vertices stretching apart, without the bones stretching apart. so can someone help me please.
## Post #3
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2018-10-13T22:24:20+00:00
- Post Title: The incredibles: animation controller problems

THAT'S IT, NOBODY NOT GOING TO HELP ME!!!!!!!!!!!!!!!!!!!!!!!!!!!
## Post #4
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-03-12T12:06:04+00:00
- Post Title: The incredibles: animation controller problems

so at the moment the rotation is called a float all along and now i'm having this problem with a float translation on the x,y and z axis. so here another one

```

struct AnimationAsset
(
	public BoneCount,
	public FrameCount,
	public KeyframeCount,
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

rollout animLoader "animLoader"
(
	group "About"
	(
		label lab1 "ANIM Asset Importer"
		label lab2 "Script by igorseabra4"
	)
	group "Import"
	(
		button importButton "Import..."
	)
	
    function DecompressFloat compressed =
    (
        local floatInt = bit.shift (bit.and compressed 0x8000) 16
        if ((bit.and compressed 0x7fff) != 0) then
        (
            floatInt = bit.or floatInt ((bit.shift (bit.and compressed 0x7800) 12) + 0x38000000)
            floatInt = bit.or floatInt (bit.shift (bit.and compressed 0x07ff) 12)
        )

        bit.intasfloat floatInt
    )
		

	function ReadAnimationsFromFile filePath =
	(
		local reader = fopen filePath "rb"
		
		local asset = AnimationAsset()
		
		local magic = ReadLong reader
		
		local unkInt1 = ReadLong reader
		
		asset.BoneCount = ReadShort reader		
		asset.FrameCount = ReadShort reader		
		asset.KeyframeCount =  ReadLong reader
		
		local unkInt2 = ReadLong reader
		local unkInt3 = ReadLong reader
		local unkInt4 = ReadLong reader
				
		for i = 1 to asset.KeyframeCount do
		(
			local kf = Keyframe()
			
			kf.Frame = ReadShort reader
				
			local RotationX = Readshort reader
			local RotationY = Readshort reader
			local RotationZ = Readshort reader
			local RotationW = Readshort reader
			local TranslationX = Readshort reader
			local TranslationY = Readshort reader
			local TranslationZ = Readshort reader
			
			kf.Rotation = quat (Float(RotationX)) (Float(RotationY)) (Float(RotationZ)) (Float(RotationW))
			kf.Translation = [ ( Float TranslationX), ( Float TranslationY), ( Float TranslationZ) ]
				
			append asset.Keyframes kf
		)
		
		for i = 1 to asset.FrameCount do
		(
			append asset.TimeMap (Readfloat reader)
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
						mAnimationNodes[boneIndex].Controller.Rotation = inverse kf.Rotation
						mAnimationNodes[boneIndex].Controller.Position = kf.Translation
					)
				)
			)
		)
	)

	on importButton pressed do
	(
		local filePath = getOpenFileName caption:"Import VColor OBJ" \
					types:"All Files (*.*)|*.*|"
	
		ReadAnimationsFromFile(filePath)
		LoadAnimation()
	)
)

createDialog animLoader 160 160
```
## Post #5
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-03-12T12:07:52+00:00
- Post Title: The incredibles: animation controller problems

couldn't send a gif because XenTax wouldn't allow me so i have to send a link instead which i did send a gif. [https://gyazo.com/caac7ce96cc1a3dc7133d1382c349864](https://gyazo.com/caac7ce96cc1a3dc7133d1382c349864)
## Post #6
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-03-12T12:36:46+00:00
- Post Title: The incredibles: animation controller problems

i think it needs another function for floats only on the translation x, y and z only and i'm out of luck to get it at the exact same size and touch the grid.
i nearly completed the script.
