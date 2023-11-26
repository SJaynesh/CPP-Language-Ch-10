# Data Abstraction 

<br><br> 

## What is Data Abstraction (To Secure / To Restrict):
> * `To hide some methods from direct contact of public users. we can abstract them using different OOP abstraction(restriction).`
> * Abstraction is process of a hiding implementation the details from the user.
> * hide logic and display only essencial part of interface(ui) to the user.
> * prevent the user from accessing the app data.

<br><br>

<p><img src = "https://github.com/SJaynesh/CPP-Languge-Ch-10/assets/115562979/c4ac0428-7e65-4f4a-86da-a960c545450f.png" width=60% height=80%></p>

<br>

<p><img src = "https://github.com/SJaynesh/CPP-Languge-Ch-10/assets/115562979/3ee115ab-961c-47e7-992e-1222fd959b19.png" width=60% height=80%></p>

<br>

<p><img src = "https://github.com/SJaynesh/CPP-Languge-Ch-10/assets/115562979/03dd6e0b-c8ab-45a6-b53a-51bedbfbc7e9.png" width=60% height=50%></p>

<br><br>

https://github.com/SJaynesh/CPP-Languge-Ch-10/assets/115562979/ce02c4cf-2a08-4a58-917b-1f0025f5cecf



br><br>

## Methods :
<br>

### 1. Using access modifiers :
> * public, private, protected.

<br>

### 2. Using Abstract class.

<br><br>


## Access Modifiers in Inheritance (Use of public, private, and protected) :

> * Access modifiers use in inheritance so it's called `Visibility Modifiers / specifiers`.

<br><br>

Data Member / Memeber Function | Private    | Protected | Public
-------------| --------   | --------- | ------- 
Inherit Private | Not Access | Private | Private.
Inherit Protected | Not Access | Protected | Protected.
Inherit Public | Not Access | Protected | Public.

<br>

<pre>
  #include<iostream>
  using namespace std;
  
  class A {
  	
  	private :
  		int a,b;
  	protected:
  		int c,d;
  	public :
  		
  		void setDataA() {
  			a = 10, b = 20, c = 30, d = 40;
  		}
  		
  		void getDataA() {
  			cout << endl << "A : " << a 
  				 << endl << "B : " << b
  				 << endl << "C : " << c 
  				 << endl << "D : " << d << endl;
  		}
  	
  };
  
  class B : private A{
  	private :
  		int m,n;
  	protected:
  		int o,p;
  	public :
  		
  		void setDataB() {
  			
  			setDataA();
  			
  			m = 10, n = 20, o = 30, p = 40;
  		}
  		
  		void getDataB() {
  			
  			getDataA();
  			
  			cout << endl << "M : " << m 
  				 << endl << "N : " << n
  				 << endl << "O : " << o
  				 << endl << "P : " << p << endl;
  		}
  };
  
  int main() {
  	B b1;
  	
  //	b1.setDataA();
  	b1.setDataB();
  	
  //	b1.getDataA();
  	b1.getDataB();
  }
</pre>

<br><br>

## Pointer object :

> * pointer is a object which stores address of another object.


<br>

<pre>
  #include<iostream>
  using namespace std;
  
  class Student {
  	
  	private :
  		int id;
  		string name;
  		double per;
  		
  	public :
  		void setData() {
  			cout << endl << "Enter your Id : ";
  			cin >> id;
  			cout << "Enter your Name : ";
  			cin >> name;
  			cout << "Enter your Percentage : ";
  			cin >> per;
  		}
  		
  		void getData() {
  			cout << endl << "Id\t: " << id 
  				 << endl << "Name\t: " << name
  				 << endl << "Per\t: " << per << endl;
  		}
  };
  
  
  int main() {
  	
  	Student s1;
  	
  	// Pointer Of Object
  	Student *ptr;
  	
  	// Store another object address in Pointer
  	ptr = &s1;
  	
  	//To Calls Methods
  	ptr->setData();
  	ptr->getData();
  	
  }
</pre>

<br><br>

## Virtual Function :

> * Virtual Function is use virtual keyword.

> * Virtual Keyword to use :
> * 1. Reverse the flow of inheritence.
> * 2. Remove ambiguity permenantly. 

<br>

### 1. Reverse the flow of inheritence :
> * Class must be inherited.
> * Child class fields can be accessed using Parent class.
> * Create a Pointer of Object.

<br><br>

<pre>
  #include<iostream>
  using namespace std;
  
  class A {
  	
  	public :
  		
  		virtual void print() {
  			cout << endl << "BASE CLASS" << endl;
  		}
  };
  
  class B : public A {
  	
  	public :
  		
  		void print() {
  			cout << endl << "CHILD CLASS" << endl;
  		}
  };
  
  
  int main() {
  	
  //	B b1;
  //
  //	b1.print();
  
  
  
  //	A *ptr;
  //	A a1;
  //
  //	ptr = &a1;
  //
  //	ptr->print();
  
  
  	A *ptr;
  	
  	B b1;
  	
  	ptr = &b1;
  	
  	ptr->print();
  	
  }
</pre>

<br><br>

### 2. Remove ambiguity permenantly :
> * removes ambiguity permenantly from the hybrid inheritence.













