Table 4-1. Differences Between Arrays and Pointers

| Pointer                                       | Array                |
|:----------------------------------------------|:--------------------:|
| Holds the address of data                     |  Holds Data          |
| Data is accessed indirectly, so you first retrieve the contents of the pointer, load that as an address (call it "L"), then retrieve its contents.<br>If the pointer has a subscript [i] you instead retrieve the contents of the location 'i' units past "L" | Data is accessed directly, so for a[i] you simply retrieve the contents of the location i units past a. |
| Commonly used for dynamic data structures     | Commonly used for holding a fixed number of elements of the same type of data |
| Commonly used with malloc(), free()           | Implicitly allocated and deallocated |
| Typically points to anonymous data            | Is a named variable in its own right |
