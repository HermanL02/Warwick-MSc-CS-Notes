# Domain and range

dom(R) = {xx | xx ∈ X ∧ ∃ yy • (yy ∈ Y ∧ xx 7→ yy ∈ R)}
ran(R) = {yy | yy ∈ Y ∧ ∃ xx • (xx ∈ X ∧ xx 7→ yy ∈ R)}

## Example 
eats = {Ben 7→ carrots, Ben 7→ broccoli,Helen 7→ beans,
Helen 7→ carrots, Sarah 7→ carrots}

The domain of eats is {Ben, Helen, Sarah}
The range of eats is {carrots, broccoli, beans}

## **定义域限制 (domain restriction)**
这个操作是基于一个子集 S 来从关系 R 中删减元素，结果的关系只包括那些其定义域在 S 中的元素。
Suppose R : X ↔ Y , S : P X and T : P Y then the domain restriction is:
S C R = {xx, yy | xx ∈ X ∧ xx ∈ S ∧ yy ∈ Y ∧ xx 7→ yy ∈ R}
### Example 
{Helen, Sarah} C eats = {Helen 7→ beans,Helen 7→ carrots, Sarah 7→ carrots}
## **值域限制 (range restriction)**
与定义域限制类似，这个操作是基于一个子集 T 来从关系 R 中删减元素，结果的关系只包括那些其值域在T中的元素
R B T = {xx, yy | xx ∈ X ∧ yy ∈ Y ∧ yy ∈ T ∧ xx 7→ yy ∈ R}

### Example

eats B {carrots} = {Ben 7→ carrots,Helen 7→ carrots, Sarah 7→ carrots}


## 定义域减法和值域减法 Domain and Range subtraction

和限制相似，只不过是将这部分从原始set中去除掉

## Example of use Relations in Specification 

A specification is required to represent a system for allowing people to view sensitive documents. Each person has a unique identifier, and only people registered with the system are allowed to see documents. For each registered person, a record is kept of the documents they are allowed to see. Documents can only be viewed by people with permission to see the document. Typical operations on the system will be to register or deregister a user, to query the documents currently viewed by a particular person, to start viewing a document, to stop viewing a document, to alter permissions, etc etc.

### Thinking: What variables and sets do we need to have? 
PID


