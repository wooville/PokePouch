# PokePouch
PokePouch is a Pokemon collection app for Android making use of PokeAPI. This readme exists for the purpose of documenting my programming process.

# Getting Started
The purpose of this app is to provide a way for users to track their Pokemon collections in a mobile format. A collection is represented by the Pokemon that have been captured by the player out of the entirety of the Pokedex. Collections will be tied to an account, the contents of which will be stored using Firebase. After creating a new project in Android Studio, I need to add dependencies and setup my Firebase.

For dependencies, I'll be using sargunv's [PokeKotlin](https://github.com/PokeAPI/pokekotlin), which is a Java/Kotlin wrapper for PokeAPI. I add its dependencies to my build.gradle, as well as Firebase's dependencies for authentication, analytics and database. Finally, I'll need Glide to grab the sprites for the Pokemon from the PokeAPI website, since they're hosted separately from the rest of the API. After creating a Firebase for this app and adding a database, we run some simple test code to add to our database:

![](https://i.imgur.com/2V5yJ6f.png)

We check our database just to make sure that it works:

![](https://i.imgur.com/5AGs1l3.png)

# Login and Register Activities
Now that our fundamentals are set, I'd like to begin working on some simple XML layouts for my login and registration screens. Using a linear layout, I end up with something like this:

![](https://i.imgur.com/bCc9cFl.png)
![](https://i.imgur.com/8Ua4jN7.png)

Now, obviously, these pages have no functionality yet, so I'll head to the activity classes and start working on integrating it into the Firebase. Before I do that, though, I make sure to add my registration activity to the manifest, add a check to ensure they fill out the registration page correctly (using regex expressions for email and password validation), and link the two activities via Intents.

Once the validation is taken care of, I just need to create a user on my Firebase once they hit the register button (assuming their information adheres to the required format). Adding a user is as simple as creating an instance of the Firebase authenticator class, passing the email and password, and adding an onComplete listener to check if it was successful or not. Registration is done! Now time to make sure that the user is created by checking Firebase:

![](https://i.imgur.com/ihLlMrt.png)

We can see that the user is added. Now all we need to do is check in with Firebase when a user tries to sign in and send them to a new activity when it goes through, which amounts to just a couple lines of code:

![code]()

Finally, we ensure that the app just sends the user to the next activity if they're already logged in, which is even simpler.

![code2]()

# The Pouch Itself
Our login and register activities are working, and we're almost ready for the meat of the app itself. But first, we need to make sure that the user can sign out. We start by creating a new activity, the Pouch of PokePouch. We create a menu item to allow the user to log out, then add it to our new Pouch activity. We also want to listen for when it's being tapped.

![](https://i.imgur.com/PopqPdO.png)
![](https://i.imgur.com/uWaKQF6.png)



