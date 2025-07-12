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

---

# Dynamic Object Creation

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

Student *fun() // ফাংশনটি একটি পয়েন্টার রিটার্ন করবে, পয়েন্টার এর টাইপ Student* তাই ফাংশনের রিটার্ন টাইপও Student*

{

 Student* rahim = new Student(342, 5, 4.99); // new কি-ওয়ার্ড ব্যাবহার করে Student টাইপের একটি ডায়নামিক অবজেক্ট ক্রিয়েট করা হয়েছে। ডায়নামিক অবজেক্ট পয়েন্টারে স্টোর রাখার জন্য একটি পয়েন্টার নেওয়া হয়েছে rahim নামের।

 return rahim; // পয়েন্টার রিটার্ন করা হচ্ছে, যা পয়েন্ট করছে একটি ডায়নামিক অবজেক্টকে। তাই ফাংশন থেকে রিটার্ন হওয়ার পরও এই পয়েন্টার দিয়ে ডায়নামিক অবজেক্টকে এক্সেস করা যাবে। 

}

int main()

{

 Student *ans = fun(); // ফাংশন কল করা হয়েছে এবং ফাংশন থেকে রিটার্ন আসা অবজেক্ট এর পয়েন্টারটি স্টোর রাখার জন্য আরেকটি Student* টাইপের পয়েন্টার নেওয়া হয়েছে।

 cout << ans->roll << " " << ans->cls << " " << ans->gpa << endl; // ডায়নামিক অবজেক্ট প্রিন্ট করা হচ্ছে। 

 delete ans; // প্রিন্ট করার পর ডায়নামিক অবজেক্ট ডিলিট করে দেওয়া যেতে পারে।

 return 0;

}

```

# Sorting in C++
---
### *Format : `sort( starting_pointer, ending_pointer);`

```cpp
#include <bits/stdc++.h>

using namespace std;

int main()

{

 int n;

 cin >> n; // সাইজ ইনপুট নেওয়া হচ্ছে। 

 int a[n]; // সেই সাইজের এরে ডিক্লেয়ার করা হচ্ছে। 

 for (int i = 0; i < n; i++) 

 {

 cin >> a[i]; // এরে ইনপুট নেওয়া হচ্ছে। 

 }

 sort(a, a + n); // ascending order সর্ট ফাংশনের মধ্যে স্টারটিং পয়েন্টার হিসেবে এরের প্রথম ইন্ডেক্স এবং এন্ডিং পয়েন্টার হিসেবে এরের সাইজ দিয়ে দেওয়া হচ্ছে। তাহলে ০ ইনডেক্স থেকে সাইজ-১ ইন্ডেক্স পর্যন্ত সর্ট হবে অর্থাৎ সম্পূর্ণ এরেটি সর্ট হবে। আমরা যদি a+3 লিখতাম তাহলে ০ ইন্ডেক্স থেকে ২ ইনডেক্স পর্যন্ত সর্ট হতো। 
sort(a, a + n, greater<int>()); //descending order সর্ট ফাংশনের মধ্যে স্টারটিং পয়েন্টার হিসেবে এরের প্রথম ইন্ডেক্স এবং এন্ডিং পয়েন্টার হিসেবে এরের সাইজ দিয়ে দেওয়া হচ্ছে। বড় থেকে ছোট অর্ডারে সর্ট করতে চাই তাই greater ফাংশনকে কল করা হয়েছে তার মধ্যে এরের ডাটা টাইপ int দিয়ে দেওয়া হয়েছে। 
 for (int i = 0; i < n; i++)

 {

 cout << a[i] << " "; // এরে প্রিন্ট করা হচ্ছে। 

 }

 return 0;

}
```

# *practice_Problem_1* 

### `Question:`

Create three static objects with the help of the constructor of the following class.

Student  
{  
name;  
roll;  
section;  
math_marks;  
cls;  
}

Then compare those 3 objects and print who got the highest math_marks and print his/her name.


### Solve:

```cpp
#include<bits/stdc++.h>  // সব স্ট্যান্ডার্ড C++ লাইব্রেরি ইনক্লুড করার শর্টকাট
using namespace std;     // বারবার std:: না লিখে সরাসরি cout, cin ব্যবহার করতে পারবো

