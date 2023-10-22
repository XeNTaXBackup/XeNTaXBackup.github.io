## Post #1
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-23T11:34:55+00:00
- Post Title: [HELP]Bones in noesis

Hi there!

So, i found the archive of a model from Leisure Suit Larry: Magna Cum Laude that looks like the skeleton of one of the girls. Now, before saying anything else, I must say i am a complete noob when it comes to skeletons and noesis scripting so, i want to know if this file is in fact the skeleton, how bones and skeletons work in noesis and, if the file is the skeleton data, how do i translate it into data that noesis can interpret.

Here is the file, it is basicaly a txt with .AKC extension:

```
LocalDrawingTransform[45]
CoordSys
{
	RotTransCoordSys "ROOTR"
	{
		Position -0.000000 -0.037779 0.941825
		Orientation 0.000000 0.000000 0.707106 0.707107
		LocalDrawingTransform 1.000000 0.000000 0.000000 0.000000  0.000000 1.000000 0.000000 0.000000  0.000000 0.000000 1.000000 0.000000  0.000000 0.000000 0.000000 1.000000
	}
	RotTransCoordSys "PELVISR"
	{
		Position 0.005879 -0.000000 0.000000
		Orientation 0.499999 0.500000 0.500000 0.500001
		Parent "ROOTR"
		LocalDrawingTransform 0.000000 1.000000 -0.000001 0.000000  -0.000001 0.000001 1.000000 0.000000  1.000000 0.000000 0.000001 0.000000  -0.000000 -0.005879 0.000000 1.000000
	}
	RotTransCoordSys "SPINER"
	{
		Position 0.092884 -0.006639 0.000000
		Orientation 0.000002 0.000001 -0.130921 0.991393
		Parent "PELVISR"
		LocalDrawingTransform 0.259588 0.965719 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.965719 -0.259588 -0.000001 0.000000  -0.089503 0.024845 0.000000 1.000000
	}
	RotTransCoordSys "SPINE1R"
	{
		Position 0.120631 -0.000069 -0.000000
		Orientation 0.000000 -0.000000 0.173648 0.984808
		Parent "SPINER"
		LocalDrawingTransform -0.086363 0.996264 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.996264 0.086363 0.000000 0.000000  -0.205982 -0.048458 -0.000000 1.000000
	}
	RotTransCoordSys "SPINE2R"
	{
		Position 0.092234 -0.000121 -0.000000
		Orientation -0.000000 -0.000000 0.043619 0.999048
		Parent "SPINE1R"
		LocalDrawingTransform -0.172864 0.984946 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.984946 0.172864 0.000000 0.000000  -0.292869 -0.074144 -0.000000 1.000000
	}
	RotTransCoordSys "NECKR"
	{
		Position 0.152646 -0.000049 -0.000000
		Orientation 0.000000 0.000000 -0.160743 0.986996
		Parent "SPINE2R"
		LocalDrawingTransform 0.148597 0.988898 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.988898 -0.148597 -0.000000 0.000000  -0.446003 0.071097 0.000000 1.000000
	}
	RotTransCoordSys "HEADR"
	{
		Position 0.064642 0.000000 -0.000000
		Orientation 0.000000 -0.000000 0.087553 0.996160
		Parent "NECKR"
		LocalDrawingTransform -0.026179 0.999657 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.999657 0.026179 0.000000 0.000000  -0.515218 -0.019067 -0.000000 1.000000
	}
	RotTransCoordSys "EYEBROWR"
	{
		Position 0.123660 0.080853 0.000329
		Orientation -0.003012 0.002918 -0.719217 0.694773
		Parent "HEADR"
		LocalDrawingTransform 0.999930 -0.008389 -0.008384 0.000000  0.008384 -0.000012 0.999965 0.000000  -0.008388 -0.999965 0.000058 0.000000  -0.077778 0.641950 0.000331 1.000000
	}
	RotTransCoordSys "JAWR"
	{
		Position 0.050846 0.036597 0.000000
		Orientation -0.000000 0.000002 -0.826495 0.562944
		Parent "HEADR"
		LocalDrawingTransform 0.939808 -0.341702 -0.000001 0.000000  0.000000 -0.000003 1.000000 0.000000  -0.341702 -0.939808 -0.000003 0.000000  0.155489 0.547129 0.000002 1.000000
	}
	RotTransCoordSys "HAIRBN1R"
	{
		Position 0.071848 -0.040862 -0.000000
		Orientation -0.000000 -0.000001 0.954138 0.299367
		Parent "HEADR"
		LocalDrawingTransform -0.549593 -0.835432 0.000001 0.000000  0.000001 0.000001 1.000000 0.000000  -0.835432 0.549593 -0.000000 0.000000  0.469388 -0.353265 0.000000 1.000000
	}
	RotTransCoordSys "HAIRBN2R"
	{
		Position 0.092461 -0.000002 0.000000
		Orientation -0.000000 0.000000 0.269923 0.962882
		Parent "HAIRBN1R"
		LocalDrawingTransform -0.035244 -0.999379 0.000001 0.000000  0.000000 0.000001 1.000000 0.000000  -0.999379 0.035244 0.000000 0.000000  0.505631 -0.105858 -0.000000 1.000000
	}
	RotTransCoordSys "REYER"
	{
		Position 0.096699 0.070851 -0.032818
		Orientation -0.000000 0.000000 -0.000000 1.000000
		Parent "HEADR"
		LocalDrawingTransform -0.027557 1.052271 0.000003 0.000000  -0.000000 -0.000003 1.081584 0.000000  1.052271 0.027557 0.000000 0.000000  -0.644123 -0.094650 0.035495 1.000000
	}
	RotTransCoordSys "LEYER"
	{
		Position 0.096699 0.070851 0.032603
		Orientation -0.000000 0.000000 -0.000000 1.000000
		Parent "HEADR"
		LocalDrawingTransform -0.027557 1.052271 0.000003 0.000000  -0.000000 -0.000003 1.081584 0.000000  1.052271 0.027557 0.000000 0.000000  -0.644123 -0.094650 -0.035263 1.000000
	}
	RotTransCoordSys "LEYELASR"
	{
		Position 0.092774 0.078773 0.034549
		Orientation 0.000000 0.000000 -0.000000 1.000000
		Parent "HEADR"
		LocalDrawingTransform -0.026179 0.999657 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.999657 0.026179 0.000000 0.000000  -0.607993 -0.097840 -0.034549 1.000000
	}
	RotTransCoordSys "REYELASR"
	{
		Position 0.092774 0.078773 -0.034373
		Orientation 0.000000 0.000000 -0.000000 1.000000
		Parent "HEADR"
		LocalDrawingTransform -0.026179 0.999657 0.000003 0.000000  0.000000 -0.000003 1.000000 0.000000  0.999657 0.026179 0.000000 0.000000  -0.607993 -0.097840 0.034373 1.000000
	}
	RotTransCoordSys "LCLAVICR"
	{
		Position -0.010758 -0.006238 0.028261
		Orientation 0.604495 -0.098696 0.780142 -0.127372
		Parent "NECKR"
		LocalDrawingTransform 0.043358 -0.984808 -0.168148 0.000000  0.968326 -0.000000 0.249690 0.000000  -0.245897 -0.173648 0.953615 0.000000  0.081809 0.065115 -0.430448 1.000000
	}
	RotTransCoordSys "LUPARMR"
	{
		Position 0.104971 -0.000000 0.000000
		Orientation -0.085603 -0.238880 -0.079696 0.963980
		Parent "LCLAVICR"
		LocalDrawingTransform -0.078587 -0.996907 -0.000898 0.000000  0.733925 -0.058465 0.676709 0.000000  -0.674669 0.052521 0.736250 0.000000  0.184813 -0.021485 -0.394264 1.000000
	}
	RotTransCoordSys "L4ARMR"
	{
		Position 0.210644 0.000000 0.000000
		Orientation 0.000000 -0.000000 0.141291 0.989968
		Parent "LUPARMR"
		LocalDrawingTransform 0.203432 -0.979089 -0.000898 0.000000  0.720978 0.149182 0.676709 0.000000  -0.662425 -0.138312 0.736250 0.000000  -0.018789 -0.027853 -0.394264 1.000000
	}
	RotTransCoordSys "LHANDR"
	{
		Position 0.244347 0.000000 0.000000
		Orientation 0.706495 0.021586 -0.021603 0.707058
		Parent "L4ARMR"
		LocalDrawingTransform 0.143280 0.000110 -0.989682 0.000000  0.728741 -0.676626 0.105427 0.000000  -0.669633 -0.736327 -0.097027 0.000000  -0.264346 0.394255 -0.012051 1.000000
	}
	RotTransCoordSys "LFING0R"
	{
		Position 0.025516 0.011878 -0.020037
		Orientation -0.677769 -0.217767 0.097569 0.695476
		Parent "LHANDR"
		LocalDrawingTransform 0.557652 -0.829214 0.037787 0.000000  0.491964 0.366829 0.789562 0.000000  -0.668577 -0.421711 0.612507 0.000000  -0.199346 -0.093922 -0.426304 1.000000
	}
	RotTransCoordSys "LFING01R"
	{
		Position 0.049868 -0.000000 0.000000
		Orientation -0.000000 -0.000000 0.000000 1.000000
		Parent "LFING0R"
		LocalDrawingTransform 0.557652 -0.829214 0.037787 0.000000  0.491964 0.366829 0.789562 0.000000  -0.668577 -0.421711 0.612507 0.000000  -0.249214 -0.093922 -0.426304 1.000000
	}
	RotTransCoordSys "LFING1R"
	{
		Position 0.070766 -0.003528 -0.017944
		Orientation -0.043220 -0.043578 0.000398 0.998115
		Parent "LHANDR"
		LocalDrawingTransform 0.228864 -0.084590 -0.969776 0.000000  0.714786 -0.661681 0.226402 0.000000  -0.660834 -0.744998 -0.090971 0.000000  -0.333169 0.395277 -0.057625 1.000000
	}
	RotTransCoordSys "LFING11R"
	{
		Position 0.026103 0.000000 -0.000000
		Orientation -0.000000 -0.000000 -0.078459 0.996917
		Parent "LFING1R"
		LocalDrawingTransform 0.212813 -0.119351 -0.969776 0.000000  0.602476 -0.765352 0.226402 0.000000  -0.769242 -0.632448 -0.090971 0.000000  -0.293014 0.446613 -0.057625 1.000000
	}
	RotTransCoordSys "LFING2R"
	{
		Position 0.071649 -0.008364 0.011344
		Orientation 0.045814 0.041250 -0.046202 0.997028
		Parent "LHANDR"
		LocalDrawingTransform 0.064975 0.081637 -0.994542 0.000000  0.666481 -0.745314 -0.017637 0.000000  -0.742685 -0.661698 -0.102835 0.000000  -0.296628 0.431121 0.041090 1.000000
	}
	RotTransCoordSys "LFING21R"
	{
		Position 0.031654 0.000000 0.000000
		Orientation 0.000000 -0.000000 -0.043619 0.999048
		Parent "LFING2R"
		LocalDrawingTransform 0.071843 0.075664 -0.994542 0.000000  0.598987 -0.800565 -0.017637 0.000000  -0.797529 -0.594451 -0.102835 0.000000  -0.289458 0.458092 0.041090 1.000000
	}
	RotTransCoordSys "RCLAVICR"
	{
		Position -0.010758 -0.006237 -0.028261
		Orientation -0.604495 0.098694 0.780142 -0.127374
		Parent "NECKR"
		LocalDrawingTransform 0.043358 -0.984808 0.168148 0.000000  -0.968326 0.000000 0.249690 0.000000  -0.245897 -0.173648 -0.953615 0.000000  0.081809 0.065115 0.430448 1.000000
	}
	RotTransCoordSys "RUPARMR"
	{
		Position 0.104971 -0.000000 -0.000000
		Orientation 0.085603 0.238880 -0.079696 0.963980
		Parent "RCLAVICR"
		LocalDrawingTransform -0.078586 -0.996907 0.000898 0.000000  -0.733925 0.058465 0.676710 0.000000  -0.674669 0.052521 -0.736250 0.000000  0.184813 -0.021485 0.394264 1.000000
	}
	RotTransCoordSys "R4ARMR"
	{
		Position 0.210644 0.000000 0.000000
		Orientation -0.000000 -0.000000 0.141291 0.989968
		Parent "RUPARMR"
		LocalDrawingTransform 0.203432 -0.979088 0.000898 0.000000  -0.720978 -0.149182 0.676710 0.000000  -0.662424 -0.138312 -0.736250 0.000000  -0.018789 -0.027853 0.394264 1.000000
	}
	RotTransCoordSys "RHANDR"
	{
		Position 0.244347 -0.000000 0.000000
		Orientation -0.706495 -0.021586 -0.021603 0.707058
		Parent "R4ARMR"
		LocalDrawingTransform 0.143280 0.000110 0.989682 0.000000  -0.728741 0.676626 0.105427 0.000000  -0.669633 -0.736327 0.097027 0.000000  -0.264346 0.394255 0.012051 1.000000
	}
	RotTransCoordSys "RFING0R"
	{
		Position 0.025516 0.011878 0.020037
		Orientation 0.677769 0.217767 0.097569 0.695477
		Parent "RHANDR"
		LocalDrawingTransform 0.557652 -0.829214 -0.037787 0.000000  -0.491964 -0.366829 0.789562 0.000000  -0.668577 -0.421711 -0.612507 0.000000  -0.199346 -0.093922 0.426304 1.000000
	}
	RotTransCoordSys "RFING01R"
	{
		Position 0.049868 0.000000 -0.000000
		Orientation -0.000000 -0.000000 0.000000 1.000000
		Parent "RFING0R"
		LocalDrawingTransform 0.557652 -0.829214 -0.037787 0.000000  -0.491964 -0.366829 0.789562 0.000000  -0.668577 -0.421711 -0.612507 0.000000  -0.249214 -0.093922 0.426304 1.000000
	}
	RotTransCoordSys "RFING1R"
	{
		Position 0.070766 -0.003528 0.017944
		Orientation 0.043220 0.043578 0.000398 0.998115
		Parent "RHANDR"
		LocalDrawingTransform 0.228864 -0.084590 0.969776 0.000000  -0.714786 0.661681 0.226403 0.000000  -0.660834 -0.744998 0.090971 0.000000  -0.333169 0.395276 0.057625 1.000000
	}
	RotTransCoordSys "RFING11R"
	{
		Position 0.026103 0.000000 -0.000000
		Orientation 0.000000 -0.000000 -0.078459 0.996917
		Parent "RFING1R"
		LocalDrawingTransform 0.212813 -0.119351 0.969776 0.000000  -0.602476 0.765352 0.226403 0.000000  -0.769242 -0.632448 0.090971 0.000000  -0.293014 0.446613 0.057625 1.000000
	}
	RotTransCoordSys "RFING2R"
	{
		Position 0.071649 -0.008364 -0.011344
		Orientation -0.045814 -0.041250 -0.046202 0.997028
		Parent "RHANDR"
		LocalDrawingTransform 0.064975 0.081637 0.994542 0.000000  -0.666481 0.745314 -0.017636 0.000000  -0.742685 -0.661698 0.102835 0.000000  -0.296628 0.431121 -0.041090 1.000000
	}
	RotTransCoordSys "RFING21R"
	{
		Position 0.031654 0.000000 0.000000
		Orientation -0.000000 -0.000000 -0.043619 0.999048
		Parent "RFING2R"
		LocalDrawingTransform 0.071843 0.075664 0.994542 0.000000  -0.598987 0.800565 -0.017636 0.000000  -0.797529 -0.594451 0.102835 0.000000  -0.289458 0.458092 -0.041090 1.000000
	}
	RotTransCoordSys "RBREASTR"
	{
		Position 0.048754 0.029431 0.052177
		Orientation -0.083904 0.054871 -0.782075 0.615067
		Parent "SPINE2R"
		LocalDrawingTransform 0.978144 -0.065893 -0.197209 0.000000  0.198734 0.017387 0.979899 0.000000  -0.061140 -0.997675 0.030102 0.000000  -0.030725 0.355485 -0.053324 1.000000
	}
	RotTransCoordSys "LBREASTR"
	{
		Position 0.048754 0.029431 -0.052177
		Orientation 0.083903 -0.054870 -0.782075 0.615067
		Parent "SPINE2R"
		LocalDrawingTransform 0.978144 -0.065892 0.197212 0.000000  -0.198737 -0.017387 0.979899 0.000000  -0.061139 -0.997675 -0.030102 0.000000  -0.030725 0.355484 0.053324 1.000000
	}
	RotTransCoordSys "LTHIGHR"
	{
		Position -0.087976 0.030522 0.080747
		Orientation 0.105086 0.993683 0.010505 0.037963
		Parent "SPINER"
		LocalDrawingTransform -0.052191 0.998598 0.008852 0.000000  0.077653 0.012896 -0.996897 0.000000  -0.995613 -0.051342 -0.078217 0.000000  -0.005963 -0.006912 0.080444 1.000000
	}
	RotTransCoordSys "LCALFR"
	{
		Position 0.380881 0.000000 -0.000000
		Orientation 0.000000 -0.000000 0.005973 0.999982
		Parent "LTHIGHR"
		LocalDrawingTransform -0.064116 0.997903 0.008852 0.000000  0.077494 0.013822 -0.996897 0.000000  -0.994929 -0.063231 -0.078217 0.000000  -0.386734 -0.011533 0.080444 1.000000
	}
	RotTransCoordSys "LFOOTR"
	{
		Position 0.470874 -0.000000 0.000000
		Orientation 0.016112 0.039664 -0.031020 0.998601
		Parent "LCALFR"
		LocalDrawingTransform -0.000000 0.999048 0.043618 0.000000  0.000000 0.043618 -0.999048 0.000000  -1.000000 -0.000000 0.000000 0.000000  -0.847696 0.037744 0.148601 1.000000
	}
	RotTransCoordSys "LTOE0R"
	{
		Position 0.094716 0.129962 0.000000
		Orientation 0.000000 -0.000000 -0.707107 0.707107
		Parent "LFOOTR"
		LocalDrawingTransform 0.999048 0.000000 0.043618 0.000000  0.043618 -0.000000 -0.999048 0.000000  -0.000000 1.000000 0.000000 0.000000  -0.092218 0.942412 0.148601 1.000000
	}
	RotTransCoordSys "RTHIGHR"
	{
		Position -0.087976 0.030523 -0.080747
		Orientation 0.105086 0.993683 -0.010502 -0.037962
		Parent "SPINER"
		LocalDrawingTransform -0.052191 0.998598 -0.008852 0.000000  -0.077653 -0.012896 -0.996897 0.000000  -0.995613 -0.051342 0.078217 0.000000  -0.005963 -0.006912 -0.080444 1.000000
	}
	RotTransCoordSys "RCALFR"
	{
		Position 0.380881 0.000000 -0.000000
		Orientation 0.000000 0.000000 0.005973 0.999982
		Parent "RTHIGHR"
		LocalDrawingTransform -0.064116 0.997903 -0.008852 0.000000  -0.077494 -0.013822 -0.996897 0.000000  -0.994929 -0.063231 0.078217 0.000000  -0.386734 -0.011533 -0.080444 1.000000
	}
	RotTransCoordSys "RFOOTR"
	{
		Position 0.470874 -0.000000 0.000000
		Orientation -0.016112 -0.039664 -0.031020 0.998601
		Parent "RCALFR"
		LocalDrawingTransform -0.000000 0.999048 -0.043618 0.000000  -0.000000 -0.043618 -0.999048 0.000000  -1.000000 -0.000000 0.000000 0.000000  -0.847696 0.037744 -0.148601 1.000000
	}
	RotTransCoordSys "RTOE0R"
	{
		Position 0.094716 0.129962 0.000000
		Orientation -0.000000 0.000000 -0.707107 0.707107
		Parent "RFOOTR"
		LocalDrawingTransform 0.999048 0.000000 -0.043618 0.000000  -0.043618 0.000000 -0.999048 0.000000  -0.000000 1.000000 0.000000 0.000000  -0.092218 0.942412 -0.148601 1.000000
	}
}
```


