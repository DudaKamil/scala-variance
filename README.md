* #### [Invariant](src/main/scala/Invariance.scala)
    * Usage: `class Foo[A]`
    * Definition: `Stack[A]` is a subtype of `Stack[B]` if and only if `A = B`
    * Example: `Cat` is a subtype of `Animal`; however, `Container[Cat]` is not a `Container[Animal]`, nor is the reverse true.
 
* #### [Covariant](src/main/scala/Covariance.scala)
    * Usage: `class Bar[+A]`
    * Definition: If `A` is a subtype of `B` then `List[A]` is a subtype of `List[B]` 
    * Example: \
      `Cat` is a subtype of `Animal` as well as `Dog` is a subtype of `Animal`.\
      `List[Cat]` is a `List[Animal]` and a `List[Dog]` is also a `List[Animal]`.\
      Therefore, both `List[Cat]` and `List[Dog]` can be substituted for (used instead of) `List[Animal]`.\
    It is possible to write `val x: List[Animal] = List(Dog("Tom"))` and `ListPrinter[Animal]` can print every subtype of `List[Animal]`
    
* #### [Contravariant](src/main/scala/Contravariance.scala)
    * Usage `class Baz[-A]`
    * Definition: \
      Opposite to covariance.\
      If `A` is a subtype of `B` then `Writer[B]` is a subtype of `Writer[A]` 
    * `Cat` is a subtype of `Animal`\
      `Printer[Animal]` is a subclass of `Printer[Cat]`; therefore, it can be used as a substitute of a `Printer[Cat]`, not inverse!
      `val x: Printer[Cat] = Printer[Animal]`
