# Part 1 - String Server
  Here is the code for the StringServer.java program which displays a string that is continuously incremented through in a URL query
  
 ``` 
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String strings = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            if (url.getQuery().contains("=") == false) {
                return "Invalid Query";
            }
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                strings += parameters[1] + "\n";
                return strings;
            }
            else {
                return "Invalid Query";
            }
        }
        else { 
            return "404 Not Found!";
        }
    }
}


class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

Here is the output for the url `localhost:4000/add-message?s=Hello`
![](images/StringServerHello.png)
The code first checks that the path contains `/add-message` and that the query is in the format `?s=<String>`. Afterwards, the String array `parameters`
has its 1st index set to `Hello`. Then, the String `strings` is concatonated with `parameters[1]` and `"\n"` to add a new line to the string.