Thank you in advance
## Post #2
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-23T15:04:29+00:00
- Post Title: [HELP]Bones in noesis

All right, i found out how to make a bone in noesis:

```
	def __init__(self, index, name, matrix, parentName = None, parentIndex = -1):
		self.index = index
		self.name = name
		self.setMatrix(matrix)
		self.parentName = parentName
		self.parentIndex = parentIndex #parent index may be specified instead of parentName, if it's more convenient. this is an index corresponding to self.index, and not the position in the list.
	def __repr__(self):
		return "(NoeBone:" + repr(self.index) + "," + self.name + "," + repr(self.parentName) + "," + repr(self.parentIndex) + ")"

	def setMatrix(self, matrix):
		if not isinstance(matrix, NoeMat43):
			noesis.doException("Invalid type provided for bone matrix")
		self._matrix = matrix
	def getMatrix(self):
		return self._matrix
```


A "NoeMat43" is 48 bytes grouped in 4 vector 3. What i need to know now is, what are each of those vector3 for?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-23T15:22:29+00:00
- Post Title: [HELP]Bones in noesis

3x4 matrix is for rotation, vec4 for position (or 4x4 matrix, last column can be ignored, so 4x3 in Noesis)

But as a noob, as you wrote, you wouldn't start like this. If you had hex data as a base, then 'yes'
but since you've ASCII data here (.AKC) it would make more sense to "convert" them to smd for example:

