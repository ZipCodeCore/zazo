# zazo
a wicked little IDE example (java) (the nano of zipcode)

pronounced: zah-zoh

The `nano` of IDEs. A simple example of an IDE in Java (220 lines of java and swing and awt).

This repo and https://github.com/ZipCodeCore/ZazoFX.

_How about a SwiftUI Mac app, with very simple sets of Command- mac keystrokes?_

_Edit menu, file menu, find menu_

`zazo` is meant to be a simple example of how to build an IDE in Java. It is not meant to be a full-featured IDE. It is meant to be a simple example of how to build an IDE in Java.

This is a VERY small IDE. It has two main UI concepts.

1. A list of files on the left side of the screen.
2. A text editor on the right side of the screen.

This UI paradigm is a very common pattern in tools like IDEs. You often see a UI where there is a list of files on the left side of the screen and a text editor (or other viewer) on the right side of the screen.
The list of files is a JTree. The text editor is a JTextArea. (See [**javax.swing**](https://docs.oracle.com/javase/8/docs/api/index.html?javax/swing/package-summary.html) for details.)

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

see zazo/zazo.sh for a simple shell script to run the app.
(well, it's called zazo_commandline but you get the idea)

And you have a small, simple IDE. Enjoy!


### JavaFX addl

```
java --module-path "/Library/Frameworks/JavaFX.framework/Versions/javafx-sdk-17.0.13/lib" --add-modules javafx.controls,javafx.fxml -jar "target/zazo-1.0-SNAPSHOT.jar" rocks.zipcode.zazo.ZazoFX
```

still not getting the right one. 

javac --module-path <path_to_javafx_lib> --add-modules javafx.controls,javafx.fxml YourFile.java

