# Lecture 3

## Entitties
- An entity is an object that exists and is distinguishable from other objects. Eg. specific person, company, event
- An entity set is a set of entities of the same type that share the same properties. Eg. group of people, companies, trees  
  Don't come at me saying that a company is already a group of people. This was the given example lmao.
- An entity is represented by a set of attributes
	- instructor=(ID, name, salary)
	- course=(course_id, title, credits)
- A subset of attributes form a primary key of the entity set, i.e. unique identier (like Aadhar/SSN/JEE main rank+year)
- Entities in an ER diagram  
  Yeah, I too regret taking this course  
  ![[DBMS/Pasted image 20220126200731.png]]
  
## Relationship Sets
  - A relationship is an association among several entities.  
    E.g. Jiu Com'bak is the mentor of Mishinnhya. Here, mentor is a relationship set. It could have been, Motthya is a discord mod of $n$ people.
  - A relationship set is a mathematical relation among  $n\geq2$ entities  
    ![[DBMS/Pasted image 20220126201437.png]]
	- Now this just seems to be a label, you may add an attribute or two to it.  
	  ![[DBMS/Pasted image 20220126201708.png]]
	  For the real diagram just extend the advisor with a dashed line and write *date* in a box
- Polyamory allowed (i.e. project guide guides the prof, the student and projects)
	  
## Roles
- Entity sets of a relationship need not be distinct  
  ![[DBMS/Pasted image 20220126202237.png]]
  Here *course_id and prereq_id* are the roles. Consider discord roles (for real users), we all are human (entity set) but have different priviledge levels.
  
  ## Complex Attributes
  - Simple and composite (address)
  - Single valued, multi-valued (phone number)
  - Derived (age from D.O.B.)  
    ![[DBMS/Pasted image 20220127011245.png]]
	
	What stupid UML diagram thing is this.
	
	## Cardinality Contraints
	![[DBMS/Pasted image 20220127011358.png]]
	An instructor is associated with several (0 included) students via advisor
	A student is associated with atmost one instructor via advisor.
	
	### Total and partial participation
	The line from advisor to student when doubled (like =) becomes : An instruct associated with (1 or more) students.  
	Partial, as the name suggests.
	
	- Instead of increasing lines, one can write `0..*` or `1..1` just like in UML only that here it is MATLAB notation and we have to write it on both sides of the line.
	  ![[DBMS/Pasted image 20220127011811.png]]
	
	....  
	Writing DBMS notes seems stupid. Decision to be taken in next lecture.