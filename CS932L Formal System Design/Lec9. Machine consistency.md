# Definition, ==Invariant==:
1.  Defines properties of a specification should adhere to
2. The specification must uphold these invariants.
3. The invariant should be true right from the start, i.e., after initialisation. 
# Initialization
` INITIALISATION inside := {} || maxin := 500 `
## Expression
Basic Initialisation Condition
1. For initialisation init and invariant I: `[init]I`
2. For invariant I, precondition Pre and operation body S: `I ∧ Pre ⇒ [S]I`
3. 