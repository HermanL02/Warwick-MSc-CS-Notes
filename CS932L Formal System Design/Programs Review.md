/* ProjectsLab3 machine. */

MACHINE Lab3

  

SETS STUDENT; PROJECT

  

CONSTANTS maxmark, MARK

  

PROPERTIES maxmark : NAT1 & MARK = 0..maxmark 
==Describes conditions for sets & constants==
  

VARIABLES students, projects, marks

  

INVARIANT students <: STUDENT &

projects : STUDENT +-> PROJECT &

dom(projects) = students &

marks : STUDENT +-> MARK &

dom(marks) <: students

  

INITIALISATION students := {} || projects := {} || marks := {}

  

OPERATIONS

signup(ss,pp) =

PRE
==:belongs to, /:not belongs to== 
ss:STUDENT & pp:PROJECT & ss /: dom(projects)

THEN
==\/ combine two sets==
students := students \/ {ss} ||
==Maplet |->映射==
projects := projects \/ {ss |-> pp}

END;

  

pp <-- assignproject(ss) =

PRE ss:STUDENT & ss /: students

THEN

==随机分配到一个project里面==

ANY proj

WHERE proj : PROJECT

THEN pp := proj

|| students := students \/ {ss}

|| projects(ss) := proj

END

END;

  

pp <-- queryproject(ss) =

PRE

ss:STUDENT & ss : dom(projects)

THEN

pp := projects(ss)

END;

  

entermark(ss,mm) =

PRE

ss:STUDENT & mm:MARK & ss:students

THEN

marks := marks <+ {ss |-> mm}

END;

  

mm <-- querymark(ss) =

PRE

ss:STUDENT & ss : dom(marks)

THEN

mm := marks(ss)

END

  

  

END