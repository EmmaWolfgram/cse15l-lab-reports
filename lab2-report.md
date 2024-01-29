# Lab 2 Report

## Part 1

```
import java.io.IOException;
import java.net.URI;

class ChatHandler implements URLHandler {
  String lines = "";

  public String handleRequest(URI url) {
    ///add-message?s=<string>&user=<string>
    String query = url.getQuery();
    if(url.getPath().equals("/add-message")) {
      String userName = "";
      String message = "";

      String userString = query.split("&")[1];
      if(userString.startsWith("user=")){
        userName = userString.split("=")[1];
      }
      String messageString = query.split("&")[0];
      if(messageString.startsWith("s=")){
        message = messageString.split("=")[1];
      }
      String fullMessage = userName + ": " + message;
      lines = lines + fullMessage + "\n";
      return lines;
    }
    return "this url needs a /add-message path";
  }
}

class ChatServer {
  public static void main(String[] args) throws IOException {
    if(args.length == 0){
      System.out.println("Missing port number!");
      return;
    }
    int port = Integer.parseInt(args[0]);
    Server.start(port, new ChatHandler());
  }
}
```

![Image](cse15l ss 1.png)
**Which methods in your code are called?**

**What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

**How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

![Image](cse15l ss 2.png)
**Which methods in your code are called?**

**What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

**How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

## Part 2

Using the command line, show with ls and take screenshots of:

**The absolute path to the private key for your SSH key for logging into ieng6:**


**The absolute path to the public key for your SSH key for logging into ieng6:** (this is the one you copied to your account on ieng6, so it should be a path on ieng6's file system)
![Image](cse15l privkey.png)

**A terminal interaction where you log into your ieng6 account without being asked for a password:**
![Image](cse15l ssh-witho-pass.png)

## Part 3
**In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn't know before.**
