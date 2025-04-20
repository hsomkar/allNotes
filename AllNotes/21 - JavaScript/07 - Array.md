- The Array object lets you store multiple values in a single variable. It stores a fixed-size sequential collection of elements of the same type.
- **Syntax**:
    - var fruits = new Array( "apple", "orange", "mango" );
    - var fruits = [ "apple", "orange", "mango" ];
- **Array Properties :** 

| Property    | Description                                                                    |
| ----------- | ------------------------------------------------------------------------------ |
| constructor | Returns a reference to the array function that created the object.             |
| index       | The property represents the zero-based index of the match in the string        |
| input       | This property is only present in arrays created by regular expression matches. |
| length      | Reflects the number of elements in an array.                                   |
| prototype   | The prototype property allows you to add properties and methods to an object.  |

- **Array Methods :**

| Method        | Description                                                                                                             |
| ------------- | ----------------------------------------------------------------------------------------------------------------------- |
| concat()      | Returns a new array comprised of this array joined with other array(s) and/or value(s).                                 |
| every()       | Returns true if every element in this array satisfies the provided testing function.                                    |
| filter()      | Creates a new array with all of the elements of this array for which the provided filtering function returns true.      |
| forEach()     | Calls a function for each element in the array.                                                                         |
| indexOf()     | Returns the first (least) index of an element within the array equal to the specified value, or -1 if none is found.    |
| join()        | Joins all elements of an array into a string.                                                                           |
| lastIndexOf() | Returns the last (greatest) index of an element within the array equal to the specified value, or -1 if none is found.  |
| map()         | Creates a new array with the results of calling a provided function on every element in this array.                     |
| pop()         | Removes the last element from an array and returns that element.                                                        |
| push()        | Adds one or more elements to the end of an array and returns the new length of the array.                               |
| reduce()      | Adds one or more elements to the end of an array and returns the new length of the array.                               |
| reduceRight() | Apply a function simultaneously against two values of the array (from right-to-left) as to reduce it to a single value. |
| reverse()     | Reverses the order of the elements of an array --the first becomes the last, and the last becomes the first.            |
| shift()       | Removes the first element from an array and returns that element.                                                       |
| slice()       | Extracts a section of an array and returns a new array.                                                                 |
| some()        | Returns true if at least one element in this array satisfies the provided testing function.                             |
| toSource()    | Represents the source code of an object                                                                                 |
| sort()        | Sorts the elements of an array.                                                                                         |
| splice()      | Adds and/or removes elements from an array.                                                                             |
| toString()    | Returns a string representing the array and its elements.                                                               |
| unshift()     | Adds one or more elements to the front of an array and returns the new length of the array.                             |
