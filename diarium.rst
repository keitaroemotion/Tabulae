ACID
----
 Atomicity
  All data transactions results must be either 0 or 1. For instance,

    ::
    insert into CUSTOMER VALUES ("1", "nauta");
    insert into CUSTOMER VALUES ("2", "clericus");
    insert into CUSTOMER VALUES ("3", "scholaris");
    insert into CUSTOMER VALUES ("4", "puella");
    insert into CUSTOMER VALUES ("5", "regina");

    if transaction failed while these five queries are executed,
    the results of the database must be either of the following states:

    (a) the database has nauta, clericus, scholaris, puella, regina
    (b) the database does not have any of the above.

 Consistency

 Isolation

 Durability


Isolation Levels
----------------

  Serializable

  Repeatable Reads

  Read Commited

  Read Uncommited



*Dirty Read*
  Uncommited Data(Dirty Data) can be read.

*NonRepeatable Read*
  Between T1 and T2, when seen at both time, the result of the same row is different.

*Phantom Read*
  (query insertion at T1, T2) T1 -> T2(at T2, more data added)

the difference between NonRepeatable Read and Phantom Read :
  the former CHANGES data
  the latter ADDS data















