In Spring Security, SecurityContextHolder is a class that provides access to the security-related information associated with the current user's authentication context.

It is a static holder for the [[SecurityContext]], which contains the user's authentication information.


```
SecurityContextHolder.getContext().getAuthentication()
```

Above expression used to retrieve the current Authentication object from the SecurityContext class

Authentication object represents the current user's security-related information after they have been authenticated.

```
SecurityContextHolder.getContext().getAuthentication() == null
```

The above expression is to checking if the user is authenticated or not. If it is null, then the user is not authenticated yet.

#SpringSecurity #Security 