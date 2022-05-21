## Streams
r := ReadStream on: (1 to: 1000).
r next.
>>> 1
>>> 2
>>> false
w := WriteStream on: (String new: 5).
w nextPut: $a.
w nextPut: $b.
w contents.
>>>  'ab'
stream := ReadStream on: #(1 (a b c) false).
stream next.
>>>   1
>>>   #(#a #b #c)
>>>   false
stream := ReadStream on: 'abcdef'.
stream next: 0.
>>>   ''
>>>   'a'
>>>   'bcd'
>>>   'ef'
stream := ReadStream on: '-143'.
"look at the first element without consuming it."
negative := (stream peek = $-).
negative.
>>> true
negative ifTrue: [ stream next ].
number := stream upToEnd.
number.
>>> '143'
stream := '-143' readStream.
(stream peekFor: $-).
>>> true
>>> '143'
stream := 'abcde' readStream.
stream position: 2.
stream peek
>>> $c
stream := 'abcdef' readStream.
stream next
>>> $a
stream position
>>>   4
stream position
>>> 2
stream position
>>> 0
stream next.
>>> $f
>>> 'abcdef'
stream1 := #(1 4 9 11 12 13) readStream.
stream2 := #(1 2 3 4 5 10 13 14 15) readStream.

"The variable result will contain the sorted collection."
result := OrderedCollection new.
[ stream1 atEnd not & stream2 atEnd not ]
  whileTrue: [
    stream1 peek < stream2 peek
        "Remove the smallest element from either stream and add it to the result."
        ifTrue: [ result add: stream1 next ]
        ifFalse: [ result add: stream2 next ] ].

"One of the two streams might not be at its end. Copy whatever remains."
result
  addAll: stream1 upToEnd;
  addAll: stream2 upToEnd.

result.
>>>   an OrderedCollection(1 1 2 3 4 4 5 9 10 11 12 13 13 14 15)
stream := String new writeStream.
stream
  nextPutAll: 'This image contains: ';
  print: Smalltalk globals allClasses size;
  nextPutAll: ' classes.';
  cr;
  nextPutAll: 'This is really a lot.'.

stream contents.
>>> 'This image contains: 9003 classes.
This is really a lot.'
string := String streamContents:
		[ :stream |
			stream
                 print: #(1 2 3);
                 space;
                 nextPutAll: 'size';
                 space;
                 nextPut: $=;
                 space;
                 print: 3.	 ].
string.
>>>   '#(1 2 3) size = 3'
  temp := String new.
  (1 to: 100000)
    do: [:i | temp := temp, i asString, ' ' ] ] timeToRun
>>> 0:00:01:54.758
  temp := WriteStream on: String new.
  (1 to: 100000)
    do: [:i | temp nextPutAll: i asString; space ].
  temp contents ] timeToRun
>>> 0:00:00:00.024
  (1 to: 100000)
       do: [:i | tempStream nextPutAll: i asString; space ] ]
	"Answer a String whose characters are a description of the receiver. 
	If you want to print without a character limit, use fullPrintString."

	^ self printStringLimitedTo: 50000
	"Answer a String whose characters are a description of the receiver.
	If you want to print without a character limit, use fullPrintString."

	^self printStringLimitedTo: limit using: [:s | self printOn: s]
	"Answer a String whose characters are a description of the receiver
	produced by given printBlock. It ensures the result will be not bigger than given limit"

	| limitedString |
	limitedString := String streamContents: printBlock limitedTo: limit.
	limitedString size < limit ifTrue: [^ limitedString].
	^ limitedString , '...etc...'
	self displayIdentifierOn: aStream.
	aStream 
		nextPutAll: ' (';
		nextPutAll: self tally printString;
		nextPutAll: ')'
	self displayIdentifierOn: aStream.
	aStream 
		nextPutAll: ' (';
		print: self tally;
		nextPutAll: ')'
	"Have anObject print itself on the receiver."

	anObject printOn: self

	^ String streamContents: [ :stream |
		stream
			nextPutAll: '"protocol: '; 
			nextPutAll: protocol printString;
			nextPut: $"; cr; cr;
			nextPutAll: sourceCode ]	

	^ String streamContents: [ :stream |
		stream
			nextPutAll: '"protocol: '; 
			print: protocol;
			nextPut: $"; cr; cr;
			nextPutAll: sourceCode ]	
  instanceVariableNames: 'stream'
  classVariableNames: ''
  package: 'PBE-Streams'

History >> initialize
    super initialize.
    stream := ReadWriteStream on: Array new
  self canGoBackward
  	ifFalse: [ self error: 'Already on the first element' ].
  stream skip: -2.
  ^ stream next.

History >> goForward
  self canGoForward
  	ifFalse: [ self error: 'Already on the last element' ].
  ^ stream next
    stream nextPut: aPage
  stream nextPut: anObject.
  stream nextPut: nil.
  stream back
  ^ stream position > 1

History >> canGoForward
  ^ stream atEnd not and: [stream peek notNil ]
  ^ stream contents
	goTo: #page1;
	goTo: #page2;
	goTo: #page3;
	goBackward;
	goBackward;
	goTo: #page4;
	contents
>>> #(#page1 #page4 nil nil)