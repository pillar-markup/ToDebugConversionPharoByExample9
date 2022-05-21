## Understanding message syntax
>>> 0.860069405812453
>>> 1.732050807568877
>>> 3.141592653589793
>>> 4
>>> false
>>> Object class  "The class of Object is Object class (BANG)"
>>> 100@100  "creates a Point object"
>>> 7
>>> 9
>>> false
>>> true  "equality is just a binary message, and Fractions are exact"
>>> false  "two equal Fractions are not the same object"
>>> true
>>> Color red  "creates a new color"
>>> (1 to: 10)  "creates an interval"
nums := Array newFrom: (1 to: 5).
nums at: 1 put: 6.
nums
>>> #(6 2 3 4 5)
>>> 1000
>>> 128
>>> 9
>>> 7
>>> an IdentitySet(#or: #| #and: #& #ifTrue: #ifTrue:ifFalse: #ifFalse: #not #ifFalse:ifTrue:)
         aPen color: Color yellow
(1)         Color yellow         "unary message is sent first"
               >>> aColor
(2)         aPen color: aColor   "keyword message is sent next"
(1)         100 + 20         "binary message first"
               >>>   120
(2)         aPen go: 120     "then keyword message"
>>> true
>>> 27    "(not 5040)"
>>> 5040
"(1) send the message clarinet to the FMSound class to create a clarinet sound.
 (2) send this sound to FMSound as argument to the lowMajorScaleOn: keyword message.
 (3) play the resulting sound."
      (65@325 extent: 134@100) center
(1)   65@325                                                    "binary"
    >>> aPoint
(2)                                134@100                     "binary"
                                 >>> anotherPoint
(3)   aPoint extent: anotherPoint                       "keyword"
      >>> aRectangle
(4)   aRectangle center                                     "unary"
      >>> 132@375
>>> 35    "(not 23)  Binary messages sent from left to right"
>>> 23
>>> (2/3)    "and not 4/3"
>>> (4/3)
>>> (7/9)    "and not 1"
>>> 1

     20 + 2 * 5
(1)  20 + 2 >>> 22
(2)  22     * 5 >>> 110
"The messages surrounded by parentheses are evaluated first therefore * is sent prior 
to + which produces the correct behaviour."

    20 + (2 * 5)
(1)      (2 * 5) >>> 10
(2) 20 + 10      >>> 30
   at: (rotatingForm
          rotateBy: angle
          magnify: 2
          smoothing: 1)
   put: 3
   ifTrue:[...]
(ord includes: $a)
   ifTrue:[...]
4 timesRepeat: [ Beeper beep ]              "the argument is evaluated more than once, so must be a block"
(x isReady) ifTrue: [ y doSomething ]       "receiver is evaluated once, so is not a block
                                            argument does not have to be evaluated not even once, 
											so it is a block"
box := 20@30 corner: 60@90.
box containsPoint: 40@50 
>>> true
Transcript show: 'fun '.
Transcript cr.
   show: 'Pharo is';
   show: 'fun ';
   cr
>>> false