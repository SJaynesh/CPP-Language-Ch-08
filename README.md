# Polymorphism 

<br>

## What is Polymorphism ?

<br>

> * Polymorphism is a fundamental concept in object-oriented programming (OOP).
> * `Poly` => Many/Multiple/different
> * `Morphs` => Forms / Structure / behaviour

<br><br> 

> * `It is a concept where any method or attribute have multiple/different behaviours.`

<br>


<p><img src = "https://github.com/SJaynesh/CPP-Languge-Ch-08/assets/115562979/414d8227-6bbb-4224-a83f-954a69e415aa.png" width=60% height=50%></p>

<br><br>

https://github.com/SJaynesh/CPP-Languge-Ch-08/assets/115562979/d7381d88-6185-4fca-a096-822453572612

<br><br>

<p><img src = "https://github.com/SJaynesh/CPP-Languge-Ch-08/assets/115562979/b0b55836-0ee9-4cf2-98e8-6f86e37db0e2.png" width=80% height=80%></p>

<br><br>

## Types of Polymorphism :

<br>

### Compile time polymorphism (Static polymorphism) : 
  > * 1. `Method Overloading`
  > * 2. `Operator Overloading`

<br>

### Run Time polymorphism (Dynamic polymorphism) :
  > * 1. `Method Overriding`
  > * 2. `Virtual function`

<br><br>

### Method Overloading :

<br>

#### `Rules :`

<br>

> 1. Multiple methods at Same class (2 or more methods) .
> 2. All methods name must be same.
> 3. Parameters must be different.

<br>

> * `Create same named method multitimes in same class with different parameters.`

<br><br>

<pre>
    * Class	  : Same
    * Method Name : Same
    * Parameters  : different
</pre>

<br>

https://github.com/SJaynesh/CPP-Languge-Ch-08/assets/115562979/35ae3714-063b-44ce-8790-e42a0b9d76f9

<br><br>

<pre>
	#include<iostream>
using namespace std;

class A
{
    public:
        void truck()
        {
            cout << "Empty truck is running" << endl;
        }
        
        void truck(int n)
        {
            cout << "The truck is running with " << n << " items" << endl;
        }
        
        void truck(int n, float o)
        {
            cout << "The truck is running with " << n << " items and " << o << " weight " << endl; 
        }
        
        void truck(float n)
        {
            cout << "Value of " << n << endl;
        }
};

int main()
{
    
    A o1;
    
    o1.truck();
    o1.truck(10);
    o1.truck(10,50.20);
    o1.truck(25.35f);
}
</pre>


<br><br>

### Method Overriding (Overwriting): 

<br><br>

#### `Rules :`

<br>

> 1. Multiple methods (2 or more methods) .
> 2. All methods name must be same.
> 3. Parameters must be different.
> 4. Derive in multiple classes (2 or more class).
> 5. Inheritance is required.

<br>

> * `Create same named method in derived class with same parameters.`

<br>

<pre>
    * Class	   : Different
    * Method Name  : Same
    * Parameters   : Same
</pre>

<br><br>

## Diffrent between Method Overloading and Method Overriding 

<br>

<p><img src = "https://github.com/SJaynesh/CPP-Languge-Ch-08/assets/115562979/c169be06-f0d8-4b31-8213-3c7dbaed163e.png" width=80% height=80%></p>

<br><br>

## Operator Overloading (Overload binary & unary operator) :

> * `A Method to perform operation between objects of same class. `
> * It automatically invokes a method named 'operator ( +,-,*,/,>,<,...)'




<br>

### Two types :

> * `Unary ` => ++ , --
> * `Binary` => +,-,*,/,>,<

<br>

### Binary Operator Overloading :

<pre>
  Example : 

  #include<<iostream>iostream>
  using namespace std;

  class Demo {
  	
  	private :
  		
  		int a;
  		
  	public :
  		
  		void setData() {
  			cout << endl << "Enter a : ";
  			cin >> a;
  		}
  		
  		void getData() {
  			cout << endl << "A\t: " << a << endl;
  		}
							 
  		Demo operator+(Demo d2) 
  		{
  			Demo d3;
  			
  			d3.a = a + d2.a;
  			
  			return d3;
  		}
  		
  		bool operator<(Demo d2)
  		{
  			if(a < d2.a) 
  			{
  				return true;
  			}else {
  				return false;
  			}
  		}
  };
  
  int main() {
  	
  	Demo d1,d2,d3;
  	
  	d1.setData();
  	d2.setData();
  	
   	// d3 = d1 + d2; // d1.operator+(d2)
  
	if(d1 < d2) //d1.operaor<(d2)
	{ 
		cout << endl << "d2 is maximum" << endl;
	}
	else 
	{
		cout << endl << "d1 is maximum" << endl;
	}
	  	
  	d1.getData();
  	d2.getData();
  	d3.getData();
  	
}
</pre>

<br><br>

<pre>
	#include<<iostream>iostream>
	using namespace std;
	
	class Demo {
		int a,b;
		
		public :
			
			void setData() {
				cout << "Enter a : ";
				cin >> a;
				cout << "Enter b : ";
				cin >> b;	
			}
			
			void getData(string obj) {
				cout << endl << obj << " A : " << a 
					 << endl << obj << " B : " << b << endl;
			}
			
			Demo operator+(Demo d2) {
				Demo tmp;
				
				tmp.a = a + d2.a;
				tmp.b = b + d2.b;
				
				return tmp;
				
			}
	};
	
	
	int main() {
		
		Demo d1,d2,d3;
		
		d1.setData();
		d2.setData();
		
		d3 = d1 + d2; // d1.operator+(d2);
		
		d1.getData("d1");
		d2.getData("d2");
		d3.getData("d3");
	}
</pre>

<br><br>

### Unary Operator Overloading :

<br>

<pre>
	#include<<iostream>iostream>
	using namespace std;
	
	class Demo {
		int a;
		
		public :
			
			void setData() {
				cout << "Enter a : ";
				cin >> a;
			}
			
			void getData(string obj) {
				cout << endl << obj << " : " << a << endl;
			}
			
			Demo operator++(int n) {
				Demo tmp;
				
				tmp.a = a++;
				
				return tmp;
			}
			
			Demo operator--() {
				Demo tmp;
				
				tmp.a = --a;
				
				return tmp;
			}
	};
	
	
	int main() {
		
		Demo d1,d2;
		
		d1.setData();
		
		// Post Increment
		d2 = d1++;// d1 + 1 // d1.operator++(1);
		
		d1.getData("D1");
		d2.getData("D2");
		
		// Pre Decrement
		d2 = --d1; // d1.operator--();
		
		d1.getData("D1");
		d2.getData("D2");
		
	}
</pre>








