# Scratches - code snippets

## PHP Promises

https://docs.php-http.org/en/latest/components/promise.html

## JS promises

```
const delay = (t: number) => new Promise(resolve => setTimeout(resolve, t));

delay(500)
    .then(() => console.log(0))
    .then(() => {
      return delay(500)
          .then(() => {
                console.log(1)
              }
          )
    }).then(() => {
      console.log(2)
    })
```

## JS async

    const fetchAuthenticatedUser = async () => {
      const authenticatedUserResponse = await authenticationService.authenticatedUser()
    
      if (store.getters["AuthenticationModule/securelyAuthenticated"]) {
        console.log("User is securely authenticated")
      } else if (store.getters["AuthenticationModule/authenticated"]) {
        console.log("User is authenticated")
      } else {
        console.log("User is not authenticated")
      }
    
      console.log(authenticatedUserResponse)
    }
    
VS

    fetchAuthenticatedUser()
    
    authenticationService.authenticatedUser().then((authenticatedUserResponse) => {
      if (store.getters["AuthenticationModule/securelyAuthenticated"]) {
        console.log("User is securely authenticated")
      } else if (store.getters["AuthenticationModule/authenticated"]) {
        console.log("User is authenticated")
      } else {
        console.log("User is not authenticated")
      }
    
      console.log(authenticatedUserResponse)
    })