// Student ক্লাস ডিক্লেয়ার করছি
class student {
public:
    string name;        // স্টুডেন্টের নাম
    int roll;           // রোল নাম্বার
    int section;        // সেকশন নম্বর
    double math_mark;   // গণিতের নাম্বার (double টাইপ, দশমিক সহ)
    int cls;            // কোন ক্লাসে পড়ে

    // Constructor: Object তৈরি করার সময় প্রপার্টি সেট করার জন্য
    student(string n, int r, int s, double mm, int c) {
        name = n;            // নাম সেট করছি
        roll = r;            // রোল সেট করছি
        section = s;         // সেকশন সেট করছি
        math_mark = mm;      // গণিত নাম্বার সেট করছি
        cls = c;             // ক্লাস সেট করছি
    }
};

int main() {
    // ৩টি Static student object তৈরি করছি
    student s1("nirob", 12, 2, 87, 5);
    student s2("tirob", 21, 2, 97, 5);
    student s3("pirob", 15, 2, 99, 5);

    // শুরুতে ধরে নিচ্ছি s1 ই highest
    student highest = s1;

    // যদি s2 এর নাম্বার highest এর চেয়ে বেশি হয়, তাহলে highest কে s2 বানাবো
    if (s2.math_mark > highest.math_mark) {
        highest = s2;
    }

    // এরপর s3 এর নাম্বার যদি highest এর চেয়ে বেশি হয়, তাহলে highest কে s3 বানাবো
    if (s3.math_mark > highest.math_mark) {
        highest = s3;
    }

    // সর্বোচ্চ নাম্বারধারী স্টুডেন্টের নাম আর নাম্বার প্রিন্ট করবো
    cout << highest.name << endl;
    cout << highest.math_mark << endl;

    return 0;  // প্রোগ্রাম শেষ
}

```

# *Practice Problem-2*

### `Question`

**Create a dynamic object named dhoni of the following class. Don’t use a constructor here, that means you need to fill the data by yourself.

Cricketer  
{  
jersey_no;  
country;  
}

Then make another dynamic object named kohli and copy the data of the dhoni object to kohli and after that delete the dhoni object. Then print the jersey_no and country of kohli object.

Note: At first try to do this, kohli=dhoni and see if it gives the correct output. If not, then think deeply why it didn’t work and try to copy the data manually like kohli->jersey_no=dhoni->jersey_no;**

### `Solve:`

```cpp
#include<bits/stdc++.h>  // সব C++ স্ট্যান্ডার্ড লাইব্রেরি ইনক্লুড করার শর্টকাট
using namespace std;     // std:: না লিখে সরাসরি cout, cin ব্যবহার করতে পারবো

// ✅ Cricketer নামে একটি ক্লাস তৈরি করছি
class Cricketer {
public:
    int jersey_no;      // Cricketer এর জার্সি নাম্বার
    string country;     // Cricketer এর দেশের নাম
};

