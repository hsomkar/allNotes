## Forward:
 
```
return “forward:/abc/xyz";

return “redirect:https://www.google.com";
```

- The request will be further processed on the server side
- The client isn't impacted by forward, URL in a browser stays the same
- Request and response objects will remain the same object after forwarding. Request-scope objects will be still available  
## Redirect:
 
- return “redirect:https://www.google.com";
- The request is redirected to a different resource
- The client will see the URL change after the redirect
- A new request is created
