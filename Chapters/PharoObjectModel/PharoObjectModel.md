## The Pharo object model
>>> 7
>>> 2432902008176640000
>>> '24 July 2021'
Date allInstVarNames 
>>> #(#start #duration)
>>> SmallInteger
>>> LargePositiveInteger
>>> ByteString
>>> Point
>>> Object
    "Answer the distance between aPoint and the receiver."

    | dx dy |
    dx := aPoint x - x.
    dy := aPoint y - y.
    ^ ((dx * dx) + (dy * dy)) sqrt
>>> 5.0
>>> Integer
>>> Number
>>> Magnitude
>>> Object
>>> ProtoObject
>>> nil
	instanceVariableNames: 'x y'
	classVariableNames: ''
	package: 'Kernel-BasicObjects'
>>> 7         
>>> 5@6
>>> Color yellow
     "Answer the default color/fill style for the receiver"
     ^ Color yellow
     "Add this morph to the world."
     self openInWorld: self currentWorld
	^ self intersectionWithLineSegmentFromCenterTo: aPoint
    "Add this morph to the world."
    self openInWorld: self currentWorld
    ^ self
    "Initialize the state of the receiver"

    super initialize.
    self borderInitialize
	aStream nextPutAll: self class name, ' new'
    ^ String streamContents: [ :s | self fullPrintOn: s  ].
    aStream nextPutAll: '('.
    super fullPrintOn: aStream.
    aStream
        nextPutAll: ') setBorderWidth: ';
        print: borderWidth;
        nextPutAll: ' borderColor: ', (self colorString: borderColor)
>>> '(EllipseMorph new) setBorderWidth: 1 borderColor: Color black'
>>> Color blue
"Color instances are self-evaluating"
>>> 0.0
>>> 1.0
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'Example'
    instanceVariableNames: 'count'
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'Example'
    count := 0.
    count := count +1.
    ^ super new
    ^ count
Hyena initialize.
Dog count
>>> 0
>>> 0
aDog := Dog new.
Dog count
>>> 1  "Incremented"
>>> 0  "Still the same"
    instanceVariableNames: 'sessions'
    classVariableNames: ''
    package: 'Web'
    instanceVariableNames: 'uniqueInstance'
>>>  "#(#superclass #methodDict #format #layout #organization #subclasses #name #classPool #sharedPools #environment #category)"
>>>  "#(#superclass #methodDict #format #layout #organization #subclasses #name #classPool #sharedPools #environment #category #uniqueInstance)"
     uniqueInstance ifNil: [ uniqueInstance := self new ].
     ^ uniqueInstance
>>> ProcessorScheduler
>>> Boolean
>>> Smalltalk
>>> true
	instanceVariableNames: 'rgb cachedDepth cachedBitPattern alpha'
	classVariableNames: 'BlueShift CachedColormaps ColorRegistry ComponentMask ComponentMax GrayToIndexMap GreenShift HalfComponentMask IndexedColors MaskingMap RedShift'
	package: 'Colors-Base'
   ^ ColorNames
    ...
    self initializeColorRegistry.
    ...
        instanceVariableNames: 'string runs'
        classVariableNames: ''
        poolDictionaries: 'TextConstants'
        package: 'Collections-Text'
    ^ CR == Character cr
	instanceVariableNames: ''
	classVariableNames: 'BS BS2 Basal Bold CR Centered Clear CrossedX CtrlA CtrlB CtrlC 
	CtrlD CtrlDigits CtrlE CtrlF CtrlG CtrlH 
	CtrlI CtrlJ CtrlK CtrlL CtrlM CtrlN CtrlO CtrlOpenBrackets CtrlP CtrlQ CtrlR CtrlS CtrlT 
	CtrlU CtrlV CtrlW CtrlX CtrlY CtrlZ Ctrla Ctrlb Ctrlc Ctrld Ctrle Ctrlf Ctrlg Ctrlh Ctrli 
	Ctrlj Ctrlk Ctrll Ctrlm Ctrln Ctrlo Ctrlp Ctrlq Ctrlr Ctrls Ctrlt Ctrlu Ctrlv Ctrlw 
	Ctrlx Ctrly Ctrlz DefaultBaseline DefaultFontFamilySize DefaultLineGrid DefaultMarginTabsArray 
	DefaultMask DefaultRule DefaultSpace DefaultTab DefaultTabsArray ESC EndOfRun Enter Italic 
	Justified LeftFlush LeftMarginTab RightFlush RightMarginTab Space Tab TextSharedInformation'
	package: 'Text-Core-Base'
    "Answer whether the receiver is less than the argument."

    ^self subclassResponsibility
    "Answer whether the receiver is greater than or equal to the argument."

    ^(self < aMagnitude) not
    "Answer true if the receiver's value < aCharacter's value."

    ^self asciiValue < aCharacter asciiValue