int main() {

    // ✅ Step 1: dhoni নামে Dynamic Object তৈরি করছি
    Cricketer* dhoni = new Cricketer;
    // এখানে new keyword দিয়ে Heap memory তে Cricketer type এর জন্য জায়গা বরাদ্দ করা হলো
    // এবং dhoni pointer সেই জায়গার ঠিকানা ধরে রাখছে।

    // ✅ Step 2: dhoni object এর Data ম্যানুয়ালি সেট করছি
    dhoni->jersey_no = 7;              // dhoni এর জার্সি নাম্বার 7 সেট করছি
    dhoni->country = "India";          // dhoni এর দেশ India সেট করছি

    // ✅ Step 3: kohli নামে আরেকটা Dynamic Object তৈরি করছি
    Cricketer* kohli = new Cricketer;
    // kohli এখন heap memory তে নতুন Cricketer object কে point করছে।

    // ✅ Step 4: ভুল চেষ্টা (পৃথিবি কপি না করে pointer address copy)
    //kohli = dhoni;
    // ⚠️ Warning: এই লাইন চালালে শুধু pointer address copy হবে।
    // অর্থাৎ kohli আর dhoni দুইটাই একই object কে point করবে।
    // তাই এটা কমেন্ট করে রেখেছি।

    // ✅ Step 5: সঠিক উপায় --> Data manually copy করা
    kohli->jersey_no = dhoni->jersey_no;    // dhoni এর জার্সি নাম্বার kohli কে দিচ্ছি
    kohli->country = dhoni->country;        // dhoni এর দেশ kohli কে দিচ্ছি

    // ✅ Step 6: dhoni object delete করা
    delete dhoni;
    // এখানে dhoni pointing করা heap memory free করে দিচ্ছি।
    // এখন dhoni আর কোন valid object point করছে না (dangling pointer হলে Access না করা উচিত)।

    // ✅ Step 7: kohli এর ডেটা প্রিন্ট করা
    cout << kohli->jersey_no << endl;    // kohli এর জার্সি নাম্বার প্রিন্ট করবো
    cout << kohli->country << endl;      // kohli এর country প্রিন্ট করবো
    // এখানে প্রিন্ট হবে:
    // 7
    // India

    // ✅ Step 8: Memory leak রোধের জন্য kohli delete করা (Good Practice)
    delete kohli;
    // kohli এর জন্য আলাদা করে allocate করা heap memory free করা হলো।

    return 0;  // প্রোগ্রাম সফলভাবে শেষ
}
```

# Practice Problem-3

### `Question`

[V. Comparison](https://codeforces.com/group/MWSDmqGsZm/contest/219158/problem/V)

### `solve`
```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){

    int a,b;

    char s;

    cin >> a >> s >> b;

    if( s == '<')

    {

        if (a < b)

        {

            cout << "Right" << endl;

        }

        else

        {

            cout << "Wrong" << endl;

        }

    }

    else if (s == '>')

    {

        if(a>b){cout << "Right" << endl;}

        else

        {

            cout << "Wrong" << endl;

        }

    }

    else if (s == '=')

    {

        if (a==b)

        {

            cout << "Right" << endl;

  

        }

        else{

            cout << "Wrong" << endl;

        }

    }

    return 0;

}
```

# Practice Problem-4

### `Question`

**Problem Statement**

You will be given an array **A** and the size of that array **N**. You need to create a function named **sort_it()**. After taking the input for the size in main function, call that function by giving the size as parameter and take the array input inside that function. After that, you need to sort the array in descending order. Then, return that array from the function and receive it in the main function. Finally, print the sorted array in the main function.

**Input Format**

- First line will contain **N**.
- Second line will contain the array **A**.

**Constraints**

1. 1 <= **N** <= 10^5
2. -10^9 <= **A[i]** <= 10^9 Where 0 <= i < N

**Output Format**

- Ouptut the array in descending order.

```
**Sample Input 0**

5
1 4 2 3 5

**Sample Output 0**

5 4 3 2 1
```

### `Solve`

```cpp
#include<bits/stdc++.h>

using namespace std;

  

int* sort_it(int n)

{

    int* ar = new int[n];  

    for (int i = 0; i < n; i++)

    {

        cin >> ar[i];

    }

  

    sort(ar, ar + n, greater<int>());

  

    return ar;  

}

  

int main() {

    int n;

    cin >> n;  

  

    int* sorted_array = sort_it(n);

  

    for (int i = 0; i < n; i++) {

        cout << sorted_array[i] << " ";

    }

    cout << endl;

  

    delete[] sorted_array;

  

    return 0;

}
```

# Practice Problem-5

**Problem Statement:**

**Amena** has just learned alphabets. She can read write from **a** to **z** only in lowercase. But, Amena always writes in alphabetic order (alphabetic order means from a to z in sorted order) what she saw. Also she writes a line as a word. For example, she writes monkey as ekmnoy. Her mother wants to test her reading and writing skills. Her mother gave her some lines, can you tell what she will write?

**Note**: Input will be given by **EOF**.

**Input Format**

- Input consist of a line **S**. The line will contain lowercase letters and spaces. It is possible that there are multiple spaces together and the line end with spaces.

**Constraints**

1. 1 <= **|S|** <= 10^5

**Output Format**

- Output what Amena will write.

#### `Sample Input 0*
monkey
i love flower
#### `Sample Output 0

