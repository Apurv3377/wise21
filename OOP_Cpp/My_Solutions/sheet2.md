## Solutions to Sheet 2: 

### Part 1: Theory::

**1. Explain the difference between call-by-value and call-by-reference.**

**2. What is a heap memory? Why it is used?**

**3. What is the undefined behavior in following program?**

```
int x = 127;
char *p = (char*) &x;
cout << *p << endl;
```


**4. Why are public interfaces of a class kept as minimal as possible?**


**5. Is C++ a memory-safe language?**

**6. In which case will using a delete this in destructor goes wrong?**


### Part 2: Debug ::

```
#include <iostream>
#include <vector>
using namespace std;
vector<int>& a() {
vector<int> t {1,2,3};
return t;
}
int main()
{
vector<int> x = a();
cout << x.at(1) << endl;
}

```

**1. The above program throws a warning that a() returns a local variable. What is the cause of this warning?**

**2. Fix the program such tha it returns the vector `t` and compiles without warning.**