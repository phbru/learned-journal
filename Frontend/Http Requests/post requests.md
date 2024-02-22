## Request example

```typescript
const requestOptions = {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(requestBody), // Has JSON format object
};

fetch("unsubscribe", requestOptions)
  .then((response) => response.text())
  .then((data) => {
    //... Do something with data

    return;
  })
  .catch((error) => console.error("Error:", error));
```
