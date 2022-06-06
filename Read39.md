# Read: 39 - Kinesis  

Using the Google Play services location APIs, your app can request the last known location of the user's device. In most cases, you are interested in the user's current location, which is usually equivalent to the last known location of the device.  

##### How to make a single request for the location of a device using the getLastLocation():  

- Set up Google Play services  
- Specify app permissions  
- Create location services client: 
In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows  

```
private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}
```  

- Get the last known location:  
To request the last known location, call the getLastLocation() method. The following code snippet illustrates the request and a simple handling of the response: 

```  
fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });
```  

- Choose the best location estimate  

Choose from one of the following, depending on your app's use case:  

1- getLastLocation() gets a location estimate more quickly and minimizes battery usage that can be attributed to your app. However, the location information might be out of date, if no other clients have actively used location recently.  

2- getCurrentLocation() gets a fresher, more accurate location more consistently. However, this method can cause active location computation to occur on the device.  


