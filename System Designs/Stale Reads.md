# Stale Reads

#### Eventual Consistency

Monotonic writes:
noted on copy
#### **Consistent Prefix reads** (Edge Case)
First we need to go over Partitioning: 1 db super big. SO rather then storing data in it split into 2 different dbs
Lets take an example where we store 1 message in one partition and other message in the other partition. and they have causal dependency in them. How we can ensure that 1 person get the both message at correct times. we can have a reply message feature and tract the causal dependency and store dependent message on same database

There is no possible way through which we can deal with stale reads but there are some aspects which make the user experience pretty bad and we have to deal with those at least.