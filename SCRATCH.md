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
