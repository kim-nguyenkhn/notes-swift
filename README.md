# notes-swift

My personal notes on the Swift programming language.

## Questions:

* What is ARC and how does it work?

  * Automatic Reference Counting (ARC) manages your app's memory usage.
  * ARC allocates memory when class instances are created, and frees up memory when they are no longer needed.
  * ARC will not deallocate an instance as long as at least one active reference to a class instance still exists.

  * Source: [Swift Docs - Automatic Reference Counting](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html)

* How is ARC different from Java's garbage collector?

  * Garbage collected memory management is deterministic.
  * In other words, the programmer can know exactly when the garbage collector will run.

  * Source: [Swift Docs - Search Bar Autocomplete](https://developer.apple.com/search/?q=garbage%20collected%20memory%20management%20is%20deterministic.%20in%20other%20words,%20the%20programmer%20can%20know%20exactly%20when%20the%20garbage%20collector%20will%20run.)

* What is a property?

  * Properties are basically "vars" in JavaScript.
  * Properties may either be stored (constant/variable values as part of an instance) or computed (value is determined/calculated, rather than stored).
  * Properties are usually associated with instances of a particular type.

  * Type properties are useful for defining values that are universal to ALL instances of a particular type.

  * Properties may have observers (willSet, didSet), which respond to changes in a property's value.

  * Source: [Swift Docs - Properties](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Properties.html)

* When should a property be strong vs weak?

  ### Strong References
  * Property declarations are strong by default.
  * Strong references protect the referred object from getting de-allocated by ARC by increasing its retain count by 1.
  * As long as ANYTHING has a strong reference to an object, it will not be deallocated.
  * Strong references are used when the hierarchy of references flow from parent to child.

  ### Weak references
  * Weak references DO NOT protect the object from being de-allocated by ARC.
  * Weak references zero out the pointer to your object when it successfully de-allocates. This ensures that when you access a weak reference, it will either be a valid object, or nil.
  * All weak references are non-constant Optionals (vars).
  * Weak references should be used in cases where you have potential retain cycles - something that happens when two objects both have strong references to each other. Using a weak reference will allow the objects to de-allocate when they are no longer used.

  * Source: [Krakendev.io Blog - Weak and Unowned References in Swift](https://krakendev.io/blog/weak-and-unowned-references-in-swift)

* Why do strong reference cycles cause a memory leak in Swift (and Objective-C), but not in Java?

  * Memory leaks are inaccessible memory that has no more pointers to it.
  * In Java,

  * Source: [Basem Emara Blog - Memory Leaks & Resource Management in Swift and iOS](http://basememara.com/memory-leaks-resource-management-swift-ios/)

* What does it mean to "capture self" in a closure and why can it lead to a memory leak?
* What is the syntax for a property that can store a closure?
* What does inferred typing mean in Swift?
* What is an implicitly unwrapped optional?
* When would you use ? vs ! to unwrap an optional?
* When casting, when would you use as? vs as!
* What is another syntax for unwrapping an optional?
* What is optional chaining?
* What is Any vs AnyObject vs NSObject?
* What is the syntax for a property getter/setter?
* What is a property observer?
* What is a failable initializer?
* What is a required vs convenience initializer?
* What are the rules for initializers with respect to inheritance?
* What is an extension?
* What is guard & defer?
* When would you use a struct vs class?
* What scopes exist in Swift?
