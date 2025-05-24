four piller in java OOO
1) Encapsulation: 
	* improve security & modularity
	* makes the class easier to use and maintain.
How in Java: use private for fields, provide public getter setter.
   _____________________________________
  | public class Employee {		|
  |  private String name;		|
  |					|
  |  public String getName() {		|
  |      return name;			|
  |  }					|
  |					|
  |  public void setName(String name) {	|
  |      this.name = name;		|
  |  }					|
  | }					|
  _______________________________________
LeetCode #1603 (Design Parking system);

2) Abstraction: 
	* helps in managing complexity
	* increase reusability & maintenance.
How in Java: use abstract class or interface 
  _____________________________________
  interface Animal {
    void makeSound();
}

class Dog implements Animal {
    public void makeSound() {
        System.out.println("Bark");
    }
}
  ______________________________________

3) Inheritence:one class(child/subclass) inherit the methods and fields of 
another class(superclass/parent)
	why it matter: 
		*code reusabilty
		*supports hierarchical classification
	How in Java:
		* using extends keywords
 super keywords give parent class variable, this.objname gives child class variable
 -----------------------------------------------
 class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
 }

 class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
 }
------------------------------------------------
4)Polymorphism:Ability of one interface to used for diffrent underlying forms(data type)
	same method name
	Types: *compile time (method overloading) (diffrent no,type of parameter)
		*runtime (method overriding) (same name, same parameter & IS-A relationship)
------------------------------------------------------------------------------------
SOLID Principles
S- Single Responsibilty principle : (one class one job): {one class one method or task}
O- open/closed principle: 
L- Liskov substitution principle
I- interface segregation principle
D- Dependency Injection principle


INterview question done.



		
