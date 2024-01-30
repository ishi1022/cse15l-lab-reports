# cse15l-lab-report
## Lab Report 2

ChatServer.Java
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
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/addMessage1.png?raw=true)

![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/addMessage2.png?raw=true)
