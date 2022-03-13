# WRRC and Java  
we present a way of performing HTTP requests in Java — by using the built-in Java class HttpUrlConnection.  
#### HTTP Request
1- Creating a Request
We can create an HttpUrlConnection instance using the openConnection() method of the URL class  
The HttpUrlConnection class is used for all types of requests by setting the requestMethod attribute to one of the values: GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE.
Let's create a connection to a given URL using GET method  
```
URL url = new URL("http://example.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```  
2- Adding Request Parameters  
If we want to add parameters to a request, we have to set the doOutput property to true, then write a String of the form param1=value¶m2=value to the OutputStream of the HttpUrlConnection instance:  
```
Map<String, String> parameters = new HashMap<>();
parameters.put("param1", "val");

con.setDoOutput(true);
DataOutputStream out = new DataOutputStream(con.getOutputStream());
out.writeBytes(ParameterStringBuilder.getParamsString(parameters));
out.flush();
out.close();  
```  
3- Setting Request Headers  
Adding headers to a request can be achieved by using the setRequestProperty() method:  
```  
con.setRequestProperty("Content-Type", "application/json");  
```  
To read the value of a header from a connection, we can use the getHeaderField() method:  
```  
String contentType = con.getHeaderField("Content-Type");  
```  
4-   Configuring Timeouts  
HttpUrlConnection class allows setting the connect and read timeouts. These values define the interval of time to wait for the connection to the server to be established or data to be available for reading.

To set the timeout values, we can use the setConnectTimeout() and setReadTimeout() methods:  
```  
con.setConnectTimeout(5000);
con.setReadTimeout(5000);  
```  
6- Handling Cookies  
The java.net package contains classes that ease working with cookies such as CookieManager and HttpCookie.  
- First, to read the cookies from a response  
- Next, we will add the cookies to the cookie store  
- Finally, to add the cookies to the request  

7-  Reading the Response  
We can enable or disable automatically following redirects for a specific connection by using the setInstanceFollowRedirects() method with true or false parameter:
``
con.setInstanceFollowRedirects(false);  
```
It is also possible to enable or disable automatic redirect for all connections:
```
HttpUrlConnection.setFollowRedirects(false);  
```  




