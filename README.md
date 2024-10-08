# Experiment 12

**Aim:** <br>
To study and implement constructors and destructors. <br>
<br>
**Theory:** <br>
Constructors: <br>
<br>
Constructors are unique member functions of a class that are automatically called when an object of the class is created. The object’s data members are initialized. Resources may also be allocated when required. <br>
There are some key points about costructors which are: <br>

&#8594; The name of the constructor is same as its class name. <br>

&#8594; Constructors do not have a return type. <br>

&#8594; Constructors are mostly declared in the public section of the class. <br>

&#8594; Multiple constructors can be defined with different parameters, this is known as overloading. <br>

<br>
There are mainly 3 types of constructors. They are: <br>

_Default Constructor:_ <br>
A constructor which takes no arguments. It is also called a zero-argument constructor as it has no parameters. <br>

_Parameterized Constructor:_  <br>
A constructor that takes parameters, allowing the object to be initialized with specific values. <br>

_Copy Constructor:_  <br>
A constructor that initializes an object using another object of the same class. It is used for deep copying and when passing objects by value. <br>
<br>

Destructors <br>
A destructor is a special member function which destroys the class objects created by the constructor. It has the same name as their class name preceded by a _tilde_ (~) symbol.
There are some key points about destructors which are: <br>

&#8594; They neither require any argument nor do they return any value. <br>

&#8594; They release memory space which are occupied by the objects created by the constructor. <br>

&#8594; Destructor cannot be overloaded. <br>

&#8594; Objects are destroyed in the reverse of an object creation. <br>

&#8594; Only one destructor can be defined. <br>
<br>

**Code:** <br>
<br>
a.<br>

```
//Vanshika Singh
//23070123148
#include <iostream>
using namespace std;

//defining constructor inside the class
class student
{
    int rn;
    char n[50];
    float avg = 0.0;
    public:
    student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
}
void display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<"%"<<endl;
}
};
int main()
{
    student s1;
    s1.display();
}

```
<br>
b.<br>

```
//Vanshika Singh
//23070123148
#include <iostream>
using namespace std;

//defining the constructor outside the class
class student
{
    int rn;
    char n[50];
    float avg;
    public:
    student();
    void display();
};
student::student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
}
void student::display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<endl;
}
int main()
{
    student s1;
    s1.display();
}

```
<br>
c.<br>

```
//Vanshika Singh
//23070123148

#include <iostream>
using namespace std;

//types of constructor - default constructor
class student
{
    int rn;
    char n[50];
    double m1, m2, m3;
    public:
    student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the subject 1 marks: ";
    cin>>m1;
    cout<<"Enter the subject 2 marks: ";
    cin>>m2;
    cout<<"Enter the subject 3 marks: ";
    cin>>m3;
}

void display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Marks for subject 1: "<<m1<<endl;
    cout<<"Marks for subject 2: "<<m2<<endl;
    cout<<"Marks for subject 3: "<<m3<<endl;
}
};
int main()
{
    student s1;
    s1.display();
}

```
<br>
d.<br>

```
//Vanshika Singh
//23070123148
#include <iostream>
using namespace std;

//types of constructor - parameterized constructor
class maxop
{
    public:
    maxop(int a, int b)
{
    cout<<"First Number: "<<a<<endl;
    cout<<"Second Number: "<<b<<endl;
    cout<<endl;
    if (a>b)
    {
        cout<<"The first number is greater than the second.";
    }
    else if (b>a)
    {
        cout<<"The second number is greater than the first. ";
    }
    else
    {
        cout<<"Both numbers are equal. ";
    }
}
};

int main()
{
    maxop n1(23,76);
}

```
<br>
e.<br>

```
//Vanshika Singh
//23070123148

#include<iostream>
#include<string.h>
using namespace std;

//types of constructors - copy constructor
class student
{
    int rn;
    char n[50];
    float avg = 0;
    public:
    student(int,char[],float);

    student(student &t)
    {
        rn=t.rn;
        strcpy(n,t.n);
        avg=t.avg;
    }
    void display();

};

 student::student(int rno,char na[],float av)
 {
    rn=rno;
    strcpy(n,na);
    avg=av;
 }

void student::display()
 {
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<" %"<<endl;
 }

int main()
{
    student s1(36,"Lewis",93.7);
    s1.display();

    student lewis(s1);
    lewis.display();

    return 0;
}
    
```
<br>
f.<br>

```
//Vanshika Singh
//23070123148
# include<iostream>
using namespace std;
int c = 0;
//using a destructor
class destruct
{
    public:
    destruct()
    {
        c++;
        cout<<"Number of objects created: "<<c<<endl;
    }
    ~destruct()
    {
        c--;
        cout<<"Number of objects destroyed: "<<c<<endl;
    }
};

int main()
{
    destruct aa,bb,cc,dd;
}

```
<br>

**Outputs:**  <br>
<br>
a.<br>
![12a](https://github.com/user-attachments/assets/b9fdf2db-d2f7-42fe-bb8f-7e8807391b1b)

 <br>
b.<br>
 ![12b](https://github.com/user-attachments/assets/46991b44-dc4f-4a74-8912-334a042686be)
 <br>

c.<br>
![12c](https://github.com/user-attachments/assets/8ac7f312-ef6c-41e8-9407-bdc61e99e1a7)

 <br>
d.<br>
![12d](https://github.com/user-attachments/assets/61ad1465-2f2c-46ac-9a9a-027196a6ab03)

 <br>
e.<br>
![12e](https://github.com/user-attachments/assets/dc323f19-959b-4947-90c6-0e6fcfa2ea34)

 <br>
f.<br>
![12f](https://github.com/user-attachments/assets/44336c84-1fd9-4bfe-bc7e-f15913e764df)

<br>



<br>

**Conclusion:** <br>
&#8594; We learnt about constructors and deconstructors in C++. <br>
&#8594; We learnt the use case of each of them in C++. <br>
*******
<br>
