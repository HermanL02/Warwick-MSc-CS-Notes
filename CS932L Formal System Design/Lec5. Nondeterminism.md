# Abstraction
1. A main benefit of specification e.g. use an abstract data type to describe a state component
2. Separation of concerns e.g. we state that we find a max value in an array, but we don't say how
3. Proofs easier, less detail
4. **Nondeterminism**
# Nondeterminism
A given start state -> A number of possible end states
Details filled in by refinement
E.g. **xx = 3 compared with xx ∈ {1, 3, 5, 7, 9}**
- 这是一个例子。第一个表达式“xx = 3”是明确的，而第二个表达式“xx ∈ {1, 3, 5, 7, 9}”则是不明确的，因为xx可以是集合中的任何一个数。
E.g. 2 **Eg2: ran(sseq) = sset ∧ card(sseq) = card(sset)**
- 另一个例子，意味着sseq的值域（ran）等于sset，且sseq的基数（即元素数量）与sset的基数相同。
# Why useful 
newmember ∈ MID − members
```
newmember <-- join(...) =

PRE ...

THEN BEGIN newmember :: MID - members ||

	...
	
	END

END
```

# ANY statement
ANY xx WHERE C THEN B END
- xx is the (new) name of the variable you want to use - local to the ANY statement. 
- C is the condition you want xx to satisfy. It must give at least the type.
- B is an AMN description of the operation.
```
ANY xx
WHERE xx ∈ (MID − members) ∧ xx != reserved id
THEN
newmember := xx || members := members ∪ {xx}
END
```
ANY is the **generalisation** of LET
## LET statement
LET is a specific case where the variable is deterministic. 

```
LET xx
BE xx = least(MID − (members ∪ {reserved id}))
IN newmember := xx || members := members ∪ {xx}
END
```
如果我们做这个，需要Least函数: 
```
CONSTANT least
PROPERTIES least : P1 (MID) → MID
```

**A LET can always be expressed as an ANY**

`LET xx BE xx = E IN B END`

is the same as

`ANY xx WHERE xx = E THEN B END`

## Choice Statement
ANY - picks from a range of values but executes the same code regardless of the choice. 
CHOICE - allows different possible actions.

**CHOICE S1 OR S2 OR . . . OR Sn END**
Ex. Suppose PRIZE is the set of different possible prizes:
```
CHOICE message := winner || prize := 20
OR
message := free go
OR
message := loser
END
```


## Question
How could we implement . . .
```
CHOICE
flip := heads
OR
flip := tails
END
```
The following are all allowable implementations
flip:=heads
flip:=tails
pseudo-random, equal chance
pseudo-random, biased
predictable e.g. alternating

CHOICE只是一种标准，他并不在乎实际用户选择什么，所以说真正的程序中可以固定只选其中一个，也可以随机选择

# SELECT statement

Like an IF statement but conditions can overlap
```
SELECT P1 THEN S1
WHEN
P2 THEN S2
. . .
WHEN Pn THEN Sn
ELSE S
END
```
Ex. 
```
SELECT age < 21 THEN section := 7
WHEN status = student THEN section := 6
WHEN status = unemployed THEN section := 8
END
```
