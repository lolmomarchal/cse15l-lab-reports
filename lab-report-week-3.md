WEEK 3 LAB REPORT 
============
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*10/14/2022*


>***Part 1**

My code for the SearchEngine from week 2 is pictured below:

```import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;


class Handler2 implements URLHandler {


    List<String> list = new ArrayList<>();
    int index = 0;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Strings: %s", Arrays.toString(list.toArray()));
        } else if (url.getPath().contains("/add")) {
            String[] string = url.getQuery().split("=");
            list.add( string[1]);
            index++;
            return String.format("String added to list!");
        }
        else if(url.getPath().equals("/search")){

            List<String> search = new ArrayList<>();
            int indexSearch =0;
            if(list.size() == 0)
            {
                return String.format("Currently, no Strings are on the list. To search" +
                        "please add some strings first.");
            }
            String[] string = url.getQuery().split("=");
            for(int i = 0; i < list.size();i++ ){
                if(list.get(i).contains(string[1])){
                    search.add(list.get(i));
                }

            }
            return String.format("Results: %s",  Arrays.toString(search.toArray()));
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/list")) {
                List<String> temp = new ArrayList<>();
                for(int i = 0; i< list.size(); i++)
                    if(list.get(i) != null){
                        temp.add(list.get(i));
                    }

                    return String.format("Current list of strings: %s", Arrays.toString(temp.toArray()));
                }
            }
            return "404 Not Found!";
        }
    }


    class SearchEngine{
        public static void main(String[] args) throws IOException {
            if(args.length == 0){
                System.out.println("Missing port number! Try any number between 1024 to 49151");
                return;
            }

            int port = Integer.parseInt(args[0]);

            Server.start(port, new Handler2());
        }



    }




 ```
 There are currently three commands supported by this program:
1.) **Adding** a string
2.) **Printing** the list of strings
3.)**Searching** all the strings containing a certain string of characters

The first one, adding, is used by using the /command and the query after it:

![image](https://user-images.githubusercontent.com/114376800/195965351-44c12611-cb65-4b3a-89a3-d68973f64acc.png)
 
 Using the /list command allows us to be able to see all of the current strings within the list
 
 ![image](https://user-images.githubusercontent.com/114376800/195965437-2b4067ab-a368-4edd-8038-87abe4c565f3.png)
 
 Following this, using the /search command for the key word "a" yields:
 
 ![image](https://user-images.githubusercontent.com/114376800/195966260-d4106528-72ca-4a6c-83a3-c2b5530de2b7.png)
 
 
 In each of these screenshots, the method being called is the handleRequest method, which takes the url as an input. The url is then split into the path. There are 3 different ifs within the method
 which all search for a certain keyword within the path(ex: /search, /list, /add) so the proper code can be run in response to a specific command. In the case of add and search, the path
 is split into an array using the keycharacter "=" as reference. In this new array, string[0] is the rest of the path including the command, and string[1] is the word 
 we are searching or attempting to add to the list. In the **/add if**, this is simply added through the usage of the List .add() method and it returns a message saying the word
 has been added to the list. On the other hand, in the **/search if**, each value is checked to see if it contains the string provided in string[1] and added to another list, which is later
 converted into an array using the .toArray() method of the List class. In the **/list** if, all of the contents of the this.list are transferred to anotehr list and then printed out. 
 
> **Part 2: **


One of the bugs I found during the lab was within ArrayExamples.java. The reverse method of this class was faulty. 

- the test I used to test this method was: 

![image](https://user-images.githubusercontent.com/114376800/195966649-9d8db336-d686-4e0f-8138-58e627fccbbf.png)

-The symptom was that this method was returning a new array that was [0,0,0,0,0]

![image](https://user-images.githubusercontent.com/114376800/195966707-7ddb7c4e-e661-445f-8dfb-9125c39a196f.png)

- The bug was due to the fact that all of the newArray is 0 so when making it equal to arr[i] it was making the entirety of array[i] = to 0.
- To fix this, all that had to be done was: 

![image](https://user-images.githubusercontent.com/114376800/195966826-5acd0953-14b4-4063-8c24-9c780307641f.png)

Which sets newArray to the values of arr!


The next bug I found was in the first method of the LinkedList class:

-The test I used to test this method was:

![image](https://user-images.githubusercontent.com/114376800/195966960-0acdd4c2-73db-451c-ae91-5d4c489e607f.png)

Which passes an empty string. 
-The symptom/result of this test is a NullPointerException
![image](https://user-images.githubusercontent.com/114376800/195967000-ae13683d-3cdd-4929-9a8d-49292a73966c.png)
-This is a bug, as it does not follow the same behavior with dealing with nulls as the rest of the program
-To fix this, I added a throw new NoSuchElementExeception() when this.root is equal to null

![image](https://user-images.githubusercontent.com/114376800/195967095-194926dd-e200-46f8-9ddf-572b1b523736.png)

