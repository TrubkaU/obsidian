Since in [[00 Java]] all primitive types should be placed into the Thread stack, all Thread will create new exemplars of the primitive value. 

So, the volatile keyword will be made the field as common between all threads;
_“… the volatile modifier guarantees that any thread that reads a field will see the most recently written value.”_ **- Josh Bloch**


Also, the 