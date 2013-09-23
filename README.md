# Android references

Android

* [Sample code](http://developer.android.com/resources/samples/index.html)
* [Common Android tasks](http://developer.android.com/resources/faq/commontasks.html)
* [Code snippets](http://www.androidsnippets.org/)
* [apps-for-android project](http://code.google.com/p/apps-for-android/) – open source apps
* [Android drawables](http://androiddrawableexplorer.appspot.com/)
* [stackoverflow for Android](http://stackoverflow.com/questions/tagged/android)

## Java

**Book reference:** This is your best reference book on Java: *Head First Java, 2nd Edition* [Amazon](http://www.amazon.com/Head-First-Java-Kathy-Sierra/dp/0596009208/ref=sr_1_1?ie=UTF8&qid=1294712873&sr=8-1) [O'Reilly.](http://oreilly.com/catalog/9780596009205/) You can read most of this on [Google Books](http://books.google.com/books?id=5VTBuvfZDyoC&printsec=frontcover&source=gbs_atb#v=onepage&q&f=false). The missing pages are [right here](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxzb2Z0ZW5namF2YXxneDoyNWRlMTA0MTVmZThmN2Rj).

### Questions

**Q: What are Java classes?**

In Java you have objects, and every object has a template that defines what its properties and functions are. A `Cat` can `cat.eat()` (a method) and a cat has a `cat.furColor` (a property). When you make a `new Cat` you give it the properties and functions on its class.

In Android, classes are used for a *lot* of things. `MainActivity` is a class, as well as `SQLiteOpenHelper`. They don't have a lot in common other than that they have a file named `MainActivity.java` and `SQLiteOpenHelper.java` and a bunch of properties and functions inside them. Read the documentation carefully for what a class should have.

**Q: What is `this` in Java?**

When you call a function like `kitty.eat("humans")`, `kitty` is an *object* of the *class* `Cat`. So in your `Cat.java` file, you'll have a method (aka a function) called `public void eat(String something) { ... }` or something to that effect. Inside of this function, if you talk about the magic `this` variable, it's referring to the `kitty` you called the `eat()` method on. 

(Sidenote: a "method" is a function defined in a class and thus all methods already have a "this" object.)


## SQL

**Android documentation on SQLite:** [http://developer.android.com/guide/topics/data/data-storage.html#db)(http://developer.android.com/guide/topics/data/data-storage.html#db)

SQL is a way of interacting with a database. If you imagine your filesystem lets you open, close, delete, rename, and move files, SQL is a way of telling a database to do those types of interactions with your data.

SQL fundamentally is a gross looking string that describes an *action* you want to do:

```sql
SELECT * FROM my_notes WHERE done = 0
```

This **selects from** the table **my_notes** all data fields (the `*` used there) **where** the **done** field is **0** (thus, all incomplete notes)

Because this is the ugliest way to work with data, we usually wrap this up in nice big Java classes.

**Q: How do I use my database using nice, big Java classes? (How do I use SQLite on Android?)**

Glad you asked. [This tutorial on AndroidHive](http://www.androidhive.info/2011/11/android-sqlite-database-tutorial/) presents a nice way to model a row in your database (here `Contact`) and a way to create, delete, and find contacts (here `DatabaseHelper`).
