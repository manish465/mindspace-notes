`AuthenticationProvider` is an [[Interface]] in [[Spring Security]] that indicates a class can process a specific [[Authentication]] implementation. It is responsible for the logic of authentication.

The `AuthenticationManager` receives a request from the HTTP filter layer and delegates the responsibility to authenticate the user to the `AuthenticationProvider`. An `AuthenticationProvider` implementation takes care of verifying an authentication request. By default, Spring Security uses `ProviderManager` class which delegates to a list of configured `AuthenticationProvider(s)`, each of which is queried to see if it can perform the authentication.

#Example :

```Java
@Bean
    public AuthenticationProvider authenticationProvider(){
        DaoAuthenticationProvider authenticationProvider=new DaoAuthenticationProvider();
        authenticationProvider.setUserDetailsService(userDetailsService());
        authenticationProvider.setPasswordEncoder(passwordEncoder());
        return authenticationProvider;
    }
```

This code snippet is defining a Bean method that returns an instance of DaoAuthenticationProvider. The DaoAuthenticationProvider is an implementation of the AuthenticationProvider interface that uses a UserDetailsService and PasswordEncoder to authenticate a username and password. In this code, the DaoAuthenticationProvider is being configured with a UserDetailsService and a PasswordEncoder by calling the setUserDetailsService method and setPasswordEncoder method respectively. The configured DaoAuthenticationProvider instance is then returned by the method.


#SpringSecurity