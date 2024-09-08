Databases are multi threaded multiple threads can read and write in database at the same time which could result in race conditions.

### Commit
In databases commit is defines that the write in database is complete and done.

### Race Conditions
### Dirty Write
Lets take an example of two people purchasing some thing

![[Fig dirty write.png]]
In the above example thread 1 and thread 2 was changing the same row so we in the end have the inconstant data. Product is purchased for the user2 and the address of user 1 is given. 
#### Fix Row level lock
We can use locking to prevent this issue
![[Fig locking explained.png]]
- In this case dead lock could occur if the share resources between and they want to access each other while in lock. but there are prevention techniques for this in databases like dead lock detection where they then give up there detection.
- Another solution in if we add data in row order it wont occur either in some cases.
This will fix the m of dirty writes but this isn't it we have

### Dirty Reads
Dirty read is actually reading uncommitted data for example in the below figure. We have Purchased some thing and now our balance is 10$ less and the now we read our balance and it is 10$ less but due to some reason the receiver didn't received the balance and you read the incorrect data
![[Fig dirty read.png]]
### Fix
We can do couple of fixes  
1. Row level locking
	- If the row is locked we cannot read it until it is freed but it is slow.
2. Store the old value until the commit
	- We purchase some thing but before the actual commit we have pointer to the old value until the commit is done then we can read the new value.

Covered 2 types of race conditions.
1. Dirty Read
2. Dirty Write

If a database protects from both dirty reads and dirty writes it is basically implementing **Read Committed Isolation**
But there are many more race conditions.