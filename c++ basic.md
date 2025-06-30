## Universal Header

> `#include<bits/stdc++.h>`

## printing Hello in C++

header file in C++ :  ```#inlcude<iostream>```

* `std` is called Namespace where print command `cout` stays

  

```cpp
#include<iostream>
int main(){
    std::cout << "hello";
    return 0;

}
```

  

## Printing Variable In C++


```cpp

#include<iostream>
int main()

{
    int x=10;
    std :: cout << x;
    std :: cout << x << y; //--> print multiple variable
    return 0 ;
}

```

  

## End line / next Line

 *  \n

```cpp

cpp std :: endl

```

  

## Using `std` as Namespace, taking input , Ascii- num/char

  

```cpp

#include<iostream>

using namespace std; //use this as one so that dont have to use again n again
int main(){

    int x;

    cin >> x; //Taking input

    cout << x << endl;

    // Printing Ascii

    char c = 'a';

    int ascii = c;

    cout << ascii << endl;

    char a = 'A';

    cout << (int)a << endl;

    return 0;

}

```

  

## EoF-( End of File), While Loop

  

```cpp

#include<iostream>

using namespace std; //use this as one so that dont have to use again n again
// Take as many as inputs user gave
int main(){
    int x;
    while (cin >> x)
    {
        cout << x << endl;
    }
    return 0;
}

```

  

## Setprecision

### Format

*  Have to add `include<iomanip`

* cout<< fixed << setprecision(num of digit want to print after point / decimal) << variable name;

  

```cpp

#include<iostream>

#include<iomanip> // input-output manipulation

using namespace std;

int main(){

    double z = 34.43252;

    cout << fixed << setprecision(3) << z << endl;

    return 0 ;

}

```

  

## If-Else Loop

```cpp

#include<iostream>

using namespace std;

int main(){

    int x =5;

    if (x % 2 == 0) // condition want to check

    {

        cout << "Even"; // output

    }

    else

    {

        cout << "Odd";

    }

    return 0;

}

```

  

## Ternary Operator

* **formate**: (condition) ? true  : False

  

```cpp

#include<iostream>

using namespace std;

int main(){

    int x = 6;

    (x%2 == 0) ? cout << "Even" : cout << "Odd";

    return 0;

}

```

  

## Switch Case

  

```cpp

#include<iostream>

using namespace std;

int main(){

    char x;

    cin >> x;

    switch (x)

    {

    case 'a':

        cout << "Vowel\n";

        break;

    case 'e':

        cout << "Vowel\n";

        break;

    case 'i':

        cout << "Vowel\n";

        break;

    case 'o':

        cout << "Vowel\n";

        break;

    case 'u':

        cout << "Vowel\n";

        break;

    default:

        cout << "Constant";

        break;

    }

}

```

  

## Min/Max , Swap

* Do it using normal if else loop, and temp variable

* using `algorithm` Library & functions like `min,max,swap`

```cpp

#include<iostream>

#include<algorithm>
using namespace std;
int main(){
    // can do this in usual rule like using if-else
    int a,b;
    cin >> a >> b;
    cout << min(a,b) << endl;
    cout << max(a,b) << endl;
    swap(a,b); // swap function have no return so have to use cout separately
    cout << a << " " << b << endl;
    return 0;
}

```

  

## Strings in C++

- After using `cin >> x`, a **newline character (`\n`)** remains in the input buffer. `cin.getline()` would immediately read that newline instead of a new line of text. So, `cin.ignore()` clears the buffer so that `getline` works correctly.

```cpp

#include<iostream>        
using namespace std;
int main() {
    int x;
    cin >> x;          
    cin.ignore();         // Ignores the leftover newline character after reading x
    char s[100];
    cin.getline(s, 100);  // Reads a line of text (max 100 characters)
    cout << x << endl << s << endl;  // Prints the integer and the string
    return 0;
}
```

# Difference Between Stack Memory and Heap Memory
---

##  Stack Memory

- **Definition**: Stack memory is a region of memory that stores temporary variables created by each function (also known as an execution stack).

- **Memory Allocation**: Automatically managed (LIFO – Last In, First Out).

- **Speed**: Faster access compared to heap.

- **Size**: Limited in size (usually much smaller than the heap).

- **Scope**: Local variables and function call management.

- **Lifespan**: Variables are destroyed once the function call is completed.
##  Heap Memory


- **Definition**: Heap memory is used for dynamic memory allocation. Variables are allocated manually and stay allocated until they are explicitly freed.

- **Memory Allocation**: Managed via functions like `malloc`, `calloc`, `new`, etc.

- **Speed**: Slower access compared to stack due to the overhead of dynamic allocation.

- **Size**: Larger than the stack.

  

##  Dynamic Variable

#### **dynamic memory** is allocated at **runtime** using special operators:

- `new` (to allocate memory)

- `delete` (to free memory)

- format: `data_type * pointer_name  = new data_type`

```cpp

#include<bits/stdc++.h>

using namespace std

int main()

{
    int x = 10;
    cout << x << endl;
    int *p = new int; // this line declares a new int type dynamic variable which stores only the address
    *p = 100; // this line stores the value of the dynamic variable
    cout << *p << endl;
}
```

  
## Return Array From Function
---
### Static Array

