Transaction Manager
A Transaction Manager uses a Transaction table to keep track of all the active transactions and a list of fileNames to keep track of all the open files
When a transaction begins, the transaction manager generates a new transaction Id for it
A user specifies the type of concurrent reading mechanism for the files: Round Robin or Random
Data Structure
Transaction table: A map between a filename and TransactionDetails. Once a transaction is committed or aborted, the entry is removed from the transaction table
Open files: List of all the open files. Once a file is terminated, or a transaction is committed or aborted, the entry is removed from this list

class TransactionDetails{
    int transactionID,
    int lineNumberRead,
    int isolationLevel;
}

HashMap<String, <TransactionDetails>> transactionTable;
LinkedList<String> fileNames;

