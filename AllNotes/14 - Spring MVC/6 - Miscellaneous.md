## Initbinder

## Initbinder

-   
    
- Initbinder comes into picture if you want to customize the request being sent to the controller. - It is defined in the controller, helps in controlling and formatting each and every request that comes to it. - To add a initbinder method we have to declare a method with @initbinder annotation ,this method should have WebDatabinder as parameter. 
## Cookies
 - cookie is a small piece of data that is done at the server-side and present in the browser-side - Cookies are mainly used for three purposes:
    
    - Session management
        
        - Logins, shopping carts, game scores, or anything else the server should remember
    - Personalization
        
        - User preferences, themes, and other settings
    - Tracking
        
        - Recording and analyzing user behavior
          
        
- Creating cookies
    
    - ```
        Cookie cookie=
        new
         Cookie(
        "key_name"
        ,
        "value"
        );
        
        response.addCookie(cookie);
        
        (@CookieValue(name=
        "key_name"
        , 
        required=
        false
        )String value)
        
        
        
        
        
        
        @
        InitBinder
        
        public void
         initBinder(WebDataBinder dataBinder) {
        
        CustomDateEditor dateEditor = 
        new
         CustomDateEditor(
        new
         SimpleDateFormat(
        "yyyy-MM-dd"
        ), 
        true
        );
        
        dataBinder.registerCustomEditor(Date.
        class
        , dateEditor);
        
        }
        
        
        
        
        
        
        
        
        @Controller
        
        @RequestMapping
        (path = 
        "cookies"
        )
        
        public class
         CookieController {
        
         
        
        @GetMapping
        (
        "/cookiepage"
        )
        
        public
         String getCookiePage() {
        
        return 
        "cookie"
        ;
        
        }
        
         
        
        @GetMapping
        (
        "/createCookie"
        )
        
        public
         String createCookie(ModelMap 
        map
        , HttpServletResponse 
        response
        ) {
        
        Cookie 
        cookie
         = 
        new
         Cookie(
        "technoelevate"
        , 
        "batch10"
        );
        
        cookie
        .setMaxAge(60);
        
        response
        .addCookie(
        cookie
        );
        
        map
        .addAttribute(
        "msg"
        , 
        "Cookies Created Successfully"
        );
        
        return 
        "cookie"
        ;
        
        }
        
         
        
        @GetMapping
        (
        "/showCookie"
        )
        
        public
         String getCookies(
        @CookieValue
        (name = 
        "technoelevate"
        , required = 
        false
        ) String 
        value
        , ModelMap 
        map
        ) {
        
        if
         (
        value
         != 
        null
        )
        
        map
        .addAttribute(
        "msg"
        , 
        "cookies found"
        );
        
        map
        .addAttribute(
        "cookieValue"
        , 
        value
        );
        
        return 
        "cookie"
        ;
        
        }
        
        }
        
        
        
        @
        GetMapping(
        "/validate/{name}"
        )
        
        public
         String getPathVariable(
        @
        PathVariable(
        "name"
        ) String name) {
        
        log.info(
        "path variable value is "
         + name);
        
        return 
        "index"
        ;
        
        }
        ```
        
        new Cookie("key_name","value");
      
    
- To send it to client-side:
    
    - response.addCookie(cookie);
      
    
- To access the cookie:
    
    - (@CookieValue(name="key_name", required=false)String value)
      
    
- To define the lifetime of a cookie:
    
    - cookie.setMaxAge(60); à cookie will be deleted after 60 sec
    - cookie.setMaxAge(0); à cookie will be deleted instantly
      
    
- Annotation which indicates that a method parameter should be bound to a URI template variable (i.e. Path parameter).
      

@InitBinder  
public void initBinder(WebDataBinder dataBinder) {  
CustomDateEditor dateEditor = new CustomDateEditor(new SimpleDateFormat("yyyy-MM-dd"), true);  
dataBinder.registerCustomEditor(Date.class, dateEditor);  
}
 
## Cookies
          
@Controller  
@RequestMapping(path = "cookies")  
public class CookieController {  
   
@GetMapping("/cookiepage")  
public String getCookiePage() {  
return "cookie";  
}  
   
@GetMapping("/createCookie")  
public String createCookie(ModelMap map, HttpServletResponse response) {  
Cookie cookie = new Cookie("technoelevate", "batch10");  
cookie.setMaxAge(60);  
response.addCookie(cookie);  
map.addAttribute("msg", "Cookies Created Successfully");  
return "cookie";  
}  
   
@GetMapping("/showCookie")  
public String getCookies(@CookieValue(name = "technoelevate", required = false) String value, ModelMap map) {  
if (value != null)  
map.addAttribute("msg", "cookies found");  
map.addAttribute("cookieValue", value);  
return "cookie";  
}  
}
 
## @PathVariable
   

@GetMapping("/validate/{name}")  
public String getPathVariable(@PathVariable("name") String name) {  
log.info("path variable value is " + name);  
return "index";  
}