```cpp

int* fun() {
    int a[5]; // ৫ সাইজের স্ট্যাটিক এরে ডিক্লেয়ার করা হয়েছে।
    for(int i=0;i<5;i++) {
        cin >> a[i]; // ইউজার থেকে ইনপুট নেওয়া হচ্ছে।
    }
    return a; // স্ট্যাটিক এরে রিটার্ন করা হচ্ছে।
}

```

- এখানে `a[5]` স্ট্যাক মেমোরিতে তৈরি হয়েছে।

- যখন `fun()` ফাংশন শেষ হয়ে যায়, তখন স্ট্যাক থেকে `a` অ্যারে **ডিলিট** হয়ে যায়।

- তাই `main()` ফাংশনে যখন তুমি `p[i]` দিয়ে অ্যারে প্রিন্ট করার চেষ্টা করো, তখন **অনির্দিষ্ট আচরণ** (undefined behavior) হয়।

### Dynamic Array

```cpp

int* fun() {

    int* a = new int[5]; // ডায়নামিক মেমোরিতে অ্যারে তৈরি হচ্ছে।

    for(int i=0;i<5;i++) {

        cin >> a[i]; // ইনপুট নিচ্ছে।

    }

    return a; // এই অ্যারে রিটার্ন করা হচ্ছে।

}

```

---

### Differences

| বিষয়             | Static Array              | Dynamic Array                             |
| ---------------- | ------------------------- | ----------------------------------------- |
| মেমোরি           | Stack                     | Heap                                       |
| লাইফটাইম         | ফাংশন শেষ হলে মুছে যায়     | ফাংশনের বাইরে পর্যন্ত টিকে থাকে            |
| মেমোরি কন্ট্রোল  | Compiler করে              | প্রোগ্রামার নিজে করে (`new/delete`)       |
| রিটার্ন করা      | ঝুঁকিপূর্ণ                 | নিরাপদ                                    |
| নমনীয়তা         | ফিক্সড সাইজ                | রানে সময়ে সাইজ নির্ধারণ সম্ভব           |
 

---

## Increase Size of an Array & Delete an Array

  

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
 int *a = new int[3]; // a এরে আছে ৩ সাইজের।
 int *b = new int[3]; // কপি করে রাখার জন্য আরেকটি b এরে নেওয়া হলো সেইম সাইজের।
 for (int i = 0; i < 3; i++)
 {
 cin >> a[i]; // ইনপুট নিয়ে a এরেতে রাখা হচ্ছে।
 b[i] = a[i]; // কপি করে b এরেতে রাখা হচ্ছে।
 }
 delete[] a; // a ডিলিট করে দেওয়া হলো।
 a = new int[5]; // নতুন করে a এরে ডিক্লেয়ার করা হলো ৫ সাইজের।
 for (int i = 0; i < 3; i++)
 {
 a[i] = b[i]; // b এরে থেকে কপি করে a এরেতে রাখা হচ্ছে।
 }
 delete[] b; // এবার b ডিলিট করে দেওয়া হলো।
 a[3] = 40; // এখন আমাদের কাছে একটিই এরে আছে a এরে, যার সাইজ হচ্ছে ৫। এবং এর প্রথম ৩ ইন্ডেক্সে পূর্বের ৩টি ভেলু স্টোর আছে। এবার শেষের দুটি ইন্ডেক্সে ভেলু রাখা হচ্ছে।
 
 a[4] = 50;
 for (int i = 0; i < 5; i++)
 cout << a[i] << " "; // a এরে প্রিন্ট করা হচ্ছে।
 return 0;
}

```
---
# Object & Class in C++
---
### **Format** of Class 

```cpp
class class_name [ নরমালি ক্যাপিটাল লেটারে লিখা হয়। না লিখলেও কাজ করবে ] 
{
public:    [ access_modifier টোটাল ৩ ধরনের হয়ঃ Public, Private, Protected ]
    data_type variable_name;
    data_type variable_name;
};
```

### **Format** Of Object

```cpp
class_name object_name;
object_name.class_variable   [ অবজেক্ট এর ক্লাস ভেরিয়েবলগুলো এক্সেস করতে হলে . (ডট) ব্যাবহার করতে হয় ]

```


## Example

```cpp
#include <bits/stdc++.h>

using namespace std;
class Student // ক্লাস ক্রিয়েট করা হয়েছে। 
{
public: // এক্সেস মডিফায়ার হিসেবে পাবলিক দেওয়া হয়েছে। 

