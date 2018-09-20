# Methods and Encapsulation

## Designing Methods

```Java
public static void full_name throws InterruptedException] (fname, lname) {
	System.out.println(fname + " " + lname);
}
```

The method above is a *method declaration* which specifies all of the information needed to call a particular method.  In this case our method is called full_name().

| Element  	| Value in full_name() example 	| Required?
|----------	| -----------------------------	| ----------|
| Access Modifieer 	| public | **No**	| 
| Optional Specifier 	| static | **No**	|
| Return Type 		| void 	 | **Yes**	|
| Name of Methods 	| full_name | **Yes** |
| List of Parameters| () | **Yes, Can be empty. ** |
| Optional Exception | throws InterruptedException | **No** 
| Body of Method | { } | **Yes, Can be empty. ** |


## 4 Access Modifiers
* **public** - Method can be called from different classees.
* **private** - Method can only be called only from within the same class.
* **protected** - Method can only be called from classes in the same package or subclasses.
* **Default** - Method can only be called from classes in the same package.

## Optional Specifiers
*static - used for class methods
*abstract - used when not providing a method body
*final (On OCP, not on OCA)
*synchronized (On OCP, not on OCA)
*native - used when using other languages
*strictfp - used for making floating-point calculations


## Return Type
A return type is required.  If the intent is to not return a value, then the type is void. 

public void hello_world() 


## Method Name
A method name is required.  A method name can contain letters, numbers, $, or _.  The first character cannot be a number.

public void hello_world()

## Parameter List
The ( ) parameter list is required but can be empty.

## Optional Exception List
The exception list is optional and appears in between the parametre list and method body.

## Method Body
The method body is required and can be left empty. 

## Varargs
Varargs must appear last in the parameter list and only have one varargs.  Varargs use is like an array, except when used other than the last var in the parameter list, a compile error will occur.  Java will create an array if provided a list in the parameter list.

public void hello_world(int... start) { }
public void hello_world(int... start, int end) { } // DOES NOT COMPILE

## Applying Access Modifiers
From the most restrictive to least: private, default, protected, public

* *private* - only code in the same class can access methods or fields.
* default - only code in the same package can access methods or fields.
* protected - allows code to access members of the parent class as well as default access.
*.* public - allows code to access protected and classes in other packages.

## Static Methods and Fields
The static methods and fields allows access to the the method or field without an instance of the class.

```Java
File: Car.java
public class Car {
	public static int wheels = 4;

	public static void main(String[] args) {
		System.out.println(wheels);
	}
}

File: Cycle.java
public class Cycle {
	public static int wheels = 2;

	public static void main(String[] args) {
		System.out.println("Cars have " + Car.wheels + " while, ");
		System.out.println("Motorcycles have " + wheels + " wheels.");
	}
}
```

## Static vs Instance
```Java
//File: Car.java
public class Car {
        public static int wheels = 4;
        public static int doors = 4;
        public int steeringwheel = 0;

        public static void main(String[] args) {
                System.out.println(Car.wheels);
                System.out.println(Car.doors);
                System.out.println(Car.steeringwheel); // Compile Error
        }
}
```