ekmnoy
eefilloorvw

### `Solve:`

```cpp
#include<bits/stdc++.h>

using namespace std;
int main()
{

    string s;
    while (getline(cin, s))
    {
        string temp = "";
        for (char c : s) {
            if (c >= 'a' && c <= 'z')

            {
                temp += c;
            }
        }
        sort(temp.begin(), temp.end());

        cout << temp << endl;

    }

    return 0;
}
```


# Practice Problem-6

### `Question`

**Problem Statement**

You will be given an array **A** and the size of that array **N**. Additionally, you will be given a sum **S**. Your task is to determine whether it is possible to select three distinct indexed values from the array such that their summation equals **S**.

**Input Format**

- First line will contain **T**, the number of test cases.
- First line of each test case will contain **N** and **S**.
- Second line of each test case will contain the array **A**.

**Constraints**

1. 1 <= **T** <= 100
2. 1 <= **N** <= 100
3. 1 <= **S** <= 1000
4. 1 <= **A[i]** <= 1000 Where 0 <= i < N

**Output Format**

- Output "**YES**" if it is possible, otherwise output "**NO**".

**Sample Input 0**

5
5 10
1 2 3 4 5
5 6
4 2 3 5 4
3 6
2 2 2
4 4
2 8 1 5
1 3
1

**Sample Output 0**

YES
NO
YES
NO
NO

**Explanation 0**

```
In the first test case, we can make 10 by adding 5+4+1. There are other ways too.
In the second test case, it is not possible to make 6 by adding three different indexed values from the array.
In the third case, it is possible to make 6 by using three different indexed values.
```

### `Solve:`

```cpp
#include <bits/stdc++.h>   // সব C++ স্ট্যান্ডার্ড লাইব্রেরি একসাথে ইমপোর্ট করার শর্টকাট
using namespace std;      // std:: না লিখতে পারার জন্য, সরাসরি cout, cin ব্যবহার করার সুবিধা

int main() 
{
    int T;              // T = টেস্টকেসের সংখ্যা
    cin >> T;           // ইউজার থেকে T এর মান ইনপুট নিচ্ছি

    while (T--)         // T বার এই লুপ চলবে (প্রতিটি টেস্টকেসের জন্য)
    {
        int N, S;       // N = অ্যারের সাইজ, S = টার্গেট স্যাম (যোগফল)
        cin >> N >> S;  // ইউজার থেকে N এবং S ইনপুট নিচ্ছি

        vector<int> A(N);   // N সাইজের ভেক্টর (ডাইনামিক অ্যারে) ডিক্লেয়ার করছি

        for (int i = 0; i < N; i++)  // N বার লুপ চালিয়ে
        {
            cin >> A[i];             // প্রতিটা ভ্যালু ইউজার থেকে ইনপুট নিচ্ছি
        }

        bool found = false;     // found ভ্যারিয়েবল বলে দেবে আমরা কি তিনটি সংখ্যা পেয়েছি নাকি না

        // নিচের তিনটি নেস্টেড লুপ দিয়ে আমরা তিনটি ভিন্ন ইনডেক্সে এমন তিনটি সংখ্যা খুঁজছি যার যোগফল S এর সমান
        for (int i = 0; i < N && !found; i++) 
        {
            for (int j = i + 1; j < N && !found; j++) 
            {
                for (int k = j + 1; k < N && !found; k++) 
                {
                    // যদি তিনটি সংখ্যার যোগফল S এর সমান হয়
                    if (A[i] + A[j] + A[k] == S) 
                    {
                        found = true;    // তাহলে found কে true করে দাও
                    }
                }
            }
        }

        if (found)      // যদি found true হয়
        {
            cout << "YES" << endl;   // আউটপুট দাও "YES"
        }
        else            // না হলে
        {
            cout << "NO" << endl;    // আউটপুট দাও "NO"
        }
    }
    return 0;   // প্রোগ্রাম শেষ
}
```
---

