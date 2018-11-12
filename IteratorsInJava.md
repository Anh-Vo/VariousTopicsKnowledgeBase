# What the heck is an iterator?

According to Michael Goodrich, author of *Data Structures and Algorithms in Java*, "An Iterator is a software design pattern
that abstracts the process of scanning through a collection of elements one element at time." 

Simply put, an iterator is a just a software construct that gives the programmer the ability to access the individual elements 
of a collection in their linear order. That is, if you have an array list of dogs e.g. DogA, DogB, and DogC, then you can use 
an iterator to return each dog to you in the order that they are stored (DogA then DogB then DogC).

# So What?

So you might be wondering what's the big deal? Well, it's really not that complicated. An iterator simply gives you the power
to go through a list of things and do something to them. That's it. 

# How does it work? 

There are 2 interfaces for working with iterators in Java, the Iterable and Iterator interface. The Iterable interface has one
method: iterator(). This method simply returns an interator to the caller. The second interface, the Iterator interface has
2 methods that need to be implemented: hasNext() and next(). The first method, hasNext(), asks that the programmer implement
logic to determine whether or not there is another element to look at. The second method, next(), asks the programmer to
return the next element.

Let's dive into the code to see how things are layed out:

```java
/** Here we define a class that implements the iterable interface */
public class CustomIterable<T> implements Iterable<T> {
  private List<T> list = new ArrayList<>(); // This list holds the objects we want to iterate or loop over
  
  /** The iterator method calls the constructor of the inner class CustomIterator which implements the iterator interface.
    * This is how the two interfaces work together. Our outer class implements the Iterable interface which requires us to
    * implement the iterator interface that returns an iterator. We then create in inner class that implements the iterator
    * iterface, which will then give us back a custom iterator. By defining our own implementation, we can define how we want
    * the iterator to work. We can make it return one element after the next, or skip every other element, or skip 5 elements
    * at a time. That's the power of having the iterator interface.
    */
  @Override
  public Iterator iterator() {
    return new CustomIterator(list); // We pass our list to our custom iterator inner class to iterate over
  }
  
  /** Our customer class that implements the iterator interface */
  public class CustomIterator<E> implements iterator<E> {
    int index = 0; // We use this index to keep track our position as we iterate through the list
    List<E> listToIterateOver;
    
    /** Our constructor takes a list that we want to iterate over */
    public CustomerIterator(List<E> listToIterateOver) {
      this.listToIterateOver = listToIterateOver;
    }
    
    /** Check if there is another element in the list to iterate over */
    @Override
    public boolean hasNext() {
      if(listToIterateOver.size() >= index+1) { // Make sure our position is within the bounds of the list
        return true;
      }
      return false;
    }
    
    /** Return the next element if it exists */
    @Override
    public E next() {
      if(!hasNext()) {
        return null;
      }
      return listToIterateOver.get(index++);
    }
    
  } // End CustomIterator Class
  
}
```

# Summary:

Iterators give us as programmers the ability to loop over a collection of elements. In Java, we are given the **Iterable** and
**Iterator** interfaces to allow us the flexibility to define our own iterator that fits our needs. **Iterable** requires 1 
method: *iterator()*, which returns an iterator. Using the **Iterator** interface we can define our own custom interator by
implementing the *next()* and *hasNext()* methods. 

Together, we implement **Iterable** interface on our outer class and an inner class that implements the **Iterator** interface.
