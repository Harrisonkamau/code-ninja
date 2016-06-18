---
layout: post
title: Object Oriented Programming(OOP)
---

<h2>Definition</h2>
<p>Object-oriented programming (OOP) is a software programming model constructed around objects. This model compartmentalizes data into objects (data fields) and describes object contents and behavior through the declaration of classes (methods).</p>

<p><h2>Features of Object Oriented Programming</h2>
		<ul>
			<li><strong>Inheritance</strong>: This refers to the hierarchical arrangement of implementation fragments. Through inheritance,less code is written, and multiple objects could 'inherit' the features of a class. E.g. A car class can have common features such as number of tyres, engine and door which are visible in different types of cars. A class could be seen as a template that describes the details of an object. </li>
			<li><strong>Polymorphism</strong>: This means abstract entities are implemented in multiple ways.</li>
			<li><strong>Encapsulation</strong>: This makes the program structure easier to manage because each object’s implementation and state are hidden behind well-defined boundaries. </li>
		</ul>
	</p>
<p>Object-oriented programming allows for simplified programming. Its benefits include re-usability, refactoring, extensibility, maintenance and efficiency.</p>

<h1>Principles of OOP</h1>
<p>In order for a programming language to be object-oriented, it has to enable working with classes and objects as well as the implementation and use of the fundamental object-oriented principles and concepts: inheritance, abstraction, encapsulation and polymorphism.</p>
<h2>Inheritance</h2>
<p>Inheritance is a fundamental principle of object-oriented programming. It allows a class to "inherit" (behavior or characteristics) of another, more general class. </p>
<p>For example, a lion belongs to the biological family of cats (Felidae). All cats that have four paws, are predators and hunt their prey. This functionality can be coded once in the <strong>Felidae</strong> class and all its predators can reuse it – <strong>Tiger, Puma, Bobcat</strong>, etc. Inheritance is described as <strong>is-kind-of relationship</strong>, e.g. <strong>Tiger</strong> is kind of Animal.</p>
<p>The class from which we inherit is referred to as parent class or base class / super class.</p>
<p>This is how the inheriting class, Lion, looks like:</p>

~~~.NET
public class Lion : Felidae
{
	private int weight;
	public Lion(bool male, int weight) : base(male)
	{
		this.weight = weight;
	}
	public int Weight
	{
		get{return weight;}
		set{this.weight = value;}
	}
}
~~~
<h2>Abstraction</h2>
<p>The next core principle of object-oriented programming we are about to examine is "abstraction". Abstraction means working with something we know how to use without knowing how it works internally. A good example is a television set. We don’t need to know the inner workings of a TV, in order to use it. All we need is a remote control with a small set of buttons (the interface of the remote) and we will be able to watch TV.</p>
<p>Abstraction is one of the most important concepts in programming and OOP. It allows us to write code, which works with abstract data structures (like dictionaries, lists, arrays and others). We can work with an abstract data type by using its interface without concerning ourselves with its implementation. For instance, we can save to a file all elements from a list without bothering if it is implemented with an array, a linked list, etc. The code remains unchanged, when we work with other data types. We can even write new data types (we will discuss this later) and make them work with our program without changing it.</p>
<h2>Encapsulation</h2>
<p>Encapsulation is one of the main concepts in OOP. It is also called "information hiding". An object has to provide its users only with the essential information for manipulation, without the internal details. A Secretary using a Laptop only knows about its screen, keyboard and mouse. Everything else is hidden internally under the cover. She does not know about the inner workings of Laptop, because she doesn’t need to, and if she does, she might make a mess. Therefore parts of the properties and methods remain hidden to her.</p>
<p>
The person writing the class has to decide what should be hidden and what not. When we program, we must define as private every method or field which other classes should not be able to access.</p>
<p>An example of Encapsulation would be:</p>

~~~.NET
public class Lion : Felidae, Reproducible<Lion>
{
    private Paw frontLeft;
    private Paw frontRight;
    private Paw bottomLeft;
    private Paw bottomRight;

    private void MovePaw(Paw paw) {
        // …
    }
    public override void Walk()
    {
        this.MovePaw(frontLeft);
        this.MovePaw(frontRight);
        this.MovePaw(bottomLeft);
        this.MovePaw(bottomRight);

    }
}
~~~
<p>In the above example, Lion doesn’t publicly disclose information about its inner workings (it encapsulates certain behavior)</p>
<h2>Polymorphism</h2>
<p>Polymorphism means one name, many forms.  Polymorphism
manifests itself by having multiple methods all with the same name, but slightly different functionality.</p
<p>There are 2 basic types of polymorphism. Overriding, also called run-time polymorphism, and overloading, which is referred to as compile-time polymorphism.  This difference is, for method overloading, the compiler determines which method will be executed, and this decision is made when the code gets compiled.
Which method will be used for method overriding is determined at runtime based on the dynamic type of an object.</p>
