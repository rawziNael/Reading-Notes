# WRRC and Java  
we present a way of performing HTTP requests in Java — by using the built-in Java class HttpUrlConnection.  
#### Creating a Request
We can create an HttpUrlConnection instance using the openConnection() method of the URL class  
The HttpUrlConnection class is used for all types of requests by setting the requestMethod attribute to one of the values: GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE.
Let's create a connection to a given URL using GET method  
```
URL url = new URL("http://example.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```
