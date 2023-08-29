# SceneLoader
Scripts :- 
1. **Loader.cs** :- its  a class for loading scene , and its have a enum ( a group of constant ) of Scene names.
    -   **Enum Scene** :- Constants for Scene Names 
    -  **Load(Scene scene)** :- it will load the target scene after the loading Scene is completed its progress . The Sequence will be :- First the Loading scene will be loaded then Target Scene 
    - **LoadSceneAsync()** :- it will load the scene asyncronously and also wait until its done . 
    To use this async unity said to use Coroutine ,To use Coroutine in our game we need to have Monobeaviour , so we create a empty MonoBehaviour class "LoadingMonoBehaviour" . and create a gameobject which will attach the mono class and Start the coroutine (we did it in the OnLoaderCallback delegate )
    - **Variable AsyncOperation** :- To know the progress of Scene Loading , we are using AsyncOperation .
    - **LoaderCallback()** :- this method will only Trigger the action OnloaderCallback if its not null .we will use this method to call the Delegate after we have done loading the loading Scene.
    - **GetLoadingProgress()** :- it is method by which we will get the information about the progress.

2. **LoaderCallback** :-  its a class which will attach to the gameobject in order to call the Loader.LoaderCallback() method after the loading scene is loaded 
3.  **LoadingProgressBar.cs** :- it is class to update the progress of Loading Scene loading bar via Loader.GetLoadingProgress(). 
4.  **LoadingScene.unity** :- it is the scene of loading
5.  White_1X1.png :- 1 pixel image for loading bar.
<Br> Use Loader.Load(Loader.Scene.SecondSplashScreen); to load the scene 