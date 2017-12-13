###Polymorphism & Composition Homework - Quiz

##Polymorphism

#What does the word 'polymorphism' mean?
Its greek :P
Poly = many  + Morph = form ... (Morpheus = the Greek god of dreams able to take any form etc.)

#What does it mean when we apply polymorphism to OO design? Give a simple Java example.
Polymorphism describes a pattern in object oriented programming in which classes have different functionality while sharing a common interface.

It allows flexibility in the way we develop our code, and scalability.
An example in java:

public class Animal{
   ...
   public void sound(){
      System.out.println("Animal is making a sound");   
   }
}

public class Cat extends Animal{
...
    @Override
    public void sound(){
        System.out.println("Meow");
    }
}




#What can we use to implement polymorphism in Java?
In Java you can have polymorphism both through inheritance and/or through implementing the same interface (abstract classes and super classes).

Polymorphism is the capability of a method to do different things based on the object that it is acting upon. In other words, polymorphism allows you define one interface and have multiple implementations.

Types of polymorphism ( methods overloading & overriding) :
1. Method Overloading in Java – compile time (or static polymorphism)
2. Method Overriding in Java –  runtime time (or dynamic polymorphism)


#How many 'forms' can an object take when using polymorphism?
a lot- unlimited.

#Give an example of when you could use polymorphism.
If I want to create classes that share common characteristics but are also independent and different from each other...Any example could fit.




##Composition

#What do we mean by 'composition' in reference to object-oriented programming?
The idea of composition is that Objects can contain other objects.
We use composition to implement polymorphism in programming.

(Composition over inheritance (or composite reuse principle) in object-oriented programming (OOP) is the principle that classes should achieve polymorphic behaviour and code reuse by their composition (by containing instances of other classes that implement the desired functionality) rather than inheritance from a base or parent class.)


#When would you use composition? Provide a simple example in Java.
The example with input/output devices using different interfaces yesterday was a good one.
It was using both Interfaces and Arraylists to achieve polymorphism - composition is the overall design/architecture of the system that enabled it to be polymorphic.

Here is our loop in order to select one output (Class) from outputDevices Arraylist inside the computer Class:

public IOutput getOutputDevice(IOutput output) {
      IOutput finaloutput = null;
      for (IOutput outputvar : outputDevices){
          if (outputvar == output) {
              finaloutput = outputvar;
          }
      }
      return finaloutput;
  }

#What is/are the advantage(s) of using composition?
We prefer it than inheritance, it creates less problems when scaling up programs in the long run and flexibility.
Initial design is simplified by identifying system object behaviours in separate interfaces instead of creating a hierarchical relationship to distribute behaviours among classes via inheritance. This approach more easily accommodates future requirements changes that would otherwise require a complete restructuring of classes in the inheritance model. Additionally, it avoids problems often associated with relatively minor changes to an inheritance-based model that includes several generations of classes.

#What happens to the behaviours when the object composed of them is destroyed?
nothing. The system is resilient - the object can be destroyed but the behaviours remain.
