

Just for completion, in `Matlab`

```matlab
if <expression 1>
% Executes when the expression 1 is true 
<statement(s)>

elseif <expression 2>
% Executes when the boolean expression 2 is true
<statement(s)>

Elseif <expression 3>
% Executes when the boolean expression 3 is true 
<statement(s)>

else 
%  executes when the none of the above condition is true 
<statement(s)>
end
```





The sort method can sort lists comprised by lists, i.e, nested structures, not only simple lists.

```python
>>> tareas = [
    [6, 'Distribución'],
    [2, 'Diseño'],
    [1, 'Concepción'],
    [7, 'Mantenimiento'],
    [4, 'Producción'],
    [3, 'Planificación'],
    [5, 'Pruebas']
]
>>> tareas.sort()
>>> print(tareas)
[[1, 'Concepción'], [2, 'Diseño'], [3, 'Planificación'], [4, 'Producción'], [5, 'Pruebas'], [6, 'Distribución'], [7, 'Mantenimiento']]
```



`sorted_list = sorted(python_list)` --> returns an ascending sorted list.  
`sorted_list = sorted(python_list, reverse=True)` --> returns a descendingsorted list.  
`python_list.index(element_in_list)` --> returns the position of an element within the list.  
`enumerate(python_list)` --> returns a list of tuples. Each tuple has an index and the correposding value of the list.  
`zip(lis1, list2)` --> combine values of two list, one by one [(list1[0], list2[0]), (list1[1], list2[1]), ...., (list1[N], list2[N])]  
`str = separator_string.join(python_list)`  
`list = str.split("separator")`  

`python_dict[key]` --> `KeyError` if `key` is not present in `python_dict`. To avoid this, use: `python_dict.get(key, default_element_if_key_not_present)`

`python_dict.update({fieldx: new_value_x, fieldy: new_value_y, new_field: value})` --> update the value associated with keys and also adds new pairs (key, value)

`del python_dict[key]` --> deletes the pair (key, value) specified.

`python_dict.pop(key)` --> removes and returns the value associated to the `key`.

`python_dict.keys()`
`python_dict.values()`
`python_dict.items()` --> return a list of tuples. Each tuple contains a pair formed by a key and a value.

`Sets` and `Dictionaries` have constant lookup time.
`set(list)`
A set doesn't have duplicates. So, if we have a list with duplicates, one way to get rid of them is to convert that list to a set. Be aware that the set is not an ordered collection. If you want to preserve order, you need to use an ordered dictionary, from the collection module.

module: random
function: choice()

module: datetime
function: date.today() (date is a class)

module: calendar
function: isleap(any_year)

module: os (SUPER IMPORTANT MODULE)



`ljust(fixed_number_of_characters)`
`str(elemento)`

Old print function: `"%s %s %d" % (string_1, string_2, integer_number)`
`"separator".join(list_of_strings)` ==> All the strings present in `list_of_strings` are separated by the string `separator`

# QUEUES

```python
from collections import queue
>> q = queue()
>> q.append(1)
>> q.append(2)
>> q.append(3)
>> q.popleft()
1
```



`try-except-else-finally-raise`

`@classmethod` and `@staticmethod`

You **never want to pass mutable data like a list or a dictionary as default arguments (empty elements, either [] or {})**, pass `None`, and then in the method's body set the argument to a `list, []` or a `dictionary, {}`. Example:

```python
def __init__(self, first, last, pay, employees=None):
    super().__init__(first, last, pay)
    if employees is None:
        self.employees = []
    else:
        self.employees = employees
```

## globals() & locals()

Si utilizamos una función reservada `globals()` obtendremos un diccionario con todas las definiciones dentro del espacio global.

Si utilizamos una función reservada `locals()` obtendremos un diccionario con todas las definiciones dentro del espacio local del bloque en el que estamos.

## GENERATORS

A generator is an object that contains the logic to provide elements on the fly. It serves the element as it is requested.

```python
def square_numbers(nums):
    for i in nums:
        yield (i*i)

my_nums = square_numbers(nums) # my_nums is a generator
```

or

```python
my_nums = (x*x for x in nums) # Another way to create a generator.
```

---

## UNIT TESTS

```bash
$ python -m unittest module_name
```

Tests don't run in order necessarily

```python
@classmethod
def setUpClass(cls): --> Runs at the very beginning
    ...

@classmethod
def tearDownClass(cls): --> Runs at the very end.
    ...

def setUp(self): --> runs before every single test
    ....
def tearDown(self): --> runs after every single test
```

https://docs.python.org/3/library/stdtypes.html#typesseq-common
