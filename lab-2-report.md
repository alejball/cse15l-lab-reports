# Part 1
        import java.io.IOException;
        import java.net.URI;
        import java.util.ArrayList;

        class Handler implements URLHandler {
            // The one bit of state on the server: a number that will be manipulated by
            // various requests.
            ArrayList<String> StringList = new ArrayList<>();
            public String handleRequest(URI url) {
                if (url.getPath().equals("/")) {
                    return String.format("String engine");
                } else if (url.getPath().equals("/add")) {
                    StringList.add(url.getQuery().split("=")[1]);
                    return String.format("Word added!");
                } else {
                    System.out.println("Path: " + url.getPath());
                    if (url.getPath().contains("/search")) {
                        String parameters = url.getQuery().split("=")[0];
                        if(a.size() == 0){
                            return String.format("No words in list");
                        }
                        String WordsInString = "";
                        for(String c:StringList){
                            if(c.contains(parameters[1])){
                                WordsInString = WordsInString + c + ",";
                            }
                        }
                        return String.format(WordsInString.substring(0,WordsInString.length() - 1));
                    }
                    else if(url.getPath().contains("/clear")){
                        StringList.clear();
                        return String.format("List cleared");
                    }
                    return "404 Not Found!";
                }
            }
        }

        class SearchEngine {
            public static void main(String[] args) throws IOException {
                if(args.length == 0){
                    System.out.println("Missing port number! Try any number between 1024 to 49151");
                    return;
                }

                int port = Integer.parseInt(args[0]);

                Server.start(port, new Handler());
            }
        }
![Adding egregious](https://github.com/alejball/cse15l-lab-reports/blob/c25f862dd2e89fab430cc880a2780d1fa84cf5ab/Screenshot%202022-10-14%20140512.png)

Here, as you can see from the image above I am adding the word "egregious" to my list of words. I am calling the handleRequest method in the Handler class. The part of the code that handles adding words to the list is the first elseif statement. The getPath() method gets the path in the URL and checks if it is equal to "/add". After that, what this portion of the code does is get the query (the stuff after the question mark) using the getQuery() method and separated the string using the split method into an array with the "=" as the indicator for where to split the string. Then, the string in the first index of the array (which is the word I want to add) is added to an ArrayList I have under the name StringList. Then, printed on the screen is "Word added!" to indicate the word has been added to the list of words.

![Searching for words with 'ous'](https://github.com/alejball/cse15l-lab-reports/blob/c25f862dd2e89fab430cc880a2780d1fa84cf5ab/Screenshot%202022-10-14%20140601.png)

Having added "egregious" with "/add," I am now searching my list of strings (that only has one word) for words that contain "ous." I am calling the handleRequest method in the Handler class. First, my code gets the path of the URL using the getPath() method, then sees if that path contains "/search" using the contains method. It does contain "/search" so the code then uses the getQuery() method and the split method to split the query (the stuff after the question mark) into a String array, then the string in the 1 index is stored in parameters (this is what I am searching for). The code then has a for loop that iterates through the words in StringList and checks if the words contain what is stored in parameters ('ous') using the contains method. The code then adds the words that match to an empty string I have stored in WordsInString followed by a comma. Then, the code prints WordsInString to the screen, but uses the substring method to cut out the comma that would have been there.

![Clearing list](https://github.com/alejball/cse15l-lab-reports/blob/c25f862dd2e89fab430cc880a2780d1fa84cf5ab/Screenshot%202022-10-14%20142237.png)

Now that I've shown how to add and search for words using my simple engine, I am now going to show how to clear the word list using my engine. As you can see in the URL above I have added "/clear" to the URL instead of "/add" or "/search." What the code does is pretty simple. First, it gets the path using the getPath() method on the URL, then checks to make sure the path contains "/clear" using the contains method. Afterwords, the clear() method is used to completely erase everything within StringList. Then, "List cleared" is printed to the screen.
# Part 2
## ArrayExamples: reversed
input: {1,2,3,4,5}

ouput (symptom):{0,0,0,0,0}

This is a visual of what I need to change in the code to fix this bug:
![Change needed](https://github.com/alejball/cse15l-lab-reports/blob/bc3e834c46acb2f81cbbc015b30ee4620aa61fb8/Screenshot%202022-10-14%20161742.png)

This is after I have changed the code to get rid of the bug:
![fixed code](https://github.com/alejball/cse15l-lab-reports/blob/bc3e834c46acb2f81cbbc015b30ee4620aa61fb8/Screenshot%202022-10-14%20161808.png)

In the first image with the original code, you see the elements in arr are being replaced with a newly created array newArray starting with the last index in newArray. The issue with this is because the values in the new Array look like: {0,0,0,0,0}. Meaning, the elements in arr are being replaced with 0. Meaning, we have to switch arr and newArray in the for loop and then replace arr being returned with newArray being returned instead. This allows for the elements in newArray to be replaced with the elements in arr, starting with the last index in arr.
## ListExamples: filter
input: {"allow","b","cows","d","egregious","f"}            (this is a List, not an Array)

output(symptom): {"egregious","cows","allow"}              (this is a List, not an Array)

This is a visual of what I need to change in the code to fix this bug:
![Change needed](https://github.com/alejball/cse15l-lab-reports/blob/d2f2c7fa3293cbb0dadf28c169bf03cf6adbcaab/Screenshot%202022-10-14%20164246.png)

This is after I have changed the code to get rid of the bug:
![Fixed code](https://github.com/alejball/cse15l-lab-reports/blob/d2f2c7fa3293cbb0dadf28c169bf03cf6adbcaab/Screenshot%202022-10-14%20170228.png)

Specifically, the symptom here is the reversed order of the valid inputs within the List. Valid strings are those whose lengths are greater than 3 for my example. The bug causing this code is what I have blocked out with red in the first image . What this blocked out code was doing was adding strings to the zeroth index of the list. Meaning, it was reversing the order of the valid strings instead of being in the same order as in the orginal list. To fix this I replaced the List add method that takes in two arguments for the List add method that takes in one argument. The reason for this is because the List add method that takes in one arguments automatically adds new strings to the end of the List, thus returning valid strings in the order they appeared in the input List.
