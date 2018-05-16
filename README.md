# Cpp-CSharp-Data-Structures
This is a summary of basic data structures and how they are used in `C++` and `C#`.

Critical contents: Class, Create, Add/Delete/Find/Update/Iteration.

Additional contents: comparator, sort
## Array
### C#
#### Create
```csharp
int[] array = new int[10];
int[] array = new int[2] {1, 2};
int[] array = new int[] {1, 2};
int[] array = {1, 2};
```
#### Find and Update
```csharp
int a = array[1];
array[3] = a;
```
#### Iteration
```csharp
foreach (int i in list) 
{
    Console.Write(i + " ");
}

for (int i = 0; i < array.Length; i++)
{
    Console.Write(array[i] + " ");
}
```
#### Sort
```csharp
// ascending
Array.Sort(array);
// descending
Array.Sort(array, (x, y) => { return y - x; });
```

### C++
- `std::array` is a class version of `c` array, size is fixed at compile time. `std:: vector` is a small class with pointers pointing to heap. **you may always prefer vector**
- Summary of declaration
```CPP
    vector<T> vect; // {vector size, meta data} on stack, {bulk contents} on heap
    vector<T>* vect; // {vector size, meta data} and {bulk contents} on heap
    vector<*T> vect; // {bulk contents} are a set of pointers
```
- Initializations example
```CPP
    vector<int> vect{10, 20, 30};
    // Any STL container assignment is a deep copy, dictated by its assign operator or copy constructor.
    // But an object which contains a pointer will only have the pointer copied
    vector<int> vect2 = vect1; // deep copy
    vector<int> vect2(vect1); // deep copy
    vector<int> vect2(vect1.begin(), vect1.end()); // deep copy
    vect2.assign(vect1.begin(), vect1.end());
    vector<int> vect(5, 10); // 5 elements of value 10
```
- Add
```CPP
    vect.push_back(3);
    vect.insert(vect.begin() + 3, 5); // add 5 to position 3.
    vect.insert(vect.begin(), 4, 5); // add 4 elements of value 5 to beginning
    vect.insert(vect.end(), vect1.begin(), vect1.end(); // append vect1 to vect
```
- Delete
```CPP
    vect.erase(vect.begin() + 5); // remove one element
    vect.erase(vect.begin(), vect.begin + 2); // remove 2 elements (right exclude)
```
- Find
```CPP
    vector<int> vect;
    vect[3] = 2; //undefined but no error, the bound is not checked
    vect.at(3) = 2; // error, bound checked
```
- Update
```CPP
    replace(vect.begin(), vect.end(), 20, 99); // change all 20 to 99
```
- Iteration
```CPP
    for (std::vector<int>::iterator it = vect.begin(); it != vect.end(); it++)
    {
        cout << *it;
    }
    for (std::vector<int>::size_type it = 0; it < vect.size(); it++)
    {
        cout << vect[it];
    }
```
- Addition
```CPP
    reverse(vect.begin(), vect.end());
    sort(vect.begin(), vect.end());
    replace(vect.begin(), vect.end(), 20, 99); // change all 20 to 99
```

## String

### C++
- Similar to vector, `std::string` is a small class with pointers pointing to heap. 
- Summary of declaration
```CPP
string s("hello"); // usually not use pointer and new
```
- Initializations example
```CPP
string s1 = "foo";
string s2 = string("foo"); // the two are the same, they created a temporary 
// string, assign to s and the compiler will delete the temporary.
string s3 (s1, 1, 2); // copy a substring of s1 to s3 from position 1, copy length = 2
string s4 (10, 'x'); // "xxxxxxxxxx"
string s5 (s1.begin(), s1.begin() + 2);
```
- Add
```CPP
str.insert(5, s1);
str.insert(str.begin() + 2, s1.begin(), s1.begin() + 2);
str.append(s2);
str.append(s2.begin() + 2, s2.end());
```
- Delete
```CPP
str.erase(8, 10); // remove 10 chars from position 8
str.erase(str.begin() + 5); // move a char at position 5  
```
- Find
```CPP
str[1];
str.at(2);
```
- Update
```CPP
s[1] = 'a';
```
- Iteration
```CPP
    for (std::string<int>::iterator it = string.begin(); it != string.end(); it++)
    {
        cout << *it;
    }
    for (std::string<int>::size_type it = 0; it < string.size(); it++)
    {
        cout << vect[it];
    }
```
- Addition
```CPP
reverse(str.begin(), str.end());
sort(str.begin(), str.end());
```
## Arraylist
## Linkedlist
## Queue
## Stack
## Heap
## Hashmap
## Tree
## Graph
## Trie
## Additionals
### CPP
- `==` and `.compare() == 0` are the same for objects.
- "Rule of Three" in CPP
    + a copy constructor/constructor
        ```CPP
        MyClass( const MyClass& other ); // correct
        MyClass( const MyClass* other );// not this
        ```
        without explicit declaration, an implicit copy constructor is given by constructor, equivalent to 
        ```CPP
        MyClass::MyClass( const MyClass& other ) :
        x( other.x ), c( other.c ), s( other.s )
        {}
        ```
        It is not always sufficient, like for `vector` we need deep copy
    + an assignment operator

        default assignment operator
        ```CPP
        MyClass& MyClass::operator=( const MyClass& other ) {
            x = other.x;
            c = other.c;
            s = other.s;
            return *this;
        }
        ```
    + a destructor
- dynamic allocation and delete: `new`, `delete p`, `delete[] q`
