- Events are "things" that happen to HTML elements. When JavaScript is used in HTML pages, JavaScript can "react" on these events. 
- Some most used events are: 

### onclick :
- This is the most frequently used event type which occurs when a user clicks the left button of his mouse. You can put your validation, warning etc., against this event type.
```
<input type="button" onclick="sayHello()" value="Say Hello"/>
```

### onsubmit : 
- onsubmit is an event that occurs when you try to submit a form. You can put your form validation against this event type.

```
<form method="POST" action="t.cgi" onsubmit="return validate()">
```
      
### onmouseover and onmouseout : 
    
- These two event types will help you create nice effects with images or even with text as well. The onmouseover event triggers when you bring your mouse over any element and the onmouseout triggers when you move your mouse out from that element.

```
<div onmouseover="over()" onmouseout="out()">
	<h2> This is inside the division </h2>  
</div>
```

