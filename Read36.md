# Cognito  

#### Getting started  

The Amplify Auth category provides an interface for authenticating a user.  
To setup and configure your application with Amplify Auth you should do the following:  

1- execute the command: amplify add auth  
2- Enter the following when prompted: 

```  
? Do you want to use the default authentication and security configuration?
    `Default configuration`
? How do you want users to be able to sign in?
    `Username`
? Do you want to configure advanced settings?
    `No, I am done.`  
```  

3- To push your changes to the cloud, execute the command:  

```  
amplify push 
```  

4- To install Amplify Libraries: 
Add the following dependency to your app's build.gradle  

```  
dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.35.4'
}  
```  

5- Initialize Amplify Auth : Add the Auth plugin before calling 'Amplify.configure'  

```
// Add this line, to include the Auth plugin.
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());
```  

6- To check the current auth session  

``` 
Amplify.Auth.fetchAuthSession(
    result -> Log.i("AmplifyQuickstart", result.toString()),
    error -> Log.e("AmplifyQuickstart", error.toString())
);
```  

# Sign in  

- The Auth category can be used to register a user, confirm attributes like email/phone, and sign in with optional multi-factor authentication.  

1- Invoke the following api to initiate a sign up flow  

``` 
AuthSignUpOptions options = AuthSignUpOptions.builder()
    .userAttribute(AuthUserAttributeKey.email(), "my@email.com")
    .build();
Amplify.Auth.signUp("username", "Password123", options,
    result -> Log.i("AuthQuickStart", "Result: " + result.toString()),
    error -> Log.e("AuthQuickStart", "Sign up failed", error)
);
``` 

2- confirm the user  

``` 
Amplify.Auth.confirmSignUp(
    "username",
    "the code you received via email",
    result -> Log.i("AuthQuickstart", result.isSignUpComplete() ? "Confirm signUp succeeded" : "Confirm sign up not complete"),
    error -> Log.e("AuthQuickstart", error.toString())
);
``` 

3- Implement a UI to get the username and password from the user then call the following method:  

```
Amplify.Auth.signIn(
    "username",
    "password",
    result -> Log.i("AuthQuickstart", result.isSignInComplete() ? "Sign in succeeded" : "Sign in not complete"),
    error -> Log.e("AuthQuickstart", error.toString())
);
``` 












    


