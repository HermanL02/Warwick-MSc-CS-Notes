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
Ex1 and Ex2. 
MACHINE 名字
SETS set
END
这样所有的machine都可以共享这个set，但是其实不会干其他事情
Ex3. Modularising the specification of a secure system.
```
MACHINE Classification

SETS CLASS = {unc,conf,sec,tops}

CONSTANTS clessthanoreq

PROPERTIES clessthanoreq : CLASS <-> CLASS &

clessthanoreq = {unc|->unc, unc|->conf, unc|->sec, ... }

END
```
## M2 USES M1
## M2 INCLUDES M1
