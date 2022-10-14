# Lab Report 2 Week 3

## Part I

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler1 implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String str = "anewstringtoadd";
    ArrayList<String> items = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("String: %s", str);
        }
        else {
            // System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    items.add(parameters[1]);
                    return String.format("Item added: %s!", parameters[1]);
                }
            } else if (url.getPath().contains("/search")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    ArrayList<String> itemHasS = new ArrayList<String>();
                    for(int i = 0; i < items.size(); i++) 
                        if(items.get(i).contains(parameters[1]))
                            itemHasS.add(items.get(i));
                    return itemHasS.toString();
                }
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

        Server.start(port, new Handler1());
    }
}
```

Detects "/add". Adds pineapple to the list. **Method handleRequest(URI url)** is called. <u> A string of "pineapple" is added to an arraylist which contains strings. </u>
![add item1](Image/report2part1.2.png)


Detects "/add". Add apple to the list. **Method handleRequest(URI url)** is called. <u> A string of "apple" is added to an arraylist which contains strings. </u>
![add item2](Image/report2part1.3.png)


Detects "/add". Add banana to the list. **Method handleRequest(URI url)** is called. <u> A string of "banana" is added to an arraylist which contains strings.</u>
![add item3](Image/report2part1.4.png)


Detects "/search". **Method handleRequest(URI url)** is called. The code block (an else if code block) that handles "search" runs. Show items that have the substring (s). <u> An arraylist itemHasS is created and stores strings that contain the substring (s). </u>
![search items](Image/report2part1.6.png)

## Part II

### **avergeWithoutLowest(double[])**


![average failure-inducing input](Image/report2part2.1.png)

![average symptoms](Image/report2part2.2.png)

![average bug](Image/report2part2.3.png)

***Explanation:*** 
- According to the comment above the function, the bug in code resides in the last for loop. In the for loop, all numbers except numbers with the lowest value are added to sum. However, this is wrong if we have more than one numbers that have the same lowest value.
  - Expected return value: (1+2+3) / 3 = 2
  - Actually return value: (2+3) / 3 = 1.666...6667
- Solution
  - Sum up all numbers first, subtract the lower value from the sum.
  - ![average fixed](image/report2part2.3.1.png)


### **merge(List\<String\>, List\<String\>)**


![merge failure-inducing input](Image/report2part2.4.png)

![merge symptoms](Image/report2part2.5.png)

![merge bug](Image/report2part2.6.png)

***Explanation***
- The symptom means there is an infinite loop caused by the code, and memory has been used up. The reason is that in Line 50 - 53, the condition of the while loop is not updated in each interation. Therefore, once the condition is satisfied, the while loop will not end. 
- Solution
  - On Line 52, change index1 to index2.
  - ![merge fixed](image/report2part2.6.1.png)
