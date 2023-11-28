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
> * 1. Remove ambiguity permenantly. 

<br><br>

### 1. Remove ambiguity permenantly :
> * removes ambiguity permenantly from the hybrid inheritence.

<br>

## Abstract class (Pure virtual function) :

> * It is a type of class which cannot be instanciated. we cannot create object of that class.
> * Abstract class to which we can not create any object.
> * In C++, abstract class can be created using pure virtual function.
> * pure virtual method can be created using virtual keyword and initial value ZERO.
> * `virtual returnType functionName([arguments]) = 0;`
> * pure virtual function can't have body in current class but it will be defined(create body) into it's child class.
> * if we won't define it into child class with same signatures(name, parameters, return type), the child class also will be abstract.


<br><br>

<pre>
  #include<iostream>
using namespace std;

class Google {
	
	protected:
		string email;
		string psw;
	
		virtual void signIn(string email,string psw) = 0;
	
	public:	
	
		void getCredentials() {
			cout << "Email\t\t: " << email << endl
				 << "Password\t: " << psw << endl;
		}
		
};

class DemoApp : public Google {
	
	string e,p;
	
		void signIn(string e,string p) {
			email = e;
			psw = p;
		}
	
	public:	
		void signInWithGoogle() {
			
			cout << "Enter email: ";
			cin  >> e;
			cout << "Enter password: ";
			cin  >> p;
			
			signIn(e,p);
			
		}
	
};

int main()
{
	DemoApp d;
	
	d.signInWithGoogle();
	
	d.getCredentials();
}

</pre>












