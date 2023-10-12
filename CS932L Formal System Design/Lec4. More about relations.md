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

eats B {carrots} = {Ben 7→ carrots, Helen 7→ carrots, Sarah 7→ carrots}


## 定义域减法和值域减法 Domain and Range subtraction

和限制相似，只不过是将这部分从原始set中去除掉

## Example of use Relations in Specification 

A specification is required to represent a system for allowing people to view sensitive documents. Each person has a unique identifier, and only people registered with the system are allowed to see documents. For each registered person, a record is kept of the documents they are allowed to see. Documents can only be viewed by people with permission to see the document. Typical operations on the system will be to register or deregister a user, to query the documents currently viewed by a particular person, to start viewing a document, to stop viewing a document, to alter permissions, etc etc.

### Thinking: What are the variables and sets? 

PID: Person id
DOC: Document set
reg: registered user
allowed: recording what people should be allowed to see aka. permission
viewing: who is currently viewing what

### Thinking: What are the operations 
dd <-- beingviewed = dd := ran(viewing)


## Relational image 关系映像
**关系与函数的区别**：
- 函数是一种特殊的关系，其中每个定义域的元素都与值域中的一个且只有一个元素相关联。
- 但在一般的关系中，一个定义域的元素可能与值域中的多个元素相关联。
**关系映像**：
- 是一个用来描述某个或某些定义域元素与哪些值域元素相关联的概念
- 如果你有一个关系 R 和一个定义域元素 a，那么 a 的关系映像是所有与 a 相关的值域元素的集合。在数学符号中，这通常表示为 R[a]。
- 如果你有一个关系 R 和一个定义域元素的集合 A，那么 A 的关系映像是所有与 A 中的任何元素相关的值域元素的集合。数学上表示R[A]。
- 

## Relational Inverse 

The types of domain and range swap. 

PRE vv : VEG THEN cc := $eats^{−1} [{vv}]$ END


## Relational composition 关系组合

R1 composition R2 = {xx, zz | xx ∈ X ∧ zz ∈ Z ∧ ∃ yy • (yy ∈ Y ∧ xx 7→ yy ∈ R1 ∧ yy 7→ zz ∈ R2)}

Supposing we have 2 relations, supposing R is 
```
1 -> 2
3 -> 4
```
and S is 
```
2 -> 5
4 -> 6
```
Then R * S is 
```
1 -> 5
3 -> 6
```
来实现关系的组合

## Relational Overriding 关系覆写 

覆写可以覆盖之前的操作，如果原关系不存在则自动创建新的操作

Operations for R : X ↔ X

id(X) = {xx, xx | xx ∈ X}

$R^{n}$ - R composed with itself n times

Eg: $R^{3}$ = R ==09== R ==09== R

$R^{+}$ - the transitive closure of R

Ie: $R^{+}$ = R ∪ $R^{2}$∪ $R^{3}$ ∪ $R^{4}$ ∪ . . .

$R^{*}$ - the reflexive transitive closure of R

Ie: $R^{+}$ ∪ id(X)
