## Operations 

 - **Before** and **after** states
 - Description rather than sequential
 - May be partial description 


## Assignment 

## Preconditioned operations 

 Operation **guarantees** correct behaviour if called when PRE is true. 
 What we need guarantee: 
 1. Types
 2. Things (e.g. No division by 0)
 3. Discounting things we don't want to make provision for here 减少其他状况的考虑
## Example of the use of both PRE and IF 
oo ← query(pp) =
	PRE pp ∈ PID
	THEN
		IF pp ∈ inside
		THEN oo := 1
		ELSE oo := 0
		END
	END

## Difference between PRE and IF 
Pre condition throws an error -> Completely non-deterministic
If does not throws an error -> What we can predict

## Exercise 


## Relations 
### Maplet notation 

Ben 7→ carrots means (Ben, carrots)

### Extensional definition (enumeration) 
eats = {Ben 7→ carrots, Ben 7→ broccoli, Helen 7→ beans, Helen 7→ carrots, Sarah 7→ carrots}

### Intensional definition (description) 

suc = {mm, nn | mm ∈ N ∧ nn ∈ N ∧ nn = mm + 1}


## Cartesian Product 
CHILD × VEG = 
{Ben 7→ carrots, Ben 7→ broccoli, Ben 7→ cabbage, Ben 7→ beans
Helen 7→ carrots, Helen 7→ broccoli, Helen 7→ cabbage, Helen 7→ beans,
Sarah 7→ carrots, Sarah 7→ broccoli, Sarah 7→ cabbage, Sarah 7→ beans,
Matthew 7→carrots, Matthew 7→broccoli, Matthew 7→cabbage, Matthew 7→beans}

## Powerset 

### Power set of single set 
P(X) is the set of all subsets of X. 
Eg: if X = {1, 2} then P(X) = {{}, {1}, {2}, {1, 2}}
### Power set of x* y 
P(CHILD × VEG) =
{{}, {Ben 7→ carrots}, {Ben 7→ broccoli}, {Ben 7→ cabbage}, . . .
{Ben 7→ carrots, Ben 7→ broccoli}, {Ben 7→ carrots, Ben 7→ cabbage}, . . .
{Ben 7→ carrots, Helen 7→ carrots} . . .
.
.
.
}