# 📘 C++ String Built-in Functions

---

## 📏 1. Capacity Functions (Capacity সম্পর্কিত)

| Function | কাজ | বাংলা ব্যাখ্যা | উদাহরণ |
|---------|-----|----------------|--------|
| `s.size()` | Returns size of string | স্ট্রিং-এ কয়টি ক্যারেক্টার আছে তা দেয় | `s = "hello"; s.size(); // 5` |
| `s.max_size()` | Max characters possible | স্ট্রিং-এ সর্বোচ্চ কত ক্যারেক্টার রাখা যাবে | `s.max_size();` |
| `s.capacity()` | Current storage size | স্ট্রিং কতটা জায়গা রিজার্ভ করে রেখেছে | `s.capacity();` |
| `s.clear()` | Clears the string | স্ট্রিং খালি করে দেয় | `s.clear();` |
| `s.empty()` | Checks if empty | খালি কিনা জানায় (true/false) | `s.empty(); // true/false` |
| `s.resize(n)` | Resizes string | স্ট্রিং-কে নির্দিষ্ট দৈর্ঘ্যে ছোট/বড় করে | `s = "hi"; s.resize(5); // "hi\0\0\0"` |


## 🔍 2. Element Access (উপাদান অ্যাক্সেস)

| Function | কাজ | বাংলা ব্যাখ্যা | উদাহরণ |
|----------|-----|----------------|--------|
| `s[i]` | Access ith char | i-তম পজিশনের ক্যারেক্টার দেখায় | `s = "hello"; s[1]; // 'e'` |
| `s.at(i)` | Safe access | `s[i]` এর মত, কিন্তু error চেক করে | `s.at(3); // 'l'` |
| `s.front()` | First char | প্রথম ক্যারেক্টার দেয় | `s.front(); // 'h'` |
| `s.back()` | Last char | শেষ ক্যারেক্টার দেয় | `s.back(); // 'o'` |

## ✍️ 3. Modifiers (স্ট্রিং পরিবর্তন)

| Function | কাজ | বাংলা ব্যাখ্যা | উদাহরণ |
|----------|-----|----------------|--------|
| `s += str` | Append | আরেকটা স্ট্রিং যোগ করে | `s += "world";` |
| `s.append(str)` | Append | আরেকটা স্ট্রিং যুক্ত করে | `s.append("world");` |
| `s.push_back(c)` | Add char at end | শেষে ক্যারেক্টার যুক্ত করে | `s.push_back('!');` |
| `s.pop_back()` | Remove last char | শেষ ক্যারেক্টার মুছে ফেলে | `s.pop_back();` |
| `s = str` | Assign string | নতুন স্ট্রিং সেট করে | `s = "new";` |
| `s.assign(str)` | Assign string | `=` এর মতই কাজ করে | `s.assign("new");` |
| `s.erase(pos, len)` | Erase part | নির্দিষ্ট অংশ মুছে ফেলে | `s.erase(1, 2);` |
| `s.replace(pos, len, str)` | Replace part | অংশ রিপ্লেস করে | `s.replace(0, 3, "Hi");` |
| `s.insert(pos, str)` | Insert part | নির্দিষ্ট স্থানে স্ট্রিং ঢুকায় | `s.insert(2, "oo");` |

## 🔁 4. Iterators (স্ট্রিং ট্রাভার্স করার জন্য)

| Function    | কাজ               | বাংলা ব্যাখ্যা             | উদাহরণ                                            |
| ----------- | ----------------- | -------------------------- | ------------------------------------------------- |
| `s.begin()` | Iterator at start | স্ট্রিংয়ের শুরুতে পয়েন্টার | `*s.begin(); // 'h'` this are basically a pointer |
| `s.end()`   | Iterator at end   | শেষের পর পয়েন্টার দেয়      | `*(s.end() - 1); // 'o'`                          |
### example:
```cpp
#include<bits/stdc++.h>

using namespace std;

 

int main() {

 string s;

 cin >> s;

 

 // for(int i=0;i<s.size();i++)

 // {

 // cout<<s[i]<<endl;

 // }

  cout<<*s.begin()<<endl; // prints only the first char of the string

  cout<<*(s.end()-1)<<endl; // prints only the last char of the string

 

 for(auto it = s.begin(); it < s.end(); it++) {

 cout << *it << endl; // prints the full string by iterating

 }

 

 return 0;

}

```

