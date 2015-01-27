ACID
----
 Atomicity
   Database transaction => all or nothing rule

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

    ---
    consistent
    1. acting or done in the same way over time, especially so as to be fair or accurate.
       unchanging in nature, standard, or effect over time.
    2. (of an argument or set of ideas) not containing any logical contradictions.
    ---

    The consistency property ensures that the database remains in a consistent state before the start of the transaction and after the transaction is over (whether successful or not).

 Isolation

 Durability
   transactions that have commited survive permanently
   `transaction log`

Isolation Levels
----------------

Isolation Level   | Dirty Read  | Nonrepeatable Read | Phantom Read

READ UNCOMMITTED  | Permitted   | Permitted          | Permitted
READ COMMITTED    | --          | Permitted          | Permitted
REPEATABLE READ   | --          | --                 | Permitted
SERIALIZABLE      | --          | --                 | --


Read Uncommited supplies nonblocking read




*Dirty Read*
  Uncommited Data(Dirty Data) can be read.

*NonRepeatable Read*
  Between T1 and T2, when seen at both time, the result of the same row is different.

*Phantom Read*
  (query insertion at T1, T2) T1 -> T2(at T2, more data added)

the difference between NonRepeatable Read and Phantom Read :
  the former CHANGES data
  the latter ADDS data








appendix
------------------------------------------------------------------
primus facere (first do)

tour (tornos=lathe)
 detour


ligare(to bind) => liable (to be responsible)


ledger[1] is the principal book or computer file for recording and totaling economic transactions measured in terms of a monetary unit of account by account type, with debits and credits in separate columns and a beginning monetary balance and ending monetary balance for each account.

Isolation refers to the requirement that other operations cannot access or see the data in an intermediate state during a transaction. This constraint is required to maintain the performance as well as the consistency between transactions in a database.

Durability refers to the guarantee that once the user has been notified of success, the transaction will persist, and not be undone. This means it will survive system failure, and that the database system has checked the integrity constraints and won't need to abort the transaction. Many databases implement durability by writing all transactions into a transaction log that can be played back to recreate the system state right before a failure. A transaction can only be deemed committed after it is safely in the log.

Durability does not imply a permanent state of the database. Another transaction may overwrite any changes made by the current transaction without hindering durability.
