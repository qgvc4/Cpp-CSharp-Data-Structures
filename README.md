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
    // Any STL container assignment is a deep copy
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


## String

### C++
- Similar to vector, `std::string` is a small class with pointers pointing to heap. 
- Summary of declaration
```CPP

```
- Initializations example
```CPP

```
- Add
```CPP
   
```
- Delete
```CPP
    
```
- Find
```CPP
  
```
- Update
```CPP

```
- Iteration
```CPP
 
```
- Addition
```CPP
```

### C#
#### Create
```csharp
string firstname = "Matt";
string lastname = "Smith";
string name = firstname + lastname;
char[] letters = { 'H', 'e', 'l', 'l', 'o' };
string greetings = new string(letters);

string[] sarray = { greetings, name };
string message = String.Join(", ", sarray);
Console.WriteLine("Message: {0}", message); // Message: Hello, MattSmith

//formatting method to convert a value
DateTime waiting = new DateTime(2012, 10, 10, 17, 58, 1);
string chat = String.Format("Message sent at {0:t} on {0:D}", waiting);
Console.WriteLine("Message: {0}", chat); // Message: Message sent at 5:58 PM on Wednesday, October 10, 2012
```
#### APIs
* length `name.Length`
* to char array `name.ToCharArray()`
* Split
```csharp
string log = "word|a word, ok.";
char[] delimers = { '|', ' ', ',', '.' };
string[] words = log.Split(delimers, StringSplitOptions.RemoveEmptyEntries);
Console.WriteLine(log);
Console.WriteLine("===");
foreach(string s in words)
{
    Console.WriteLine(s);
}
Console.WriteLine("===");
```
* substring
```csharp
string substr = str.Substring(stratIndex, length);
```
* join
```csharp
string message = String.Join(", ", sarray);
// String.Join(separator, IEnumerable<String>/Object[]/String[])
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
    - a copy constructor
    - an assignment operator
    - a destructor
- dynamic allocation and delete: `new`, `delete p`, `delete[] q`
