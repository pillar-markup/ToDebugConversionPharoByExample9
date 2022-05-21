## Collections 
	select: [ :each | each gpa < threshold ]
>>> #(1)
>>> #(1 2)
>>> #(1 2 3)
>>> #(1 2 3 4)
>>> #(1 2 3 4 5)
>>> #(1 2 3 4 5 6)
>>> an OrderedCollection(1 2 3 4 5 6 7 8)
>>> #(7 3 1 3)
>>> an OrderedCollection(7 3 1 3)
>>> a SortedCollection(1 3 3 7)
>>> a Set(7 1 3)
>>> a Bag(7 1 3 3)
anArray := Array new: 5.
anArray at: 1 put: 4.
anArray at: 2 put: 3/2.
anArray at: 3 put: 'ssss'.
anArray at: 1
>>> 4
new: 5` creates an array of size 5. 
>>>  {4. (3/2). 'lulu'}
>>> 2
>>>  #(1 #+ 2)
>>> #(3)
>>> 0.5
>>> (1/3)
anArray := #(1 2 3 4 5 6) copy.
anArray at: 3 >>> 3
anArray at: 3 put: 33.
anArray at: 3
>>> 33
ordCol := OrderedCollection new.
ordCol add: 'Seaside'; add: 'SmalltalkHub'; addFirst: 'GitHub'.
ordCol
>>> an OrderedCollection('GitHub' 'Seaside' 'SmalltalkHub')
ordCol remove: 'GitHub'.
ordCol
>>> an OrderedCollection('Seaside' 'SmalltalkHub' 'GitHub')
result
>>> 33
>>> an OrderedCollection(1 2 3)
>>> an OrderedCollection($h $e $l $l $o)
>>> (1 to: 100)
>>> true
>>> 199
>>> 99.5
>>> (15/2)
colors := Dictionary new.
colors at: #yellow put: Color yellow.
colors at: #blue put: Color blue.
colors at: #red put: Color red.
colors at: #yellow
>>> Color yellow
>>> #(#red #blue #yellow)
>>> {Color red . Color blue . Color yellow}
colors := Dictionary newFrom: { #blue->Color blue . #red->Color red . #yellow->Color yellow }.
colors removeKey: #blue.
colors associations
>>> {#yellow->Color yellow. #red->Color red}
b := a copy.
trouble := IdentityDictionary new.
trouble at: a put: 'a'; at: b put: 'b'.
trouble at: a
>>> 'a'
>>> 'b'
>>> 'a'
>>> a Set(ByteSymbol)
s add: 4/2; add: 4; add:2.
s size
>>> 2
>>> true
>>> 2
>>> 3
>>> a Set(1 2 3 4 5 6 7 8 9 10)
>>> 'eh'
>>> true
>>> a SortedCollection(-10 2 5 50)
>>> a SortedCollection(-10 2 5 50)
>>> a SortedCollection($e $h $l $l $o)
>>> 'a SortedCollection($e $h $l $l $o)'
>>> 'ehllo'
>>> 'ehllo'
>>> 'ehllo'
>>> a SortedCollection((-2/3) 5 5.21)
         sortBlock: [ :c1 :c2 | c1 luminance <= c2 luminance ].
col addAll: { Color red . Color yellow . Color white . Color black }.
col
>>> a SortedCollection(Color black Color red Color yellow Color white)
>>> 'Hello'
>>> 'A'
>>> 'hi!'
>>> 'hello'
>>> $'
>>> $i
s
>>> 'no worries'
s
>>> 'no hurries'
>>> #(1 2 3 $4 $5)
s
>>> 'No hurries'
s
>>> 'No worries'
>>> 'No wombats'
>>> #(1 2 'three' 'etc.' 6)
>>> true
>>> true
>>> $b
>>> $a
>>> 'alpha'
>>> 'habet'
>>> 'abe'
>>> 'p' (not $p)
>>> false
>>> false
>>> false
>>> true
>>> 'Pharo is cool'
>>> 'look-   -here'
>>> 'Pharo is cool'
>>> 'cool is Pharo'
>>> '''Pharo'' or Pharo'
>>> 'Quentin plays'
>>> 'Thibaut plays'
>>> 'xyz'
>>> 'XYZ'
>>> 'Tintin'
>>> 'tintin'
>>> 1.54
>>> 'this sent...too long'
>>> '#ASymbol'
>>> 'ASymbol'
    doWithIndex: [ :each :i | (each = 'joe') ifTrue: [ ^ i ] ]
>>> 2
res := ''.
#('bob' 'joe' 'toto')
   do: [ :e | res := res, e ]
   separatedBy: [ res := res, '.' ].
res
>>> 'bob.joe.toto'
   #('bob' 'joe' 'toto') asStringOn: stream delimiter: '.' ]
>>> 'bob.joe.toto'
colors keysDo: [ :key | Transcript show: key; cr ].
colors valuesDo: [ :value | Transcript show: value; cr ].
colors associationsDo: [:value | Transcript show: value; cr].
double := OrderedCollection new.
#(1 2 3 4 5 6) do: [ :e | double add: 2 * e ].
double
>>> an OrderedCollection(2 4 6 8 10 12)
>>> #(2 4 6 8 10 12)
result := aCol species new: aCol size.
1 to: aCol size do: [ :each |
	result at: each put: (aCol at: each) abs ].
result
>>> #(2 3 4 35 4 11)
>>> #(2 3 4 35 4 11)
>>> "error!"
>>> #(97 98 99)
>>> #(2 4 6 8 10)
>>> #(2 3 5 7 11 13 17 19)
>>> #(4 6 8 9 10 12 14 15 16 18 20)
>>> $o
    detect: [:each | '*cobol*' match: each asString]
    ifNone: [ nil ]
>>> nil
>>> 5050
	(1 to: n) 
		inject: 1 
		into: [ :product :each | product * each ] ].
factorial value: 10
>>> 3628800
   count: [ :each | 'Collection*' match: each asString ]
>>> 10
colors := {Color white . Color yellow .  Color blue . Color orange}.
colors includes: Color blue.
>>> true
>>> true
collection := OrderedCollection new add: 1; add: 2.
collection
>>> 2
collection := OrderedCollection new.
collection add: 1; add: 2.
collection
>>> an OrderedCollection(1 2)
collection := OrderedCollection new add: 1; add: 2; yourself
>>> an OrderedCollection(1 2)
range := (2 to: 20) asOrderedCollection.
range do: [ :aNumber | aNumber isPrime
                            ifFalse: [ range remove: aNumber ] ].
range
>>> "error!"
range := (2 to: 20) asOrderedCollection.
range copy do: [ :aNumber | aNumber isPrime
                              ifFalse: [ range remove: aNumber ] ].
range
>>> an OrderedCollection(2 3 5 7 11 13 17 19)
   self class = aBook class ifFalse: [ ^ false ].
   ^ title = aBook title and: [ authors = aBook authors ]

Book >> hash
   ^ title hash bitXor: authors hash