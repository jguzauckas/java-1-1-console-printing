# Console Printing

In Java, we have two primary methods for printing information on the screen for the user of a program to see. They act very similarly with a key differentiator.

---

## `print`

Let's start with this code sample from `NotesPrint1.java`:

```java
System.out.print(“Hello, World!“);
```

In programming, we refer to things like `print` as **methods**. Methods are an action that the program will perform for you. In Java, we need to tell the computer exactly what to do, including where to look to find and use the `print` method, which is what the `System.out` preceding it accomplishes.

You will need to remember the syntax `System.out.print`, so one way to think about it as a set of instructions:

1. What are we asking to perform an action? We are asking the computer in general, which we refer to as `System`.
2. What kind of action would we like to do? We would like to do an output, which we refer to as `out`.
3. How would we like to output information? We would like to do it via printing out text on the screen, which we refer to as `print`.

Note the semicolon, `;`, at the end of the line. This is required in Java at the end of each regular line of code.

Methods can take in extra information in parentheses to help decide what to do, which we call **arguments**. The `print` method takes in a single argument, some text in double quotes like the `"Hello, World!"` you can see in the example above. In the case of `print`, the argument tells the method exactly what to print out on the screen.

One of the data types that Java can work with is known as a **`String`**, which for us just effectively means normal text like `this is an example` or `my name is...`. To let Java know that we are working with a `String`, we put it in double quotes like `"this is an example"`, and when we are using it directly in a method like `print`, we refer to it as a **`String` literal**.

With the details out of the way, the `print` method takes the text inside of the double quotes and parentheses and prints it to the console for the user to see. In the example above, the following output would be printed:

```
Hello, World!
```

Try it for yourself! Go over to the `NotesPrint1.java` file that this example is from and run the file to see if the output matches these notes. A lifelong programming tip is to run your code early and often as you go to make sure things are working as expected!

Performing consecutive `System.out.print` calls will result in the information being printed out one after the other one the same line, without even so much as a space added between them. Here are two examples from the `NotesPrint2.java` file:

```java
System.out.print("Hello");
System.out.print("World!");
```

You can think of `print` as a really basic cursor, writing the information you tell it to, and nothing more. It doesn't add spaces between information, it doesn't start new paragraphs on its own, it takes very specific instructions from you. In the example above, the following output would be printed:

```
HelloWorld!
```

Basic cursors can be really useful, but just stringing text together can feel like it's not as useful. What if it at least hit the `enter` or `return` key each time you printed something?

---

## `println`

Let's look at this code sample from `NotesPrintln1.java`:

```java
System.out.println("Hello, World!");
```

`println` is the mostly similar but slightly different sibling of `print`. As you can see in the example above, it appears to work almost exactly like `print`, but with one key difference based on those two new letters in the name. `ln` is short for `line`, and this method, after printing what it is told in the parentheses, will move the cursor to the next line for future printing (akin to hitting `enter` or `return` on the keyboard).

In the example above, the following output would be printed:

```
Hello, World!
```

This doesn't appear to be any different from our first example with `print` because we only printed one line of text. The second example from `print`, redone with `println` is where the difference is most noticeable. Look at this code sample from `NotesPrintln2.java`:

```java
System.out.println("Hello");
System.out.println("World!");
```

This should print `Hello`, move to a new line and then print `World!`. In the example above, the following output would be printed:

```
Hello
World!
```

Now we have some basic formatting available to us by moving to a new line, but we can only do this by finishing the current `println` command and then moving and starting a new `print` or `println` command to continue. How can we offer more customization without using a new command every time?

---

## Escape Characters

When working with `Strings` in Java, the backslash character `\` is referred to as an **escape character**. This means that if you ever use a backslash within a `String`, it actually won't just be treated as its own character. Let's look at this example from `NotesEscape1.java`:

```java
System.out.println("Backslash can be good\bad");
```

Notice that the coloring of the text looks kind of odd with the backslash. Not only is the backslash a different color, it changes the color of the next character as well, in this case the `\b` are both a different color than the rest of the text.

So what does it do? Let's start by looking at what happens when we run the code example from above:

```
Backslash can be gooad
```

First, it's clear that the `\b` itself did not print, but what happened to the `d` in `good`? The escape character utilizes the immediate next character as an instruction for what to do. In this case the `b` in `\b` is the instruction for essentially hitting the `backspace` key on a keyboard. When it tries to print the `String`, it writes out character-by-character and follows special instructions like this one. resulting in the following steps occurring:

```
Backslash can be g
Backslash can be go
Backslash can be goo
Backslash can be good
Backslash can be goo
Backslash can be gooa
Backslash can be gooad
```

As we can see in these steps, it did write out `good`, but then following the escape character sequence for backspace and removed the last character before continuing. Our computers work so fast, that this all appears to happen instantaneously.

The common escape character combinations are as follows:

- `\\` - This will print a single backslash `\` (thereby allowing you to still print one if needed)
- `\n` - This will move to a new line, effectively hitting the `enter` or `return` keys
- `\t` - This will insert a tab space, moving text a significant amount over
- `\"` - This will print a double quote character `"`, instead of treating as a quotation mark to close a string

Let's look at an example where each of these is used:

```java
System.out.println("Backslash can be good\\bad");
System.out.print("I can put a new line here\nand don't need println\n");
System.out.println("I can say one thing here and move the other over\tthere");
System.out.println("Mr. G once said \"Backslashes are extremely useful\"");
```

Can you predict how the output would print here? Compare what you think against the output here:

```
Backslash can be good\bad
I can put a new line here
and don't need println
I can say one thing here and move the other over        there
Mr. G once said "Backslashes are extremely useful"
```

Escape character sequences allow us to do things much more easily than we would be able to otherwise, please work on remembering them!

---

## Final Notes

Taking our very first example from `NotesPrint1.java`, the whole file looks like this:

```java
public class NotesPrint1{
    public static void main (String[] args){
        System.out.print("Hello, World!");
    }
}
```

We only honed in on the middle line with `print` initially, but every piece of this file is important to the program running and doing what we want. Taking a look at our second example from `NotesPrint2.java`, that whole file looks like this:

```java
public class NotesPrint2{
    public static void main (String[] args){
        System.out.print("Hello");
        System.out.print("World!");
    }
}
```

Comparing the first two lines of code from both files should feel extremely similar, with only a slight variation. All of our Java files for the foreseeable future will have this structure. The first line is `public class NameOfFileHere{`, where you'll notice that in both examples, it utilizes the name of the file without the `.java` extension. The second line is identical in both cases as `public static void main (String[] args){`.

Throughout the year we will end up unpacking these lines and better understand how they work to better use them to our advantage. For the time being though, we will let Visual Studio Code autofill those lines when we create a Java file and understand that it's on the third line where we put our code using things like `print` statements.

---

## Assignment

Now that you have gone through the notes for this section, you can check out `Initial Try` folder to try a short assignment using this material.
