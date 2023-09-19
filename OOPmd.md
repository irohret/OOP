
# Objects Oriented Programming Notes 

## What is Object-oriented programming? 
Object-oriented programming (OOP) is a programming paradigm that uses objects to represent and manilulate data and their interactsion. 

## Structure of OOP
OOP is contructed of this four builiding blocks:
- Classes
  - Are User-defined data types that acts like the blueprint for object, atribtes, and methods
- Objects
  - Are instances of a class with specific defined data
  - when a class is defined there is not memory allocated to it, but when a object is created from that class then memory is allocated
- Methods
  - Are fucnitosn that are defined inside a classs that help define a object hehavior
- Attirbutes
  - Are defiens in the Class template and represent that the sstat of an object

# Principles of OOP
- INHERITANCE 
  - Process of acquireing traits form parent class 

- POLYMORPHISM 
  - Popery to act diffently under different conditions 

-  ENCAPSULATION 
   - Hides all unnecessay complex porcessing by packing all related data & methods inot a single unit called class 

-  ABSTRACTION 
   - Expose only what is necesary and hides unnecessary details


e.g. Classes / Object 
---

<details>
    <summary>C++</summary>

```C++
#include <iostream>
#include <string.h>

using namespace std;

class Person {                                  // The class
    public:                                     // Access specifieir
        string name;                            // Attributes
        string major;
        int age;
    
    void print_person_info(){                   // Method  inseid the class
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Major: " << major << endl;
    }
};

// void Person::print_person_info();            // Method define outside the class

int main(int argc, char **argv){
    Person p1;                                  // Object  of the class

    p1.age = 23;                                //Access attributes
    p1.major = "Computer Science";
    p1.name = "John";

    p1.print_person_info();

    return 0;
}
```
</details>


<details>
    <summary>Java</summary>
  
```java
class Person {
    String name;
    String major;
    int age;

    void print_info(){
        System.out.println("Name : " + name);
        System.out.println("Age : " + age);
        System.out.println("Major : " + major);
    }

    public static void main(String[] args){
        Person p1 = new Person();
        p1.name = "John";
        p1.age = 23;
        p1.major = "Computer Science";
        p1.print_info();
    }
}
```
</details>

### Output
```
Name: John
Age: 23
Major: Computer Science
```
    
<hr style="border:2px solid gray">

### e.g. Constructor/**__ INIT __**
<details>
    <summary>C++</summary>

```C++
#include <iostream>
#include <string.h>

using namespace std;

class Person {
    public:
        string name;
        string major;
        int age;

        // Constructor with parameteres
        Person(string init_name, int init_age, string init_major){
            name = init_name;
            age = init_age;
            major = init_major;
        }
    }
    
    void print_person_info(){           // Method
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Major: " << major << endl;
    }
};

int main(int argc, char **argv){

    Person p1("Summer", 18, "Math"); // Create Person Object and call constructore
    p1.print_person_info();         // print info

    return 0;
}
```
</details>


<details>
    <summary>Java</summary>
  
```java
class Person {
    String name;
    String major;
    int age;

    Person(String name, int age, String major){
    	this.name = name;
    	this.major = major;
        this.age = age;
    }

    void print_info(){
        System.out.println("Name : " + name);
        System.out.println("Age : " + age);
        System.out.println("Major : " + major);
    }

    public static void main(String[] args){
        Person p1 = new Person("Summer", 18, "Math");
        p1.print_info();
    }
}
```
</details>

### Output
```
Name: Summer
Age: 18
Major: Math
```
# Polymorphism
<details>
    <summary>C++</summary>

```C++
#include <iostream>
#include <string.h>

using namespace std;

class Person {
    public:
        string name;
        string major;
        int age;

        // Constructor with parameteres
        Person(string init_name, int init_age, string init_major){
            name = init_name;
            age = init_age;
            major = init_major;
        }
    }
    
    void print_person_info(){           // Method
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Major: " << major << endl;
    }
};

int main(int argc, char **argv){

    Person p1("Summer", 18, "Math"); // Create Person Object and call constructore
    p1.print_person_info();         // print info

    return 0;
}
```
</details>

# Encapsulation

# Inheritance
<details>
    <summary>C++</summary>

