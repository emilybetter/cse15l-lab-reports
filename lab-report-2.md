#Lab Report 2

###### Part 1- Simplest Search Engine
The code for my Simplest Search Engine:
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> listStrings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Number: %d", num);
        } else if (url.getPath().equals("/increment")) {
            num += 1;
            return String.format("Number incremented!");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("count")) {
                    num += Integer.parseInt(parameters[1]);
                    return String.format("Number increased by %s! It's now %d", parameters[1], num);
                }
                if (parameters[0].equals("s")) {
                    listStrings.add(parameters[1]);
                    return "Added: "+parameters[1];
                }
            }
            else if (url.getPath().contains("/search")){
                ArrayList<String> searchListStrings = new ArrayList<String>();
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    for (String s : listStrings){
                        if (s.contains(parameters[1])){
                            searchListStrings.add(s);
                        }
                    }
                    return "Result: " + searchListStrings;
                }
            }
            return "404 Not Found!";
        }
    }
}
```
In this screenshot I am calling the handleRequest method. First the method checks if there is a path after '/'. 
There is, so the value of url.gethPath() is going to be /add and the value of url.getPath().contains("/add") is true. 
Then, url.getQuery() is ?s=first. It splits this String from the =, and parameters[0] is going to store the first string (s), 
so parameters[0].equals("s") is true and parameters[1] (in this case, 'first') is added to the list of Strings. 
![Image](lab_2_add_first.png)
Adding "second":
![Image](lab_3_add_second.png)
Adding "irksome":
![Image](lab_2_add_irksome.png)
Searching for "ir":
![Image](lab_2_search_ir.png)


For each screenshot, describe:

Which methods in your code are called
What the values of the relevant arguments to those methods are, and the values of any relevant fields of the class
If those values change, how they change by the time the request is done processing
