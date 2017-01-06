# Generics

#### What are generics?

#### Why use generics?
* Runtime bugs are hard to debug. Compile time bugs are easier to catch with clear error messages
* Generics add stability to your code by making bugs more detectable. Hence we are able to reduce runtime bugs to compile-time bugs
* Benefits of generics:
  * Stronger type checks at compile time
  * We can eliminate casting
  * We can implement generic algorithms (e.g. sorting) and we can reuse them. For instance, rather than having to implement separate sort methods for sorting strings, doubles, integers, we can use implement one sort method that takes a generic parameter.
  * Reduce duplication. For example:
    ```
    // instead of doing this:
    public void draw(Car car);
    public void draw(Bus bus);

    // we can do this:
    public void draw(T t);  // generic types!
    ```
