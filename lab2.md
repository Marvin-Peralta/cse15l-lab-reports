# **CSE15L Lab Report 2**
## By Marvin Peralta, A17271264

### **Part 1**

```
import java.io.IOException;
import java.net.URI;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.List;
import java.util.Arrays;

class StringHandler implements URLHandler {
  List<String> lines;
  String path;
  StringHandler(String path) throws IOException {
    this.path = path;
    this.lines = Files.readAllLines(Paths.get(path));
  }
  public String handleRequest(URI url) throws IOException {
    String query = url.getQuery();
    if(url.getPath().equals("/add")) {
      if(query.startsWith("s=")) {
        String toAdd = query.split("=")[1];
        this.lines.add(toAdd);
        String fullLines = "";
        for (int i = this.lines.size() - 1; i >= 0; i--) {
          fullLines += this.lines.get(i) + "\n";
          System.out.println(fullLines);
        }
        return fullLines;
      }
      else {
        return "/add requires a query parameter s\n";
      }
    }
    else if(url.getPath().equals("/save")) {
      String toSave = String.join("\n", lines) + "\n";
      Files.write(Paths.get(this.path), toSave.getBytes());
      return "Saved!\n";
    }
    else if(url.getPath().equals("/search")) {
      if(query.startsWith("q=")) {
        String toSearch = query.split("=")[1];
        String result = "";
        for(String s: lines) {
          if(s.contains(toSearch)) {
            result += s + "\n";
          }
        }
        return result;
      }
      else {
        return "/search requires a query parameter q\n";
      }
    }
    else {
      return String.join("\n", lines) + "\n";
    }
  }
}

class StringServer {
  public static void main(String[] args) throws IOException {
    if(args.length == 0){
      System.out.println("Missing port number! Try any number between 1024 to 49151");
      return;
    }
    if(args.length == 1){
      System.out.println("Missing file path! Give a path to a text file as the second argument.");
      return;
    }

    int port = Integer.parseInt(args[0]);

    Server.start(port, new StringHandler(args[1]));
  }
}
```

<img src="HelloMessage2.png" alt="HelloMessage" width="250" height="200">

DISCLAIMER: I used the Skill Demo's stringsearch-main code and edited some of its contents to do this lab report!

The main method was called to start the server (essentially calling the `start` method in Server.java, but because I ran the server to display an empty file called `labresub.txt`, I had to add the string `hello` through editing the URL, calling the `handleRequest` method.

<img src="WorldMessage2.png" alt="WorldMessage" width="250" height="200">

Again, I edited the URL to add `world` so `handleRequest` was called again

Relevant arguments in the code are the URL containing any of the following:
`/add-message`
`/search`
`/save`
Whatever is added, saved, or searched is a string from a list of strings saved in labresub.txt (or there for the time being). So even if an int, char, or double are added, it will still be a string value.

The list of string append a string given `/add-message?s=<text>` is added to the URL where `text` is the string added.


### **Part 2**

Note:
```
LinkedList emptyLL = new LinkedList();
LinkedList anotherEmptyLL = new LinkedList();

```
This block of code came before the tests

```
@Test
public void testAppendEmpty() {
  this.emptyLL.append(12);
  assertEquals(12, this.emptyLL.root.value);
  }
```
This test passed
```
@Test void testToString() {
  this.anotherEmptyLL.prepend(45);
  this.anotherEmptyLL.append(52);
  this.anotherEmptyLL.prepend(22);
  assertEquals("22, 45, 52", this.anotherEmptyLL.toString());
```
This test failed

<img src="JUnit_Tests2.png" alt="JUnitTests" width="250" height="200">

```
public String toString() {
  Node n = this.root;
  String s = "";
  while(n != null) {
    s += n.value + " ";
    n = n.next;
  }
  return s;
}
```
This is the old code
```
public String toString() {
  Node n = this.root;
  String s = "";
  if (n != null) {
    s += n.value;
    n = n.next;
    while (n != null) {
      s += " " + n.value;
      n = n.next;
    }
  }
  return s;
```
This is the new code that passes the JUnit test

The JUnit assertEquals compares `22 45 52` to `22 45 52 ` where there is a space left over. In the new code, spaces are only in between existing values instead of after every existing value. Now the JUnit test for `testToString()` works.

<img src="JUnit_Tests3.png" alt="JUnitTests2" width="250" height="200">

### **Part 3**

I learned that you can change a web server's contents by simply portions of the URL. Of course, this does not apply to all sites, only those that are programmeed to do so, yet it is really interesting to alter the contents without having to change some of the coding.