```C++
#include <iostream>
#include <string>

using namespace std;

class Animal {                                  // The class
    public:
        string animal_name;
        string environment;
        double age;
        string food; 
        int num_of_legs;

    Animal(string animal_name){
        this->animal_name = animal_name;
    }

    void print_food(){
        cout << animal_name << " likes to eat: " << food << endl;
    }

    void print_lifespan(){
        cout << "The life span of a " << animal_name << " is: " << age << endl;

    }

    void print_living_environment(){
        cout << animal_name << " love to live in " << environment << " environment" << endl;
    }
};

class Mammals : public Animal {
    public:
        string type;
    
    Mammals(string animal_name, string type) : Animal(animal_name){
        this->type = type; 
    }
    
    void print_fur_or_hair(){
        cout << animal_name << " has " << type << endl;
    }

    void print_blood(){
        cout << animal_name << " has warn blood" << endl;
    }

    void print_milk(){
        cout << animal_name << " drinks Milk" << endl;
    }
};

class Reptiles : public Animal {
    public:
        Reptiles(string animal_name) : Animal(animal_name){}

    void print_blood(){
        cout << animal_name << " has cold blood" << endl;
    }

    void print_scales(){
        cout << animal_name << " has scales" << endl;
    }
};

class Amphibians  : public Animal {
    public:
        int legs;
    
    Amphibians (string animal_name, int legs) : Animal(animal_name){
        this->legs = legs; 
    }

    void print_blood_type(){
        cout << animal_name << " has cold blood" << endl;
    }
    
    void print_legs(){
        cout << animal_name << " have " << legs << " legs" << endl;
    }
};

int main(int argc, char **argv){

    Mammals lion("Lion", "fur");
    lion.food = "meat";
    lion.age = 15;
    lion.environment = "grasslands";

    lion.print_food();
    lion.print_lifespan();
    lion.print_living_environment();
    lion.print_fur_or_hair();
    lion.print_blood();
    lion.print_milk();
    
    printf("\n");

    Reptiles snake("Snake");
    snake.food = "rodents";
    snake.age = 25;
    snake.environment = "desert";

    snake.print_food();
    snake.print_lifespan();
    snake.print_living_environment();
    snake.print_blood();
    snake.print_scales();

    printf("\n");

    Amphibians frog("Frog", 4);
    frog.food = "insects";
    frog.age = 11;
    frog.environment = "pond";

    frog.print_food();
    frog.print_lifespan();
    frog.print_living_environment();
    frog.print_blood_type();
    frog.print_legs();
    printf("\n");
    return 0;
    
}
```
</details>


<details>
    <summary>Java</summary>
  
```java
public class Animal {
    public String animal_name;
    public String environment;
    public double age;
    public String food;
    public int num_of_legs;

    public Animal(String animal_name) {
        this.animal_name = animal_name;
    }

    public void print_food() {
        System.out.println(animal_name + " likes to eat: " + food);
    }

    public void print_lifespan() {
        System.out.println("The life span of a " + animal_name + " is: " + age);
    }

    public void print_living_environment() {
        System.out.println(animal_name + " loves to live in " + environment + " environment");
    }
}

public class Mammals extends Animal {
    public String type;

    public Mammals(String animal_name, String type) {
        super(animal_name);
        this.type = type;
    }

    public void print_fur_or_hair() {
        System.out.println(animal_name + " has " + type);
    }

    public void print_blood() {
        System.out.println(animal_name + " has warm blood");
    }

    public void print_milk() {
        System.out.println(animal_name + " drinks Milk");
    }
}

public class Reptiles extends Animal {
    public Reptiles(String animal_name) {
        super(animal_name);
    }

    public void print_blood() {
        System.out.println(animal_name + " has cold blood");
    }

    public void print_scales() {
        System.out.println(animal_name + " has scales");
    }
}

public class Amphibians extends Animal {
    public int legs;

    public Amphibians(String animal_name, int legs) {
        super(animal_name);
        this.legs = legs;
    }

    public void print_blood_type() {
        System.out.println(animal_name + " has cold blood");
    }

    public void print_legs() {
        System.out.println(animal_name + " have " + legs + " legs");
    }
}

public class Main {
    public static void main(String[] args) {
        Mammals lion = new Mammals("Lion", "fur");
        lion.food = "meat";
        lion.age = 15;
        lion.environment = "grasslands";

        lion.print_food();
        lion.print_lifespan();
        lion.print_living_environment();
        lion.print_fur_or_hair();
        lion.print_blood();
        lion.print_milk();

        System.out.println();

        Reptiles snake = new Reptiles("Snake");
        snake.food = "rodents";
        snake.age = 25;
        snake.environment = "desert";

        snake.print_food();
        snake.print_lifespan();
        snake.print_living_environment();
        snake.print_blood();
        snake.print_scales();

        System.out.println();

        Amphibians frog = new Amphibians("Frog", 4);
        frog.food = "insects";
        frog.age = 11;
        frog.environment = "pond";

        frog.print_food();
        frog.print_lifespan();
        frog.print_living_environment();
        frog.print_blood_type();
        frog.print_legs();
    }
}

```
</details>






# Abtrantion