 char name[100]; // ক্লাস ভেরিয়েবল ডিক্লেয়ার করা হয়েছে। 
 int roll;
 double cgpa;
};
int main()
{
 Student a, b; // Student ক্লাসের অবজেক্ট ক্রিয়েট করা হচ্ছে ২টি। 

 cin.getline(a.name, 100); // শুরুতে প্রথম অবজেক্টের নাম ইনপুট নেয়া হচ্ছে। নামের মধ্যে স্পেস থাকতে পারে তাই গেটলাইন দিয়ে ইনপুট নেওয়া হয়েছে। 

 cin >> a.roll >> a.cgpa; // তারপর প্রথম অবজেক্টের রোল এবং সিজিপিএ ইনপুট নেওয়া হচ্ছে।

 getchar(); // প্রথম অবজেক্টের রোল এবং সিজিপিএ ইনপুট দেওয়ার পর একটি এন্টার দেওয়া হবে তারপর দ্বিতীয় অবজেক্টের নাম ইনপুট দেওয়া হবে। সেই এন্টারটি ইগনোর করার জন্য getchar() ইউজ করা হয়েছে। 
 
 cin.getline(b.name, 100); // দ্বিতীয় অবজেক্টের নাম ইনপুট নেয়া হচ্ছে।

 cin >> b.roll >> b.cgpa; // তারপর দ্বিতীয় অবজেক্টের রোল এবং সিজিপিএ ইনপুট নেওয়া হচ্ছে।

 cout << a.name << " " << a.roll << " " << a.cgpa << endl; // প্রথম অবজেক্ট এর নাম, রোল, সিজিপিএ প্রিন্ট করা হচ্ছে।

 cout << b.name << " " << b.roll << " " << b.cgpa << endl; // দ্বিতীয় অবজেক্ট এর নাম, রোল, সিজিপিএ প্রিন্ট করা হচ্ছে।
 return 0; 
}

```
---
# Constructor

##### কনস্ট্রাক্টর হল একটি বিশেষ ধরনের ফাংশন যা কোনো ক্লাসের অবজেক্ট তৈরি করার সময় স্বয়ংক্রিয়ভাবে কল (চালু) হয়। এটি মূলত অবজেক্ট ইনিশিয়ালাইজ করার জন্য ব্যবহৃত হয়।

### 🔹 কনস্ট্রাক্টরের বৈশিষ্ট্য

1. কনস্ট্রাক্টরের নাম ক্লাসের নামের সাথে একই হতে হবে।
    
2. এর কোন **রিটার্ন টাইপ** থাকে না (void ও না!).
    
3. এটি **অটোমেটিক্যালি কল** হয় যখন কোনো ক্লাসের অবজেক্ট তৈরি করা হয়।
    
4. ওভারলোড করা যায় (একাধিক কনস্ট্রাক্টর থাকতে পারে)।
### 🔸 কনস্ট্রাক্টরের প্রকারভেদ

1. **Default Constructor**
    
2. **Parameterized Constructor**
    
3. **Copy Constructor**

```cpp
#include <bits/stdc++.h>

using namespace std;

class Student

{

public:

 int roll;

 int cls;

 double gpa;

 Student(int roll, int cls, double gpa)

 {

 this->roll = roll; // দিস কি-ওয়ার্ড দিয়ে ক্লাস ভেরিয়েবল roll এর মধ্যে কন্সট্রাক্টর ভেরিয়েবল roll কে রেখে দেওয়া হচ্ছে।

 this->cls = cls;

 this->gpa = gpa;

 }

};

int main()
{
 Student rahim(29, 9, 5.);

 Student karim(45, 10, 4.33);

 cout << rahim.roll << " " << rahim.cls << " " << rahim.gpa << endl;

 cout << karim.roll << " " << karim.cls << " " << karim.gpa << endl;

 return 0;
}
```

# Return object from function

```cpp
#include <bits/stdc++.h>

using namespace std;

class Student

{

public:

 int roll;

 int cls;

 double gpa;

 Student(int roll, int cls, double gpa)

 {

 this->roll = roll;

 this->cls = cls;

 this->gpa = gpa;

 }

};

Student *fun() // এবার ফাংশনটি একটি পয়েন্টার রিটার্ন করবে, পয়েন্টার এর টাইপ Student* তাই ফাংশনের রিটার্ন টাইপও Student*

{

 Student rahim(342, 5, 4.99); // কন্সট্রাক্টর কল করে অবজেক্ট ডিক্লেয়ার করা হয়েছে। 

 Student *p = &rahim; // একটি পয়েন্টার নিয়ে তাতে অবজেক্ট এর এড্রেস রেখে দেওয়া হয়েছে। যেহেতু পয়েন্টার একটি Student ক্লাসের অবজেক্টকে পয়েন্ট করছে তাই পয়েন্টার এর ডাটা টাইপ হচ্ছে Student* 

 return p; // পয়েন্টার রিটার্ন করা হচ্ছে। 

}

int main()

{

 Student *ans = fun(); // ফাংশন কল করে ফাংশন থেকে রিটার্ন আসা পয়েন্টার আরেকটি পয়েন্টারে স্টোর করে রাখা হচ্ছে। 

 cout << ans->roll << " " << ans->cls << " " << ans->gpa << endl; // সেই পয়েন্টার কে ডিরেফারেন্স করে ( এক্ষেত্রে শর্টকাটে এরো সাইন ব্যাবহার করা হয়েছে ) তার ভেলু প্রিন্ট করা হচ্ছে। 

 return 0;

}

```