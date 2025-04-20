- Web storage objects **localStorage** and **sessionStorage** allow to save key/value pairs in the browser. 
- Storage limits in browsers is 5mb-10mb 
- **localStorage** object stores data with no expiration date. The data will not be deleted when the browser is closed. 
- **sessionStorage** object stores data for one session (data is lost when the browser tab is closed). 
- Syntax:

```
<script type="text/javascript">  
      localStorage.setItem("name", "John Smith");  
      console.log(localStorage.getItem("name")); // "John Smith"
 
      localStorage.removeItem("name");  
      console.log(localStorage.getItem("name")); // null  
    </script>
```
 - If you want to store simple structured data, you can use JSON to serialize it to and from strings for storage. 
```
    <script type="text/javascript">  
      var players = [  
        { name: "Tyler", score: 22 },  
        { name: "Ryan", score: 41 },  
      ];  
      localStorage.setItem("players", JSON.stringify(players));  
      console.log(JSON.parse(localStorage.getItem("players")));  
      // [ Object { name: "Tyler", score: 22 }, Object { name: "Ryan", score: 41 } ]  
    </script>
```
 - Simpler way of handling Storage: 
```
    <script type="text/javascript">  
      // Set  
      localStorage.greet = "Hi!"; // Same as: window.localStorage.setItem("greet", "Hi!");  
      // Get  
      localStorage.greet; // Same as: window.localStorage.getItem("greet");  
      // Remove item  
      delete localStorage.greet; // Same as: window.localStorage.removeItem("greet");  
      // Clear storage  
      localStorage.clear();  
    </script>
```
 - **localStorage.length** property returns an integer number indicating the number of elements in the localStorage 
 - To clear the storage, simply run **localStorage.clear()**
 - To remove a specific item from the browser Storage (the opposite of setItem) use removeItem
	- `localStorage.removeItem("greet");`

