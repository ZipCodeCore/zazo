# zazo
a wicked little IDE example (java)

pronounced: zah-zoh

This is a VERY small IDE. It has two main UI concepts.

1. A list of files on the left side of the screen.
2. A text editor on the right side of the screen.

The list of files is a JTree. The text editor is a JTextArea.

The JTree loads all the files in the current directory and displays them in the tree. When you click on a file in the tree, the text editor displays the contents of the file. You can edit the file in the text editor and save it back to the file system. (Which happens automatically when you click on another file in the tree.)

This is a very simple example of an IDE. It is not meant to be a full-featured IDE. It is meant to be a simple example of how to build an IDE.

The code is very simple and easy to understand. 
I'm trying to take the mystery out of building an IDE and building a java UI in general.

```
mvn archetype:generate -DgroupId=rocks.zipcode.zazo \
                       -DartifactId=zazo \
                       -Dversion=1.0-SNAPSHOT
```

And if you want to run the app:

```
mvn clean package
java -jar target/zazo-1.0-SNAPSHOT-jar-with-dependencies.jar
```

Now wrap that jar up in small executable jar:

```
cd zazo
mvn clean package
java -cp target/zazo-1.0-SNAPSHOT.jar rocks.zipcode.zazo.Zazo
```

And you have a small, simple IDE. Enjoy!
