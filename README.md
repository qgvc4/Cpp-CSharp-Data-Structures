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
