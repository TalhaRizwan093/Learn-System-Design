System design is a process of designing your system that best suits your product needs according to your user base it primarily consists of three fundamental components Client Server and Data store.
Lets take an example of Facebook, what is their high level design?

![[Components of System.png]]

These three components are the fundamentals of a system. 
The primary goal of a system is to serve data to the client in a way that the client can understand. For a system like Facebook we there are billion of users for that reason the system should be fast, scalable, available and consistent.

Lets dive into these components why we actually need these?
As discussed our primary goal is to handle data.

Lets first discuss storage types, we have Hard drive and RAM. RAM is a lot faster then the Hard Drive but is volatile means is the system shut downs the data will be gone for forever. But the hard drive is non volatile means it can persist data even if the system shut downs.

![[HDD and Ram.png]]

**Question:** Where should the Facebook store data?
For a large user base we speed is very essential so should we store data in RAM? But we also said that the availability is also very important users don't want to post their information and then after some time its get deleted, Right? 
We can conclude that the systems like Facebook should use both. But How we will do that? This is what system design is, it tells what a system should consists of and how it integrates different parts to ensure. Speed, Reliability, Consistency, Availability. 

**App Server:**
App server is also a very important part of a system, it consists of the the business logic of a system, and billion user connects with it and we somehow should manage it. For that we replicate the server so that different user could connect and use the system.

**Conclusion:**
System Design is the process of designing a system such that the system is faster (read/write), reliable (fault tolerant, backups etc.), Consistent (Same information to all users), Available (The data should be available to all the clients).