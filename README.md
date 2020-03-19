# PokePouch
PokePouch is a Pokemon collection app for Android making use of PokeAPI. This readme exists for the purpose of documenting my programming process.

# Getting Started
The purpose of this app is to provide a way for users to track their Pokemon collections in a mobile format. Collections will be tied to an account, the contents of which will be stored using Firebase. After creating a new project in Android Studio, I need to add dependencies and setup my Firebase.

For dependencies, I'll be using sargunv's [PokeKotlin](https://github.com/PokeAPI/pokekotlin), which is a Java/Kotlin wrapper for PokeAPI. I add its dependencies to my build.gradle, as well as Firebase's dependencies for authentication, analytics and database. After creating a Firebase for this app and adding a database, we run some simple test code to add to our database:

![](https://i.imgur.com/2V5yJ6f.png)

We check our database just to make sure that it works:

![](https://i.imgur.com/5AGs1l3.png)

# Starting Login Activity
Now that our fundamentals are set, I'd like to begin working on a simple XML layout for my login screen. 
