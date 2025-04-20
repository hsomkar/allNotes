- The values are written as **name : value** pairs (name and value separated by a colon). 
- Objects can be created in two ways:
    - Directly using var:
```
var person = {  
firstName : “John”,  
lastName : “Doe”,  
age : 50,  
eyeColor : “blue”,  
fullName : function() {  
return this.firstName + " " + this.lastName;  
}  
};
```

- Using new keyword : 

```
var person = new Object();  
person.firstName = "John";  
person.lastName = "Doe";  
person.age = 50;  
person.eyeColor = "blue";
```
#### The Object() Constructor : 
- A constructor is a function that creates and initializes an object. JavaScript provides a special constructor function called Object() to build the object. 
- Eg : 

```
<html>
  
<head>
   
<title>
User-defined objects
</title>
    
<script
 
type
=
"text/javascript"
>

      
// Define a function which will work as a method

      
function
 addPrice(amount) {

        
this
.price = amount;

      }

      
function
 book(title, author) {

        
this
.title = title;

        
this
.author = author;

        
this
.addPrice = addPrice; 
// Assign that method as property.

      }

    
</script>

  
</head>

  
<body>

    
<script
 
type
=
"text/javascript"
>

      
var
 myBook = 
new
 book(
"Perl"
, 
"Mohtashim"
);

      myBook.addPrice(
100
);

      document.write(
"Book title is : "
 + myBook.title + 
"<br>"
);

      document.write(
"Book author is : "
 + myBook.author + 
"<br>"
);

      document.write(
"Book price is : "
 + myBook.price + 
"<br>"
);

    
</script>

</body>

</html>

   <head>  
    <title>User-defined objects</title>  
    <script type="text/javascript">  
      // Define a function which will work as a method  
      function addPrice(amount) {  
        this.price = amount;  
      }  
      function book(title, author) {  
        this.title = title;  
        this.author = author;  
        this.addPrice = addPrice; // Assign that method as property.  
      }  
    </script>  
  </head>  
  <body>  
    <script type="text/javascript">  
      var myBook = new book("Perl", "Mohtashim");  
      myBook.addPrice(100);  
      document.write("Book title is : " + myBook.title + "<br>");  
      document.write("Book author is : " + myBook.author + "<br>");  
      document.write("Book price is : " + myBook.price + "<br>");  
    </script>  
  </body>  
</html>
```
- Output : 
	Book title is : Perl  
	Book author is : Mohtashim  
	Book price is : 100
 
## Date Object
 
- Creating Date Objects:
    - new Date()
        - Ex : var date = new Date();
    - new Date(year, month, day, hours, minutes, seconds, milliseconds)
        - Ex : var date = new Date(2018, 11, 24, 10, 33, 30, 0);
    - new Date(milliseconds)
        - Ex : var date = new Date(0); Zero time is January 01, 1970 00:00:00 UTC.
    - new Date(date string)
        - Ex : var date = new Date("October 13, 2014 11:13:00"); - Date Object Methods:

|Method|Description|
| --- | --- |
|getFullYear()|Get the year as a four digit number (yyyy)|
|getMonth()|Get the month as a number (0-11)|
|getDate()|Get the day as a number (1-31)|
|getHours()|Get the hour (0-23)|
|getMinutes()|Get the minute (0-59)|
|getSeconds()|Get the second (0-59)|
|getMilliseconds()|Get the millisecond (0-999)|
|getTime()|Get the time (milliseconds since January 1, 1970)|
|getDay()|Get the weekday as a number (0-6)|
|Date.now()|Get the time. ECMAScript 5.|

## Math Object
 
- **Math.PI** – returns pi value.
- **Math.round(x)** - returns the value of x rounded to its nearest integer.
- **Math.pow(x , y)** - returns the value of x to the power of y.
- **Math.sqrt(x)** - returns the square root of x.
- **Math.abs(x)** - returns the absolute (positive) value of x.
- **Math.ceil(x)** - returns the value of x rounded up to its nearest integer.
- **Math.floor(x)** - returns the value of x rounded down to its nearest integer.
- **Math.min()** and **Math.max()** - can be used to find the lowest or highest value in a list of arguments.
- **Math.random()** - returns a random number between 0 (inclusive), and 1 (exclusive).

