- As soon as we add the dependency by default it gives login page to enter the application - Default username is 'user' - password is Auto-generated copy and paste it from console - So change the Username and password follow, - We give Username and password in properties file by, - (OR) Add a configuration class which extends WebSecurityConfigureAdapter which has
    
    - @Configuration -->
    - @EnableWebSecurity --> tell Spring security that this is web security configuration
      
    

```
@
Configuration

@
EnableWebSecurity

public
 
class
 SecurityConfiguration 
extends
 WebSecurityConfigurerAdapter {

    
@Override

    
protected
 
void
 configure(AuthenticationManagerBuilder 
auth
) 
throws
 Exception {

        
// Set your configuration on the auth object

        
auth
.inMemoryAuthentication()

                .withUser(
"blah"
)

                .password(
"blah"
)

                .roles(
"USER"
)

                .and()

                .withUser(
"foo"
)

                .password(
"foo"
)

                .roles(
"ADMIN"
);

    }

 

    
@
Bean

    
public
 PasswordEncoder getPasswordEncoder() {

        
return
 NoOpPasswordEncoder.getInstance();

    }

 

    
@Override

    
protected
 
void
 configure(HttpSecurity 
http
) 
throws
 Exception {

        
http
.authorizeRequests()

                .antMatchers(
"/admin"
).hasRole(
"ADMIN"
)

                .antMatchers(
"/user"
).hasAnyRole(
"ADMIN"
, 
"USER"
)

                .antMatchers(
"/"
).permitAll()

                .and().formLogin();

    }

}

    
@Override

    
protected
 
void
 configure(HttpSecurity 
http
) 
throws
 Exception {

        
http
.authorizeRequests()

            .antMatchers(
"/admin"
).hasRole(
"ADMIN"
)//-->only accessed by admin

            .antMatchers(
"/user"
).hasAnyRole(
"ADMIN"
, 
"USER"
)//-->accessed by all roles

            .antMatchers(
"/"
).permitAll()//-->accessed by all

            .and().formLogin();

    }










```

Configuration  
@EnableWebSecurity  
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {  
@Override  
protected void configure(AuthenticationManagerBuilder auth) throws Exception {  
// Set your configuration on the auth object  
auth.inMemoryAuthentication()  
.withUser("blah")  
.password("blah")  
.roles("USER")  
.and()  
.withUser("foo")  
.password("foo")  
.roles("ADMIN");  
}  
   
@Bean  
public PasswordEncoder getPasswordEncoder() {  
return NoOpPasswordEncoder.getInstance();  
}  
   
@Override  
protected void configure(HttpSecurity http) throws Exception {  
http.authorizeRequests()  
.antMatchers("/admin").hasRole("ADMIN")  
.antMatchers("/user").hasAnyRole("ADMIN", "USER")  
.antMatchers("/").permitAll()  
.and().formLogin();  
}  
}

- To set a password encoder, --> Just expose an @Bean of type PasswordEncoder! - To provide authorization --> Override configure(HttpSecurity http)

@Override  
protected void configure(HttpSecurity http) throws Exception {  
http.authorizeRequests()  
.antMatchers("/admin").hasRole("ADMIN")//-->only accessed by admin  
.antMatchers("/user").hasAnyRole("ADMIN", "USER")//-->accessed by all roles  
.antMatchers("/").permitAll()//-->accessed by all  
.and().formLogin();  
}
       

spring.security.user.name=username  
spring.security.user.password=password