Build the hierarchy; from some example smd:
version 1
nodes
 0 "Bip01 root" -1
 1 "Bip01 Pelvis" 0
 2 "Bip01 L Leg" 1
 3 "Bip01 L Leg1" 2
 4 "Bip01 L Foot" 3
 5 "Bip01 L Toe0" 4
...
end
skeleton

#(where Pelvis is the parent for "L Leg")

time 0
 0 0.036827 -0.141679 5.384692 1.570796 -0.000000 0.000000
 1 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
 2 0.584765 -0.000001 -0.000000 -1.508191 0.461758 -3.000221
 3 0.124339 0.306796 2.409173 -0.090667 0.051733 0.000000
 4 0.161219 0.229377 2.507935 -0.966771 0.854986 3.141592
 5 0.082358 0.047370 1.253160 0.000000 -0.000000 -0.000000
...
end

Where the first 3 floats in a line are position then 3 euler angels (in radians) to follow.

So your task would be to copy the .AKC into such a scheme including transforming the 4 floats of quaternion (Orientation 0.000000 0.000000 0.707106 0.707107 for example) to euler angles (iirc).
## Post #4
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-24T09:48:19+00:00
- Post Title: [HELP]Bones in noesis

> Reply from shakotay2
>
> Where the first 3 floats in a line are position then 3 euler angels (in radians) to follow.

