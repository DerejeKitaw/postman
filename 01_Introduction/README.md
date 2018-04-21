### Explore google map
> [Go to](https://developers.google.com/maps/documentation/geocoding/start)
> [Get google API key](https://developers.google.com/maps/documentation/geocoding/start#get-a-key)
![postman](./note/DOC/postman_1.png)
![postman](./note/DOC/postman_2.png)
![postman](./note/DOC/postman_3.png)

> The folowing request the latitude and longtude of "1600 Amphitheatre Parkway, Mountain View, CA"

https://maps.googleapis.com/maps/api/geocode/json?address=1600+Amphitheatre+Parkway,+Mountain+View,+CA&key=YOUR_API_KEY

![postman](./note/DOC/postman_4.png)
![postman](./note/DOC/postman_5.png)
> Now we can past API KEY for the key value, but the best pactice is to use variables

> Replace "YOUR_API_KEY" with {{googleMapsGeocodingApiKey}}
![postman](./note/DOC/postman_6.png)
![postman](./note/DOC/postman_7.png)

> Open enviroment manager
![postman](./note/DOC/postman_8.png)
![postman](./note/DOC/postman_9.png)
![postman](./note/DOC/postman_10.png)
![postman](./note/DOC/postman_11.png)
![postman](./note/DOC/postman_12.png)
> Make sure you have selected the new enviroment
![postman](./note/DOC/postman_13.png)
![postman](./note/DOC/postman_14.png)
![postman](./note/DOC/postman_15.png)
> Now let us hit send
![postman](./note/DOC/postman_16.png)
### How to autorize OAuth 1 using postman
> [We will use twiter api](https://developer.twitter.com/)
![postman](./note/DOC/postman_17.png)
![postman](./note/DOC/postman_18.png)
![postman](./note/DOC/postman_19.png)
![postman](./note/DOC/postman_20.png)

[GET user/show](https://developer.twitter.com/en/docs/accounts-and-users/follow-search-get-users/api-reference/get-users-show)

> To access api create OAuth token
![postman](./note/DOC/postman_21.png)
![postman](./note/DOC/postman_22.png)
![postman](./note/DOC/postman_23.png)
![postman](./note/DOC/postman_24.png)

> https://developer.twitter.com/en/docs/accounts-and-users/follow-search-get-users/api-reference/get-users-show

![postman](./note/DOC/postman_25.png)
### Save your first request in a collection
![postman](./note/DOC/postman_26.png)
![postman](./note/DOC/postman_27.png)
![postman](./note/DOC/postman_28.png)
![postman](./note/DOC/postman_29.png)
![postman](./note/DOC/postman_30.png)
![postman](./note/DOC/postman_31.png)
![postman](./note/DOC/postman_32.png)
![postman](./note/DOC/postman_33.png)
![postman](./note/DOC/postman_34.png)
![postman](./note/DOC/postman_35.png)
![postman](./note/DOC/postman_36.png)
![postman](./note/DOC/postman_37.png)
![postman](./note/DOC/postman_38.png)
![postman](./note/DOC/postman_39.png)

### Writing a test in postman
![postman](./note/DOC/postman_39.png)
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
![postman](./note/DOC/postman_40.png)
![postman](./note/DOC/postman_41.png)
![postman](./note/DOC/postman_42.png)

### More test on postman
```js
pm.test("Nmae of the test", function to be evaluated to true or false;)
});
```
```js
pm.test("Response includes results", function () {
    pm.expect(pm.response.json()).to.include.keys("results");
});
```
![postman](./note/DOC/postman_43.png)

### What if you want to run the test over and over in the entire collection?
![postman](./note/DOC/postman_44.png)
![postman](./note/DOC/postman_45.png)

### How do we save from googleapi the longtiude and latitude values to a variable so we can use it later.

> Test
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Response includes results", function () {
    pm.expect(pm.response.json()).to.include.keys("results");
});

let firstResponse = pm.response.json().results[0];
let lat = firstResponse.geometry.location.lat;
let lng = firstResponse.geometry.location.lng;

pm.enviroment.set('lat', lat);
pm.enviroment.set('lng', lng);
````
![postman](./note/DOC/postman_46.png)
![postman](./note/DOC/postman_47.png)
> Now check the enviromental variables
![postman](./note/DOC/postman_48.png)
![postman](./note/DOC/postman_49.png)
> Now we have saved the variable in the enviroment variable.
### How to use dynamicaly saved variable in another request.

### [Go to google places api](https://developers.google.com/places/web-service/search)

![postman](./note/DOC/postman_50.png)
![postman](./note/DOC/postman_51.png)
![postman](./note/DOC/postman_52.png)
![postman](./note/DOC/postman_53.png)
![postman](./note/DOC/postman_54.png)






