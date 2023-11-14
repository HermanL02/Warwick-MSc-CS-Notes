# Abstract Machines Structures
		1. Modularity 模块化
		2. Encapsulation and separation of concerns 封装和分离concern
		3. Incremental specification and reuse 增加specification并且重用代码
		4. Tree Structure
# Incorporating one machine in another
## M2 SEES M1
- M2 can Refers any sets and constants defined in M1
- M2 can Query/Use values variables in M1
- M2 can't use operations in M1 (except query)
- M2 invariant can't refer to variables in M1
- A machine can be seen by different machines
- if M1 has parameters, M2 has no control over the values chosen
- M2 does not see machines M1 sees
## Example
## M2 USES M1
## M2 INCLUDES M1
