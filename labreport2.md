## Lab Report 1

# PART1

***ChatServer.Java***

```
import java.io.IOException;
import java.net.URI;

class ChatHandler implements URLHandler {
    private String chatHistory = "";

    public String handleRequest(URI url){
        if(url.getPath().equals("/add-message")){
            String[] parameters = url.getQuery().split("&");
            String message = parameters[0].split("=")[1];
            String user = parameters[1].split("=")[1];
            chatHistory += user + ": " + message + "\n";
        }
        return chatHistory;
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new ChatHandler());
    }
}

```
***/addMessage 1***

![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/addMessage1.png?raw=true)
- The handleRequest method in the ChatHandler class is called (ChatHandler.handleRequest(URI url)). It handles the incoming request.
- The **argument** for this method is a **"url"** which is a URI object that represents the request. This argument url is /add-message?s=Hello&user=jpolitz for this image. A relevant **field** is **"chatHistory"** which is an originally an empty string "". 
- The URI url arguement is /add-message?s=Hello&user=jpolitz. The chatHistory field in the Chathandler class changes from an empty string to "jpolitz: Hello\n" as the method finds the user which is "jpolitz" and message which is "Hello" from the url and appends it to the string.
  
***/addMessage 2***

![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/addMessage2.png?raw=true)
- The handleRequest method in the ChatHandler class is called again (ChatHandler.handleRequest(URI url)). It handles the new incoming request again.
- The **argument** for this method is a **"url"** which is a URI object that represents the request(same as before but for the new url). This argument url is /add-message?s=Hi!&user=isdesai for this image. A relevant **field** is **"chatHistory"** which is a string and before this method call is "jpolitz: Hello\n". 
- The URI url argument changes to /add-message?s=Hi!&user=isdesai. The chatHistory field in the Chathandler class changes from "jpolitz: Hello\n" to "jpolitz: Hello\nisdesai: Hi!\n" as the method finds the user which is "isdesai" and message which is "Hi!" from the new url and appends it to the existing string.
# PART2

***The absolute path to the private key***

***The absolute path to the public key***

***ieng6 login without password***

# PART3

Something new I have learned this week that i didnt know before is how to start a web server. I also learned about the URI class and how to read a url. I learned how to read and manipulate queries using code. 