So your task would be to copy the .AKC into such a scheme including transforming the 4 floats of quaternion (Orientation 0.000000 0.000000 0.707106 0.707107 for example) to euler angles (iirc)

I don't think I've understand you properly. Are you saying that i have to transform the Quaternion for orientation into a matrix of 3xeuler angles? ((0, 0, 0), (0, 0, 0), (0, 0, 0)) 
Or just 1xeuler angle? (0, 0, 0)

I understand how to make the first one, but the 4x3 matrix in noesis requires 4xvector 3, then i dont know how to fill the rest of information if it is the second case.


> Reply from shakotay2
>
> But as a noob, as you wrote, you wouldn't start like this. If you had hex data as a base, then 'yes'
but since you've ASCII data here (.AKC) it would make more sense to "convert" them to smd for example:

As for this, i was thinking in parsing the data to floats (but i dont even know if it is possible in python(i hope so)).
Another thing that i would like you to tell me is, How can i work with another archive from the script? I mean, the 3d model is in one archive and animations, skeleton and materials are in different archives so, How can i add them to the model?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-24T10:50:43+00:00
- Post Title: [HELP]Bones in noesis

> Reply from Repeperilka
>
> Or just 1xeuler angle? (0, 0, 0)yep, see [http://www.euclideanspace.com/maths/geo ... onToEuler/](http://www.euclideanspace.com/maths/geometry/rotations/conversions/quaternionToEuler/)

> I understand how to make the first one, but the 4x3 matrix in noesis requires 4xvector 3, then i dont know how to fill the rest of information if it is the second case.4th line is position, as I wrote, it's x y z 1 usually in matrices. If vec3 is required you simply can ignore w=1.

> As for this, i was thinking in parsing the data to floats (but i dont even know if it is possible in python(i hope so)).You're a pythoner, aren't you? Well, everything should be possible with coding, even in python. 
But I don't get it, why "parsing the data to floats"? The data is already ASCII floats in the .AKC, isn't it?

> How can i work with another archive from the script? I mean, the 3d model is in one archive and animations, skeleton and materials are in different archives so, How can i add them to the model?I'd suggest to do it step by step: model, skeleton, then animation (hardest part usually). You'd need to upload a model sample. 
Once you have the skeleton in Noesis you can simply drag the animation file onto it, iirc.
(But you need to have a script which handles the animation, of course.)
## Post #6
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-24T12:58:48+00:00
- Post Title: [HELP]Bones in noesis

> Reply from shakotay2
>
> 4th line is position, as I wrote, it's x y z 1 usually in matrices. If vec3 is required you simply can ignore w=1.

So, final result should be this one, right?

```
((orientation(eulerAngles)), (orientation(eulerAngles)), (orientation(eulerAngles)), (position(vector3)))
```

Then, from wich quaternions do i take the three orientation angles? In the .akc archive, in each bone, the field "Orientation" only have 1 quaternion. And the field "LocalDrawingTransform" (wich i dont know what means) has 4 quaternions

> Reply from shakotay2
>
> You're a pythoner, aren't you? Well, everything should be possible with coding, even in python. 
But I don't get it, why "parsing the data to floats"? The data is already ASCII floats in the .AKC, isn't it?

Haha a pythoner. I came from programming in unity with c#, i just started learning python for this project and i must say that the indentation and class declarations are killing me, and i've just started learning it. So i wouldent consider myself a pythoner xD.
I meant to parse hex ASCII strings to floats so i can store them on a variable for later use in the NoeMat34(if that makes sense)

> Reply from shakotay2
>
> I'd suggest to do it step by step: model, skeleton, then animation (hardest part usually). You'd need to upload a model sample. 
Once you have the skeleton in Noesis you can simply drag the animation file onto it, iirc.
(But you need to have a script which handles the animation, of course.)

But for the animations i need the bones so, where can i get the bones of the currently shown skeleton?

Sorry for asking too much but i'm not very good at anything related to this xD
Last Question: any tutorials for game assets extraction and noesis scripting? I've read the ones on the wiki, "An Imitable Workflow for Reverse Engineering a Game Model", the one for Hex2Obj, the one for ModelResearcher, "Noesis tutorial Basic Model" by chrrox, most of the videos of xentax in youtube and a couple of videos that a guy uploaded about scripting in noesis
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-24T13:39:12+00:00
- Post Title: [HELP]Bones in noesis

> Reply from Repeperilka
>
> So, final result should be this one, right?
Code: Select all((orientation(eulerAngles)), (orientation(eulerAngles)), (orientation(eulerAngles)), (position(vector3)))
Then, from wich quaternions do i take the three orientation angles? In the .akc archive, in each bone, the field "Orientation" only have 1 quaternion. And the field "LocalDrawingTransform" (wich i dont know what means) has 4 quaternions
For SPINER I'd use this quad for rotation: Orientation 0.000002 0.000001 -0.130921 0.991393

For the quads, you need a function like Quaternion2Euler(Quat q, D3Dvec3 &euler) where
struct D3Dvec3 {
	float x, y, z ;
} ;

struct Quat {  // (well, little bit inconsistent to use floats and doubles, but THAT's me  )
	double x, y, z, w ;
} ;
You can set the angles to 0.0 0.0 0.0 for a first test in the smd and use position values only.


btw. the local thingie is not "my terrain" (bonespace, localspace, worldspace); I'll check this later when updating my skel2smd project (WIP, time to check the matr[3][3] to quaternion function, how to use it with matr[4][4]?)

> But for the animations i need the bones so, where can i get the bones of the currently shown skeleton?
For example (uncomplete), with hierarchy:
ROOTR - SPINER - SPINER1 - SPINER2 - NECKR - HEADR - EYEBROWR

You really should try building an smd for the skeleton (see my first post), it's the fastest way here, imho.

> Sorry for asking too much but i'm not very good at anything related to this xDThat's like everyone started.  

> Last Question: any tutorials for game assets extraction and noesis scripting?I wouldn't know better than that you found already. You might also search this forum for skeleton for example.

Don't have much time today, as you may know. Will look in here in three days or so to see you progress.
(If you don't have the skeleton then I maybe give it a try.)
## Post #8
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-24T14:03:39+00:00
- Post Title: [HELP]Bones in noesis

> Reply from shakotay2
>
> Don't have much time today, as you may know. Will look in here in three days or so to see you progress.
(If you don't have the skeleton then I maybe give it a try.)

Challenge acepted! and thaks for all the help!
I'll be posting the progress.
## Post #9
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-26T17:11:30+00:00
- Post Title: [HELP]Bones in noesis

Ok, I've failed.
It turns out, the position of each bone is relative to the position and orientation of its parent (as far as i know) and noesis requires a global location and orientation to place a bone (as far as i know).

I'm still not able to deduce what do i have to place in the 3 first vector's 3 noesis asks me (the last one is position, thats the only vec3 i know) so, here i am, with no knowledge of how to instance a bone properly and needing to translate local position and orientation to global (without knowing how).

Leisure suit larry: magna cum laude, a sh*@#!ty game in all of its ambits
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-26T20:48:54+00:00
- Post Title: [HELP]Bones in noesis

> Reply from Repeperilka
>
> It turns out, the position of each bone is relative to the position and orientation of its parent (as far as i know) and noesis requires a global location and orientation to place a bone (as far as i know).well, as I wrote, simplest way here is using smd (you could have build the hierarchy at least  )
I ignored the head's face bones and didn't calculate the euler angles so far, so the skeleton looks a little bit weird but not wrong:
(so smd seems to support relative positions?)



LeisureSweetLarry_skel_without_rotation.png (66.66 KiB) Viewed 367 times



```
nodes
0 "ROOTR" -1
1 "Bip01 PELVISR" 0
2 "Bip01 SpineR"  1
3 "Bip01 Spine1R" 2
4 "Bip01 Spine2R" 3
5 "Bip01 NeckR" 4
6 "Bip01 HeadR" 5
7 "Bip01 LClavicR" 5
8 "Bip01 LUPArmR" 7 
9 "Bip01 L4armR" 8
10 "Bip01 LHandR" 9 
11 "Bip01 LFing0R" 10
12 "Bip01 LFing01R" 10
13 "Bip01 LFing1R" 10 
14 "Bip01 LFing11R" 13
15 "Bip01 LFing2R" 10 
16 "Bip01 LFing21R" 15
17 "Bip01 RClavicR" 5 
18 "Bip01 RUPArmR" 17 
19 "Bip01 R4armR" 18
20 "Bip01 RHandR" 19 
21 "Bip01 RFing0R" 20 
22 "Bip01 RFing01R" 20 
23 "Bip01 RFing1R" 22 
24 "Bip01 RFing11R" 23
25 "Bip01 RFing2R" 20 
26 "Bip01 RFing21R" 25
27 "Bip01 RBREASTR" 4
28 "Bip01 LBREASTR" 4
29 "Bip01 LTHIGHR" 2
30 "Bip01 LCALFR" 29
31 "Bip01 LFOOTR" 30
32 "Bip01 LTOE0R" 31
33 "Bip01 RTHIGHR" 2
34 "Bip01 RCALFR" 33
35 "Bip01 RFOOTR" 34
36 "Bip01 RTOE0R" 35
end
skeleton
time 0
0 -0.000000 -0.037779 0.941825 0.000000 0.000000 0.000000
1 0.005879 -0.000000 0.000000 0.000000 0.000000 0.000000
2 0.092884 -0.006639 0.000000 0.000000 0.000000 0.000000
3 0.120631 -0.000069 -0.000000 0.000000 0.000000 0.000000
4 0.092234 -0.000121 -0.000000 0.000000 0.000000 0.000000
5 0.152646 -0.000049 -0.000000 0.000000 0.000000 0.000000
6 0.064642 0.000000 -0.000000 0.000000 0.000000 0.000000
7 -0.010758 -0.006238 0.028261 0.000000 0.000000 0.000000
8 0.104971 -0.000000 0.000000 0.000000 0.000000 0.000000
9 0.210644 0.000000 0.000000 0.000000 0.000000 0.000000
10 0.244347 0.000000 0.000000 0.000000 0.000000 0.000000
11 0.025516 0.011878 -0.020037 0.000000 0.000000 0.000000
12 0.049868 -0.000000 0.000000 0.000000 0.000000 0.000000
13 0.070766 -0.003528 -0.017944 0.000000 0.000000 0.000000
14 0.026103 0.000000 -0.000000 0.000000 0.000000 0.000000
15 0.071649 -0.008364 0.011344 0.000000 0.000000 0.000000
16 0.031654 0.000000 0.000000 0.000000 0.000000 0.000000
17 -0.010758 -0.006237 -0.028261 0.000000 0.000000 0.000000
18 0.104971 -0.000000 -0.000000 0.000000 0.000000 0.000000
19 0.210644 0.000000 0.000000 0.000000 0.000000 0.000000
20 0.244347 -0.000000 0.000000 0.000000 0.000000 0.000000
21 0.025516 0.011878 0.020037 0.000000 0.000000 0.000000
22 0.049868 0.000000 -0.000000 0.000000 0.000000 0.000000
23 0.070766 -0.003528 0.017944 0.000000 0.000000 0.000000
24 0.026103 0.000000 -0.000000 0.000000 0.000000 0.000000
25 0.071649 -0.008364 -0.011344 0.000000 0.000000 0.000000
26 0.031654 0.000000 0.000000 0.000000 0.000000 0.000000
27 0.048754 0.029431 0.052177 0.000000 0.000000 0.000000
28 0.048754 0.029431 -0.052177 0.000000 0.000000 0.000000
29 -0.087976 0.030522 0.080747 0.000000 0.000000 0.000000
30 0.380881 0.000000 -0.000000 0.000000 0.000000 0.000000
31 0.470874 -0.000000 0.000000 0.000000 0.000000 0.000000
32 0.094716 0.129962 0.000000 0.000000 0.000000 0.000000
33 -0.087976 0.030523 -0.080747 0.000000 0.000000 0.000000
34 0.380881 0.000000 -0.000000 0.000000 0.000000 0.000000
35 0.470874 -0.000000 0.000000 0.000000 0.000000 0.000000
36 0.094716 0.129962 0.000000 0.000000 0.000000 0.000000
end
```
## Post #11
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-27T13:11:40+00:00
- Post Title: [HELP]Bones in noesis

So, i got the same resoult when I made the script to get the local position relative to the parent of the bone (I did not do it relative to the parents orientation because i had no idea of how to do that) with this script: 

```
import math

def registerNoesisTypes():
	handle = noesis.register("Leisure Suit Larry_AKCf", ".AKCf")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)

	noesis.logPopup()
	return 1
	
def noepyCheckType(data):
	if len(data) < 8:
		return 0
	j = NoeBitStream(data)
	if j.readUInt() != 0x54746F52:
		return 0
	return 1
	
def noepyLoadModel(data, mdlList):
	f = NoeBitStream(data)
	sizeOfFile = f.getSize()
	f.seek(0x23, NOESEEK_ABS)
	bonePositions = []
	for i in range(0, sizeOfFile):
		byte = f.readByte()
		if byte == 0x52:
			bonePositions.append(f.tell() - 1)
	listOfItemsToPop = []
	for i in range(0, len(bonePositions)):
		f.seek(bonePositions[i] + 1, NOESEEK_ABS)
		nextByte = f.readByte()
		if (nextByte != 0x6F):
			listOfItemsToPop.append(i)
	for i in reversed(listOfItemsToPop):
		bonePositions.pop(i)
	#each bone
	bones = []
	bonesPref = []
	for i in range(0, len(bonePositions)):
		f.seek(bonePositions[i] + 0x12, NOESEEK_ABS)
		boneName = f.readBytes(TillHex(f.tell(), 0x22, data)).decode("ASCII")
		print("-------" + boneName + "-------")
		f.seek(TillHexPos(f.tell(), 0x50, data) + 0x9, NOESEEK_ABS)
		stringPosition = f.readBytes(TillHex(f.tell(), 0x0d, data)).decode("ASCII")
		print("Position = " + stringPosition)
		f.seek(TillHexPos(f.tell(), 0x4f, data) + 0xc, NOESEEK_ABS)
		stringOrientation = f.readBytes(TillHex(f.tell(), 0x0d, data)).decode("ASCII")
		print("Orientation = " + stringOrientation)
		f.seek(0x4, NOESEEK_REL)
		parentName = ""
		localDrawing = ""
		check = f.readByte()
		if check == 0x50:
			f.seek(0x7, NOESEEK_REL)
			parentName = f.readBytes(TillHex(f.tell(), 0x22, data)).decode("ASCII")
			print("Parent = " + parentName)
			f.seek(0x1B, NOESEEK_REL)
			localDrawing = f.readBytes(TillHex(f.tell(), 0x0D, data)).decode("ASCII")
			boneMatrix = FixLocalDrawing(stringPosition, parentName, bonesPref)
			bonesPref.append(BoneDef(i, boneName, boneMatrix[0], boneMatrix[1], boneMatrix[2], boneMatrix[3], parentName))
			bones.append(NoeBone(i, boneName, NoeMat43((boneMatrix[0], boneMatrix[1], boneMatrix[2], boneMatrix[3])), parentName))
		elif check == 0x4C:
			f.seek(0x15, NOESEEK_REL)
			localDrawing = f.readBytes(TillHex(f.tell(), 0x0D, data)).decode("ASCII")
			boneMatrix = FixLocalDrawing(stringPosition, "", bonesPref)
			bonesPref.append(BoneDef(i, boneName, boneMatrix[0], boneMatrix[1], boneMatrix[2], boneMatrix[3]))
			bones.append(NoeBone(i, boneName,  NoeMat43((boneMatrix[0], boneMatrix[1], boneMatrix[2], boneMatrix[3]))))
	mdl = NoeModel([], bones, [])
	mdlList.append(mdl)
	return 1
	
def TillHex (startIndex, hexToStop, data):
	f = NoeBitStream(data)
	f.seek(startIndex, NOESEEK_ABS)
	hex = 0x0
	Number = 0
	while hex != hexToStop:
		hex = f.readByte()
		Number = Number + 1
	f.seek(startIndex, NOESEEK_ABS)
	return Number - 1
	
def TillHexPos (startIndex, hexToStop, data):
	f = NoeBitStream(data)
	f.seek(startIndex, NOESEEK_ABS)
	hex = 0x0
	while hex != hexToStop:
		hex = f.readByte()
	f.seek(-0x1, NOESEEK_REL)
	return f.tell()

def FixLocalDrawing (stringNum, parentName, list):
	arrayOfString = stringNum.split(' ')
	arrayOfFloats = []
	for i in arrayOfString:
		if i != "":
			floats = float(i)
			arrayOfFloats.append(floats)
	if parentName != "":
		vec3Parent = GetParentPos(parentName, list)
		vx = vec3Parent[0] + arrayOfFloats[0]
		vy = vec3Parent[1] + arrayOfFloats[1]
		vz = vec3Parent[2] + arrayOfFloats[2]
		vec3 = NoeVec3((vx, vy, vz))
		print("Local vec = " + str(vec3))
	else:
		vec3 = NoeVec3((arrayOfFloats[0], arrayOfFloats[1],arrayOfFloats[2]))
		print("Non-Local vec = " + str(vec3))
	veczero = NoeVec3((0, 0, 0))
	return [veczero, veczero, veczero, vec3]
	
def FixVector3 (splitVector):
	vxf = float(splitVector[0])
	vyf = float(splitVector[1])
	vzf = float(splitVector[2])
	return NoeVec3((vxf, vyf, vzf))
		

def toEuler (qx, qy, qz, qw):
	sinr_cosp = 2 * (qw * qx + qy * qz)
	cosr_cosp = 1 - 2 * (qx * qx + qy * qy)
	roll = math.atan2(sinr_cosp, cosr_cosp)
	
	sinp = 2 * (qw * qy - qz * qx)
	pitch = 0
	if math.fabs(sinp) >= 1:
		pitch = math.copysign(math.pi / 2, sinp)
	else:
		pitch = math.asin(sinp)
	
	siny_cosp = 2 * (qw * qz + qx * qy)
	cosy_cosp = 1 - 2 * (qy * qy + qz * qz)
	yaw = math.atan2(siny_cosp, cosy_cosp)
	
	return NoeVec3((roll, pitch, yaw))
	
def GetParentPos (parentName, list):
	for i in list:
		if i.GetName() == parentName:
			return i.GetPos()
	return 0

class BoneDef:
	def __init__(self, index, name, v1, v2, v3, v4, parentName = "", parentIndex = -1):
		self.index = index
		self.name = name
		self.v1 = v1
		self.v2 = v2
		self.v3 = v3
		self.v4 = v4
		self.parentName = parentName
		self.parentIndex = parentIndex #parent index may be specified instead of parentName, if it's more convenient. this is an index corresponding to self.index, and not the position in the list.
	def __repr__(self):
		return "(NoeBone:" + repr(self.index) + "," + self.name + "," + repr(self.parentName) + "," + repr(self.parentIndex) + ")"

	def GetPos (self):
		return self.v4
	def GetName (self):
		return self.name
```


But still, the noesis exporter does some pretty weird things so, i went with the .smd approach.
It went well, i just had to write the local position and rotation in euler angles and i got a nice viped rigg (but not in the right position, for some reason):
[](https://ibb.co/nkVssDB)
[goat kid name](https://babynamesetc.com/animal)

And it does not import well to me in blender:
[](https://ibb.co/J5w4BW8)

And when i drag the archive to the 3d model in noesis i get this error:

```
Parsing/indexing SMD.
Error: Unexpected syntax in skeleton definition.
Converting SMD animation (45 bones, 1 frames)...
Conversion finished.
Freed 4.00MB in temporary pools.
```


And here is the .smd:

```
nodes
0 "ROOTR" -1
1 "PELVISR" 0
2 "SPINER" 1
3 "SPINE1R" 2
4 "SPINE2R" 3
5 "NECKR" 4
6 "HEADR" 5
7 "EYEBROWR" 6
8 "JAWR" 6
9 "HAIRBN1R" 6
10 "HAIRBN2R" 9
11 "REYER" 6
12 "LEYER" 6
13 "LEYELASR" 6
14 "REYELASR" 6
15 "LCLAVICR" 5
16 "LUPARMR" 15
17 "L4ARMR" 16
18 "LHANDR" 17
19 "LFING0R" 18
20 "LFING01R" 19
21 "LFING1R" 18
22 "LFING11R" 21
23 "LFING2R" 18
24 "LFING21R" 23
25 "RCLAVICR" 5
26 "RUPARMR" 25
27 "R4ARMR" 26
28 "RHANDR" 27
29 "RFING0R" 28
30 "RFING01R" 29
31 "RFING1R" 28
32 "RFING11R" 31
33 "RFING2R" 28
34 "RFING21R" 33
35 "RBREASTR" 4
36 "LBREASTR" 4
37 "LTHIGHR" 2
38 "LCALFR" 37
39 "LFOOTR" 38
40 "LTOE0R" 39
41 "RTHIGHR" 2
42 "RCALFR" 41
43 "RFOOTR" 42
44 "RTOE0R" 43
end
skeleton
time 0
0 -0.0 -0.037779 0.941825 0.0 0.0 1.5707941172651394
1 0.005879 -0.0 0.0 1.5707943267968967 2.0000000000033334e-06 1.5707963267948966
2 0.092884 -0.006639 0.0 3.7037300000201016e-06 2.5064700000026246e-06 -0.26259588738603606
3 0.120631 -6.9e-05 -0.0 0.0 -0.0 0.3490655599644922
4 0.092234 -0.000121 -0.0 -0.0 0.0 0.08726566640436267
5 0.152646 -4.9e-05 -0.0 0.0 0.0 -0.3228867016719503
6 0.064642 0.0 -0.0 0.0 -0.0 0.17533051221628268
7 0.12366 0.080853 0.000329 -0.00838276146428265 -0.000277867983575727 -1.6053664218767245
8 0.050846 0.036597 0.0 -3.3059800000144034e-06 2.251776000001903e-06 -1.9457054908065088
9 0.071848 -0.040862 -0.0 -1.9082760000015003e-06 -5.987340000000358e-07 2.533534268317497
10 0.092461 -2e-06 0.0 0.0 0.0 0.5466261657586431
11 0.096699 0.070851 -0.032818 -0.0 0.0 -0.0
12 0.096699 0.070851 0.032603 -0.0 0.0 -0.0
13 0.092774 0.078773 0.034549 0.0 0.0 0.0
14 0.092774 0.078773 -0.034373 0.0 0.0 0.0
15 -0.010758 -0.006238 0.028261 -0.8895529417491586 -1.1631126325120917 -2.210626473071723
16 0.104971 -0.0 0.0 -0.1447126119470553 -0.4940500583945059 -0.12842003952981776
17 0.210644 0.0 0.0 0.0 -0.0 0.2835307232253701
18 0.244347 0.0 0.0 1.5699971158707204 0.061087917831116084 -4.843615543905436e-05
19 0.025516 0.011878 -0.020037 -1.5845855793778945 -0.17148418981320346 0.4526159807369817
20 0.049868 -0.0 0.0 -0.0 0.0 0.0
21 0.070766 -0.003528 -0.017944 -0.08674869817975676 -0.08706727141720391 0.004578741881316081
22 0.026103 0.0 -0.0 0.0 -0.0 -0.15707938774013466
23 0.071649 -0.008364 0.011344 0.08798677237884742 0.08659639641996507 -0.08879867630727252
24 0.031654 0.0 0.0 0.0 0.0 -0.08726566640436267
25 -0.010758 -0.006237 -0.028261 0.8895502788854442 1.1631129218353915 -2.2106238175619817
26 0.104971 -0.0 -0.0 0.1447126119470553 0.4940500583945059 -0.12842003952981776
27 0.210644 0.0 0.0 -0.0 0.0 0.2835307232253701
28 0.244347 -0.0 0.0 -1.5699971158707204 -0.061087917831116084 -4.843615543905436e-05
29 0.025516 0.011878 0.020037 1.5845855604084207 0.17148463183047183 0.4526161588380579
30 0.049868 0.0 -0.0 -0.0 0.0 0.0
31 0.070766 -0.003528 0.017944 0.08674869817975676 0.08706727141720391 0.004578741881316081
32 0.026103 0.0 -0.0 0.0 0.0 -0.15707938774013466
33 0.071649 -0.008364 -0.011344 -0.08798677237884742 -0.08659639641996507 -0.08879867630727252
34 0.031654 0.0 0.0 0.0 -0.0 -0.08726566640436267
35 0.048754 0.029431 0.052177 -0.1905763330741936 -0.06378299784109394 -1.802639380384352
36 0.048754 0.029431 -0.052177 0.1905734784263502 0.06378266314451013 -1.8026392302418905
37 -0.087976 0.030522 0.080747 3.112654902662217 0.07330415091977466 2.929806735251053
38 0.380881 0.0 -0.0 0.0 -0.0 0.011946069104648498
39 0.470874 -0.0 0.0 0.029818660586333007 0.0803028870308345 -0.06090888778813026
40 0.094716 0.129962 0.0 0.0 0.0 -1.5707969456925137
41 -0.087976 0.030523 -0.080747 -3.112661088956378 -0.07330279041614685 2.929806952563134
42 0.380881 0.0 -0.0 0.0 0.0 0.011946069104648498
43 0.470874 -0.0 0.0 -0.029818660586333007 -0.0803028870308345 -0.06090888778813026
44 0.094716 0.129962 0.0 -0.0 0.0 -1.5707969456925137
end
```
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-27T13:50:36+00:00
- Post Title: [HELP]Bones in noesis

> Reply from Repeperilka
>
> So, i got the same resoult when I made the script to get the local position relative to the parent of the bonewell, I see  

> But still, the noesis exporter does some pretty weird things so, i went with the .smd approach.well, Noesis isn't that bad and it displays the smd skeleton, but it's too hard to start with skeleton import code, imho.

> And when i drag the archive to the 3d model in noesis i get this error:
>
> Code: Select allAttempting to extract bones/animations from C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR - copia\GIRLACTRsmd.smd...
>
> Parsing/indexing SMD.
>
> Error: Unexpected syntax in skeleton definition.
>
> Converting SMD animation (45 bones, 1 frames)...
>
> Conversion finished.
>
> Freed 4.00MB in temporary pools.Nothing to worry about. Seems you simply missed the carriage return (enter)  at smd file's end.

> And it does not import well to me in blender:using source engine smd importer does well for me:



Larry_skel_in_blender.png (65.22 KiB) Viewed 352 times
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-12-30T16:00:32+00:00
- Post Title: [HELP]Bones in noesis

Maybe this help for akc to smd converter:

Quaternion rotation   try convert to matrix than invert this matrix and than convert inverted matrix to euler

Pyhon code for Blender version 249. 
Sometimes i  use separate matrices for bone position and rotation.
(bone matrice (4x4) = bone rotation matrice (4x4) * bone position matrice (4x4))

Useless for Noesis .
I don't know how this code tranform to Noesis code. i tried but no luck.

```


def akcParser(filename,g):

	skeleton=Skeleton()	
	lines=g.readlines()
	boneCount=lines[0].strip().split('[')[1].split(']')[0]	
	boneCount=int(boneCount)
	id=4
	for m in range(boneCount):
		line=lines[id].strip()
		id+=1
		if 'RotTransCoordSys' in line:
			bone=Bone()
			skeleton.boneList.append(bone)
			bone.name=line.split('"')[1]
			while(True):
				line=lines[id].strip()
				id+=1
				if '}' in line:break
				if 'Position' in line:
					floatarray=map(float,line.split('Position')[1].split())
					bone.posMatrix=VectorMatrix(floatarray)
				if 'Orientation' in line:
					floatarray=map(float,line.split('Orientation')[1].split())
					bone.rotMatrix=QuatMatrix(floatarray).resize4x4().invert()# QuatMatrix is function to convert quat to matrices 3x3
				if 'Parent' in line:
					bone.parentName=line.split('"')[1]
		else:
			break
	skeleton.draw()		
```

[bones.jpg](https://xentaxbackup.github.io/file/15401_bones.jpg)
