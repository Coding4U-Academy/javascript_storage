# Local Storage:

Local Storage is a way to store data on the user's browser permanently, even if the browser is closed or the computer is turned off.
The data is stored in key-value pairs and can be accessed using JavaScript.
The maximum size of local storage varies from browser to browser, but it is typically around 5-10 MB.
Local Storage is not sent to the server with each HTTP request, which makes it faster than sending data back and forth from the server.
Data stored in Local Storage is not encrypted, so sensitive data should not be stored there.

To set a value in Local Storage, use the setItem() method and pass in the key and value as arguments: 
```
    localStorage.setItem('key', 'value');
```
To get a value from Local Storage, use the getItem() method and pass in the key:
```
const value = localStorage.getItem('key');
```
To remove a value from Local Storage, use the removeItem() method and pass in the key: 
```
    localStorage.removeItem('key');
```

# Session Storage:

Session Storage is similar to Local Storage, but the data is only stored for the duration of the user's session. Once the user closes the browser, the data is deleted.
Session Storage is also accessed using JavaScript and stored in key-value pairs.
The maximum size of Session Storage is similar to that of Local Storage.
Like Local Storage, Session Storage is not sent to the server with each HTTP request.

To set a value in Session Storage, use the setItem() method and pass in the key and value as arguments: 
```
    sessionStorage.setItem('key', 'value');
```
To get a value from Session Storage, use the getItem() method and pass in the key: 
```
    const value = sessionStorage.getItem('key');
```
To remove a value from Session Storage, use the removeItem() method and pass in the key:
``` 
    sessionStorage.removeItem('key');
```

# Cookie Storage:

Cookies are small text files that are stored on the user's computer by the website.
Cookies can be used to store information such as login details or user preferences.
Cookies have an expiration date and can be set to expire after a certain amount of time or when the user closes the browser.
Cookies are sent to the server with each HTTP request, which can slow down the website.
Cookies can be used to track user behavior, which can be a privacy concern.

To set a cookie, use the document.cookie property and set it to a string with the name, value, and optional attributes such as the expiration date and path: 
```
    document.cookie = 'name=value; expires=Thu, 21 March 2024 12:00:00 UTC; path=/';
```
To get a cookie, use the document.cookie property and split the string by semicolons to get an array of cookies. Then loop through the array and find the cookie with the name you want: 
```
let cookies = document.cookie.split(';'); 
for (var i = 0; i < cookies.length; i++) { 
    let cookie = cookies[i].trim(); 
    if (cookie.indexOf('name=') == 0) { 
        let value = cookie.substring('name='.length, cookie.length); 
    } 
}
```
To remove a cookie, set its expiration date to a date in the past: 
```
document.cookie = 'name=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/';
```