#  *Creating and sharing your own Android Library*

If you have ever thought of writing your own custom Android library for others to use or extend, and wonder how you could achieve that, then you can join me on this ride. In this post, I will be showing a step by step guide on how to create an Android library. I will also be showing you how to distribute your library through JitPack.


## Create Your Library

We will be creating a simple Circular Image library, that can be used to compute a basic A fast circular ImageView perfect for profile images. This is based on *RoundedImageView* from Vince Mi which itself is based on techniques recommended by *Romain Guy*. To achieve this, we follow the steps below:

Create a new Android app that showcases the library
Create a new library module within the Android app
Write the code for your custom library
Add the library as a dependency to the project
Publish your library to Github
Setup to share your library with any other android project using Jitpack
Create a new Android project
Create a new Android project using the create new project wizard on Android studio. This project will be used to test your library and also for later showcasing it.

## Create a new library module
Next is to create a new Android libraray module within the created Android app above.

Right-click the project new -> module then select Android Library

Once the project is done building, we should see our newly created module in the project.

Write library code
Our library for now will have just one class. CircularImageView.java. Create this file in the java folder under the library module.

## Add the library module as a dependency of the android project
Go to File -> Project Structure, click on the app module and select the Dependencies tab. Use the (+) icon at the bottom of the window to add a new module dependency. Select the newly created library.

Click the ok button when done. The dependency should be automatically added to the app module build.gradle file.

## Publish your library to Github
Now that our app is ready, we need to upload to Github. Init a git repository in the project root, create a new remote git repository on Github and push all committed codes to the remote repo.


## Setup and share your library through Jitpack
https://jitpack.io/
Now go to the above link and past your Git repo URL.

Jitpack is an easy to use package repository for Git. It allows you share your library with anyone by just adding the dependency of your library to their projects. We need to setup our library for Jitpack by adding some few lines to our gradle files.

Add the android-maven plugin. In the root build.grade file, add:

## Application Module
```bash
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

## Gradle
```bash
dependencies {
    ...
    implementation 'com.github.LazyyTeddy:How.2.Create.Your.Own.Lib.N.Share:1.0.0'
    (or)
    implementation 'com.github.LazyyTeddy:CircularImageView_Rajiv:1.1.1'
}
}
```

## Usage

```python
        <com.lazy.teddy.circularimagelib.CircularImageView
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:src="@drawable/chris"
            />

OR

        <com.lazy.teddy.circularimagelib.CircularImageView
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:src="@drawable/chris"
            app:civ_border_width="5dp"
            app:civ_border_color="#00BCD4"
            />
```

![Alt text](https://user-images.githubusercontent.com/46523494/53401351-a88ad980-39d5-11e9-845a-b36dc7c8a4b0.png?raw=true "Optional Title")

## References

https://jitpack.io/docs/
