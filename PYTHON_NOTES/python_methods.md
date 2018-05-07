# LIST METHODS

**list()**  
 -> new empty list

**list(iterable)**  
-> new list initialized from iterable's items

**L1 == L2**  
**L1 != L2**  
**L1 >= L2**  
**L1 >  L2**  
**L1 <= L2**  
**L1 <  L2**  
-> True or False (Compare values, not references)

**L.append(object)**  
-> None    -- append object to end

**L.extend(iterable)**  
-> None    -- extend list by appending elements from the iterable

**L.clear()**  
-> None    -- remove all items from L

**L.insert(index, object)**  
           -- insert object before index  

**L.remove(value)**  
-> None    -- remove first occurrence of value. Raises ValueError if the value is not present.

**L.copy()**  
-> list    -- a shallow copy of L

**L.count(value)**  
-> integer -- return number of occurrences of value

**L.index(value, [start, [stop]])**  
-> integer -- return first index of value.    Raises ValueError if the value is not present.

**L.pop([index])**  
-> item    -- remove and return item at index (default last). Raises IndexError if list is empty or index is out of range.

**L.reverse()**  
           -- reverse *IN PLACE*  

**L.sort(key=None, reverse=False)**  
-> None    -- stable sort *IN PLACE*


# TUPLES

**tuple()**  
-> empty tuple

**tuple(iterable)**  
-> tuple initialized from iterable's items
If the argument is a tuple, the return value is the same object.

**T1 + T2**
-> Tuple
 
**T1 == T2**  
**T1 != T2**  
**T1 >= T2**  
**T1 >  T2**  
**T1 <= T2**  
**T1 <  T2**  
-> True or False (Compare values, not references)
 
**hash(T)**  
-> hash id
 
**iter(self)**  
-> iterator

**len(T)**  
-> length of the tuple

**T*integer**  
-> duplicate the tuple T 'integer' times.

**T.count(value)**  
-> integer -- return number of occurrences of value

**T.index(value, [start, [stop]])**  
-> integer -- return first index of value.
Raises ValueError if the value is not present.






