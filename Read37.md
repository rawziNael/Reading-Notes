# Read: 37 - S3  

What is Amazon S3?  
Amazon S3 is Amazon Simple Storage Service which is an object storage service that offers industry-leading scalability, data availability, security, and performance.  

#### Features of Amazon S3  

- Storage classes  
- Storage management  
- Access management  
- Data processing  
- Storage logging and monitoring  
- Automated monitoring tools  
- Manual monitoring tools  
- Analytics and insights  
- Strong consistency  

#### How Amazon S3 works  

Amazon S3 is an object storage service that stores data as objects within buckets. An object is a file and any metadata that describes the file. A bucket is a container
for objects.  

To store your data in Amazon S3, you first create a bucket and specify a bucket name and AWS Region. Then, you upload your data to that bucket as objects in Amazon S3.
Each object has a key (or key name), which is the unique identifier for the object within the bucket.  

S3 provides features that you can configure to support your specific use case.  
 
#### Amazon S3 data consistency model  

Using Amazon S3 you will be able to read-after-write consistency for PUT, DELETE and GET requests of objects in your Amazon S3 bucket in all AWS Regions.  
Updates to a single key are atomic. For example, if you make a PUT request to an existing key from one thread and perform a GET request on the same key from a second
thread concurrently, you will get either the old data or the new data, but never partial or corrupt data.  

#### Related services  

After you load your data into Amazon S3, you can use it with other AWS services. The following are the services that you might use most frequently:  

- Amazon Elastic Compute Cloud (Amazon EC2)  
- Amazon EMR  
- AWS Snow Family  
- AWS Transfer Family  

# Amplify Storage 

#### Setup & Configure  

- To start provisioning storage resources in the backend  

```
amplify add storage
```  
- To push your changes to the cloud

```
amplify push
```  

- To install Amplify Libraries  

```
dependencies {
    implementation 'com.amplifyframework:aws-storage-s3:1.35.4'
    implementation 'com.amplifyframework:aws-auth-cognito:1.35.4'
}
```  

- To initialize Amplify Storage  

```
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSS3StoragePlugin());
```  

- To Upload data to your bucket  

```
private void uploadFile() {
    File exampleFile = new File(getApplicationContext().getFilesDir(), "ExampleKey");

    try {
        BufferedWriter writer = new BufferedWriter(new FileWriter(exampleFile));
        writer.append("Example file contents");
        writer.close();
    } catch (Exception exception) {
        Log.e("MyAmplifyApp", "Upload failed", exception);
    }

    Amplify.Storage.uploadFile(
            "ExampleKey",
            exampleFile,
            result -> Log.i("MyAmplifyApp", "Successfully uploaded: " + result.getKey()),
            storageFailure -> Log.e("MyAmplifyApp", "Upload failed", storageFailure)
    );
}
```












