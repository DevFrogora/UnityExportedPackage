After importing LoginScreen pakcage aka AuthenticationScreen package ( note:- this package is depends on Unity service authentication) , you need to do some steps to use this unity service :- <br> 
1) Install Authentication from package manager 
2) link the project with Unity dashboard.
Project setting -> services -> select the organisation -> create project id -> save
3) Go to unity dashboard -> explore services -> authentication -> setup -> setup authentication 
<br>
(Now we are done & don't forget to call UnityServer.initialization())

 This package is imported from  [this project](https://github.com/DevFrogora/UnityAuthentication)

 Summary about the files :- <br>
- Graphics :- images /texture 
- UI :- LoginScreenVisualTree is the main UI
- Initialization :- Uinity Initilization
- MainLoginScreen.Prefab:- it is the prefab of the UI. Just drop this game object for Login Screen UI.
- Scripts :- 
     1. Class ServiceInitialization :- it can be used for any  Service initialization 
        - ServiceInitialization.UnityServiceInitialization() :-  Unity service initialization
    2. Interface IAuth :- it is the interface to interact with the implementation of the authenticaiton
    3. Each name of the class Implementation of different authentication method will be end with SignIn suffix :-
        -  for anonymous SignIn method we are using AnonymousSignIn class .
    4. All different authentication will be accessed through AuthManager class. so it will be center hub of all the authentication , and if someone want to access the method of authManager then he should access via IAuth interface .
    5. Class MainLoginScreenUI  will only handle the UI events and also it will use AuthManager class to interact with implementation of authentication.

