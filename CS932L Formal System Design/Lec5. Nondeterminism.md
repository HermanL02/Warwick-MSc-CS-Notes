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
