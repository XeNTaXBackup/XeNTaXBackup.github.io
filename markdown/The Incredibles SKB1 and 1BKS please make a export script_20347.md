## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-05-09T01:23:34+00:00
- Post Title: The Incredibles: SKB1 and 1BKS please make a export script

hi, listen can you make a export script for SKB1 and 1BKS because the rotation on the X, Y, Z, W axis = 00 00 00 00 00 00 FF 7F are floats for the rotations and the rest of the translation is a float called 00 00 00 00 00 00 on the x, y and z axis the rotations match in game and translation match in game with all floats, there all in 16 bit integers. 
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
	public translation
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
	
	function ReadAnimationsFromFile filePath =
	(
		local reader = fopen filePath "rb"
		
		local asset = AnimationAsset()
		
		local magic = readlong reader
		
		local unkInt1 = Readlong reader
		
		asset.BoneCount = readshort reader
		asset.FrameCount = ReadShort reader
		asset.KeyframeCount =  Readlong reader
		
		
		local unkInt2 = ReadLong reader
		local unkInt3 = ReadLong reader
		local unkInt4 = ReadLong reader
				
		for i = 1 to asset.KeyframeCount do
		(
			local kf = Keyframe()
			
			kf.Frame = Readshort reader
				
			local RotationX = Readshort reader
			local RotationY = Readshort reader
			local RotationZ = Readshort reader
			local RotationW = Readshort reader
			local TranslationX = ReadShort reader
			local TranslationY = ReadShort reader
			local TranslationZ = ReadShort reader
			
			
			kf.Rotation = quat (Float(RotationX)) (Float(RotationY)) (Float(RotationZ)) (Float(RotationW))
			kf.translation =  [ (float TranslationX), (float TranslationY), (float TranslationZ)]
				
			append asset.Keyframes kf
		)
		
		for i = 1 to asset.FrameCount do
		(
			append asset.TimeMap (Readfloat reader)
		)
		
		for j = 1 to (asset.FrameCount - 1) do
		(
			local frameList = #()
			
			for i = 1 to asset.BoneCount do
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
			for FrameIndex = 1 to (glAsset.FrameCount - 1) do
			(
				local keyframeList = glAsset.KeyframeMap[frameIndex]
				for boneIndex = 1 to glAsset.BoneCount do
				(
					
					local keyframeIndex = keyframeList[boneIndex] + 1
					local kf = glAsset.Keyframes[keyframeIndex]
					at time (kf.Frame)
					(
						mAnimationNodes[BoneIndex].Controller.Rotation = inverse kf.Rotation
						mAnimationNodes[BoneIndex].Controller.Position = kf.Translation
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


can you convert this into a export *.anim script by it's opposite for SKB1 please in maxscript

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
	
	function ReadLongReversed input =
	(
		local intArray = #()
		local byte1 = ReadByte input
		local byte2 = ReadByte input
		local byte3 = ReadByte input
		local byte4 = ReadByte input
		append intArray byte4
		append intArray byte3
		append intArray byte2
		append intArray byte1
		
		local byteArray = dotnet.valueToDotNetObject intArray (dotnetclass "System.Byte[]")
		local returnValue = bitConverter.ToInt32 byteArray 0
		
		returnValue
	)
	
	function ReadFloatReversed input =
	(
		local intArray = #()
		local byte1 = ReadByte input
		local byte2 = ReadByte input
		local byte3 = ReadByte input
		local byte4 = ReadByte input
		append intArray byte4
		append intArray byte3
		append intArray byte2
		append intArray byte1
		
		local byteArray = dotnet.valueToDotNetObject intArray (dotnetclass "System.Byte[]")
		local returnValue = bitConverter.ToSingle byteArray 0
		
		returnValue
	)
	
	function ReadShortReversed input =
	(
		local intArray = #()
		local byte1 = ReadByte input
		local byte2 = ReadByte input
		append intArray byte2
		append intArray byte1
		
		local byteArray = dotnet.valueToDotNetObject intArray (dotnetclass "System.Byte[]")
		local returnValue = bitConverter.ToInt16 byteArray 0
		
		returnValue
	)
	
	function ReadAnimationsFromFile filePath =
	(
		local reader = fopen filePath "rb"
		
		local asset = AnimationAsset()
		
		local magic = ReadLong reader
		
		local unkInt1 = ReadLongReversed reader
		
		asset.BoneCount = ReadShortReversed reader		
		asset.FrameCount = ReadShortReversed reader		
		asset.KeyframeCount =  ReadLongReversed reader
		
		local unkInt2 = ReadLongReversed reader
		local unkInt3 = ReadLongReversed reader
		local unkInt4 = ReadLongReversed reader
				
		for i = 1 to asset.KeyframeCount do
		(
			local kf = Keyframe()
			
			kf.Frame = ReadShortReversed reader
				
			local RotationX = ReadShortReversed reader
			local RotationY = ReadShortReversed reader
			local RotationZ = ReadShortReversed reader
			local RotationW = ReadShortReversed reader
			local TranslationX = ReadShortReversed reader
			local TranslationY = ReadShortReversed reader
			local TranslationZ = ReadShortReversed reader
			
			kf.Rotation = quat (Float(RotationX)) (Float(RotationY)) (Float(RotationZ)) (Float(RotationW))
			kf.Translation = [ Float(TranslationX), Float(TranslationY), Float(TranslationZ) ]
			
			append asset.Keyframes kf
		)
		
		for i = 1 to asset.FrameCount do
		(
			append asset.TimeMap (ReadFloatReversed reader)
		)
		
		for i = 1 to (asset.FrameCount - 1) do
		(
			local frameList = #()
			
			for j = 1 to asset.BoneCount do
			(
				local frameIndex = ReadShortReversed reader				
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
		if ( mAnimationNodes == undefined ) then
		mAnimationNodes = GetAnimationNodes()
		
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


can you convert this into a export *.anim script by it's opposite for 1BKS please in maxscript
[SKB1 and 1BKS.zip](https://xentaxbackup.github.io/file/16202_SKB1 and 1BKS.zip)
