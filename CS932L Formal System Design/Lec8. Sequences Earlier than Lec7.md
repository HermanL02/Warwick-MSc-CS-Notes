# Sequence
1. Not just a set
2. Tracks may be repeated
3. order is important
## Modelling 
### As a function
Uniquely identify the position
[tt3,tt27,tt14,tt3,tt8]
first track: tt3, second: tt27...
n-long sequence -> as function -> from 1...n
==Reordering and repeating== elements in the set gives ==exactly the same set and same sequence==
### As an operation
Has the special property that the domain is exactly 1 . . n
## Notation
The set of all finite sequences with elements of type X:
seq(X) = {f | f ∈ N1 7→ X ∧ dom(f ) = 1 . . card(f )}
The set of all non-empty seqs with elements of type X:
seq 1(X) = seq(X) − {[]}
The set of all injective sequences with elements of type X:
iseq(X) = seq(X) ∩ (N  X)
The set of all seqs in which each element of X occurs exactly once:
perm(X) = 

## Declaring sequences
playlist ∈ seq(TRACK)
game ∈ seq1(MOVE)
checkout ∈ iseq(PERSON)
presentations ∈ perm(STUDENT)




