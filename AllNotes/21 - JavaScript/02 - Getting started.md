- JavaScript is case sensitive language. 
- Use script tag to include js in html
```
<script src = “index.js”></script>
```
- document.write():
    - Can be used to write anything on document

#### These are some methods belongs to window object as it is global object its methods can be used directly

- window.alert():
    - The alert method displays a visual alert box on screen and the method parameter is displayed to the user in plain text.

- window.prompt():
    - An easy way to get an input from a user is by using the prompt() method.

- window.confirm():
    - confirm() method displays a modal dialog with an optional message and two buttons, OK and Cancel, which returns boolean result.

### Console API 
- Some methods of console object: 
- console.log() - console.log() can be used to log variables of any kind to be displayed in the console.
- console.time():
    - console.time() can be used to measure how long a task in your code takes to run.
    - Calling console.time([label]) starts a new timer. When console.timeEnd([label]) is called, the elapsed time, in milliseconds, since the original .time() call is calculated and logged.
    - Eg.:
    ```
    console.time(
    'response in'
    );
    
    alert(
    'Click to continue'
    );
    
    console.timeEnd(
    'response in'
    );
    
    alert(
    'One more time'
    );
    
    console.timeEnd(
    'response in'
    );
    ```
    - Output:
	    response in: 774.967ms  
		response in: 1402.199ms

- console.info() – small informative icon (ⓘ) appears on the left side of the printed string(s) or object(s).
- console.warn() – small warning icon (!) appears on the left side. In some browsers, the background of the log is yellow.
- console.error() – small times icon (⊗) appears on the left side. In some browsers, the background of the log is red.
- console.trace() – outputs the current stack trace or displays the same output as the log method if invoked in the global scope.
- console.table() - can be used to display objects and arrays in a tabular format.
- console.count() - to count no. Of times function is invoked.
- console.clear() - You can clear the console window using this method.
- console.assert() - Writes an error message to the console if the assertion is false. Otherwise, if the assertion is true, this does nothing.  

