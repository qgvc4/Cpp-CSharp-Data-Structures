# Cpp-CSharp-Data-Structures
This is a summary of basic data structures and how they are used in `C++` and `C#`.

Critical contents: Class, Create, Add/Delete/Find/Update/Iteration.

Additional contents: comparator, sort
## Array
### C++
- `std::array` is a class version of `c` array, size if fixed at compile time. `std:: vector` is a small class with pointers pointing to heap. **you may always prefer vector**
- Summary of declaration
```CPP
    vector<T> vect; // {vector size, meta data} on stack, {bulk contents} on heap
    vector<T>* vect; // {vector size, meta data} and {bulk contents} on heap
    vector<*T> vect; // {bulk contents} are a set of pointers
```
- Initializations example
```CPP
    vector<int> vect{10, 20, 30};
    vector<int> vect2 = vect1; // deep copy
    vector<int> vect2(vect1); // deep copy
    vector<int> vect2(vect1.begin(), vect1.end()); // deep copy
    vect2.assign(vect1.begin(), vect1.end());
    vector<int> vect(5, 10); // 5 elements of value 10
```
- Add
## String
## Arraylist
## Linkedlist
## Queue
## Stack
## Heap
## Hashmap
## Tree
## Graph
## Trie