it = s.begin() ইটারেটরকে স্ট্রিংয়ের প্রথম ক্যারেক্টারের পজিশনে সেট করে।
it < s.end() লুপটি চলবে যতক্ষণ না ইটারেটর স্ট্রিংয়ের শেষে পৌঁছে যায়।
*it বর্তমান ইটারেটরের নির্দেশিত ক্যারেক্টারকে নির্দেশ করে এবং তা প্রিন্ট করা হয়।

---
# String Input With Spaces

```cpp
#include<bits/stdc++.h>
using namespace std; 

int main() {

    string s; // একটি string টাইপ ভেরিয়েবল 's' ডিক্লেয়ার করা হলো

    getline(cin, s); // পুরো লাইন ইনপুট নেওয়া হচ্ছে, স্পেস সহ

    cout << s << endl; // ইনপুট নেওয়া স্ট্রিংটি আউটপুট দেওয়া হচ্ছে

    return 0; // প্রোগ্রাম সফলভাবে শেষ হলো বোঝাতে 0 রিটার্ন করছে

}

```

## ব্যাখ্যা:

string s;: একটি স্ট্রিং ভেরিয়েবল ঘোষণা করা হয়েছে।
`getline(cin, s);: getline()` ফাংশনটি ব্যবহার করে কনসোল থেকে স্ট্রিং ইনপুট নেয়। এটি স্পেস সহ সমস্ত লাইন পড়ে স্ট্রিং ভেরিয়েবলে রাখে। `cout << s <<`

`endl;:`  ইনপুট নেয়া স্ট্রিং স্পেস সহ সমস্ত লাইন পরিদর্শন করে।
এই উদাহরণে, `getline()` ফাংশন ব্যবহার করা হয়েছে যার ফলে স্ট্রিং ইনপুটের সময় স্পেস ও গ্রহণ করা হয়।
## Important Note:

আপনি যদি `getline()` ব্যবহার করার আগে` cin.ignore()` ফাংশনটি ব্যবহার করেন, তবে এটি ইনপুট বাফার থেকে অবশিষ্ট অক্ষরগুলি মুছে ফেলে (যেমন আগের ইনপুট থেকে Enter কি)। এটি পরবর্তী `getline()` আরও সঠিকভাবে কাজ করতে সাহায্য করে।

---

# Stringstream

```cpp
#include <iostream>
#include <string>
#include <sstream>
using namespace std;

int main()
{
    string s = "Hello world!";

    // 1st way: স্ট্রিং সরাসরি Constructor দিয়ে stringstream তৈরি
    stringstream ss(s);

    // 2nd way: স্ট্রিং "<<" অপারেটর দিয়ে stringstream তৈরি
    // stringstream ss;
    // ss << s;

    string word;

    ss >> word;  // প্রথম শব্দটা পড়া

    cout << word << endl;  // প্রিন্ট করা

    return 0;
}
```

### ব্যাখ্যা:
1. `string s = "Hello world!";` → একটি স্ট্রিং ঘোষণা করা হয়েছে।
2. `stringstream ss(s);` → s কে stream বানানো হয়েছে।
3. `ss >> word;` → stream থেকে প্রথম শব্দ (Hello) বের করে word-এ রাখা হয়েছে।
4. `cout << word;` সেই শব্দটি প্রিন্ট করা হয়েছে।

### we can also use loop to do this

```cpp
#include <iostream>
#include <sstream>
#include <string>
using namespace std;

int main() {
    string s = "C++ is fun";
    
    // stringstream-এর মধ্যে সরাসরি স্ট্রিং ইনপুট দেওয়া
    stringstream ss(s);

    string word;
    while (ss >> word) {
        cout << word << endl;
    }

    return 0;
}
```

