# 15 Data Structures and Algorithm Interview Questions

### Question 1: How to find middle element of linked list in one pass?

One of the most popular question from data structures and algorithm, mostly asked on telephonic interview. Since many programmer know that, in order to find length of linked list we need to first traverse through linked list till we find last node, which is pointing to null, and then in second pass we can find middle element by traversing only half of length. They get confused when interviewer ask him to do same job in one pass. In order to find middle element of linked list in one pass, you need to maintain two-pointer, one increment at each node while other increments after two nodes at a time, by having this arrangement, when first pointer reaches end, second pointer will point to middle element of linked list.

### Question 2: How to find if linked list has a loop ?

This question has bit of similarity with earlier algorithm and data structure interview question. I mean we can use two pointer approach to solve this problem. If we maintain two pointers, and we increment one pointer after processing two nodes and other after processing every node, we are likely to find a situation where both the pointers will be pointing to same node. This will only happen if linked list has loop.

### Question 3 : How to find 3rd element from end in a linked list in one pass?

This is another frequently asked linked list interview question. This question is exactly similar to finding middle element of linked list in single pass. If we apply same trick of maintaining two pointers and increment other pointer, when first has moved up to 3rd element, than when first pointer reaches to the end of linked list, second pointer will be pointing to the 3rd element from last in a linked list.

### Question 4: In an integer array, there is 1 to 100 number, out of one is duplicate, how to find?

This is a rather simple data structures question, especially for this kind of. In this case you can simply add all numbers stored in array, and total sum should be equal to n(n+1)/2. Now just subtract actual sum to expected sum, and that is your duplicate number. Of course there is a brute force way of checking each number against all other numbers, but that will result in performance of O(n^2) which is not good. By the way this trick will not work if array have multiple duplicates or its not numbers forming arithmetic progression. 

### Question 6 : How to reverse String in Java ?

This is one of my favorite question. Since String is one of the most important type of programming, you expect lot of question related to String any data structure interview. There are many ways to reverse Sting in Java or any other programming language, and interviewer will force you to solve this problem by using without API i.e. without using reverse() method of StringBuffer. In follow-up he may ask to reverse String using recursion as well. 

### Question 7: Write a Java program to sort an array using Bubble Sort algorithm?

I have always send couple of questions from searching and sorting in data structure interviews. Bubble sort is one of the simplest sorting algorithm but if you ask anyone to implement on the spot it gives you an opportunity to gauge programming skills of a candidate. 

### Question 8: What is the difference between Stack and Queue data structure?

One of the classical data structure interviews question. I guess every one know, No? Any way main difference is that Stack is LIFO(Last In First Out) data structure while Queue is a FIFO(First In First Out) data structure.

### Question 9: How do you find duplicates in an array if there is more than one duplicate?

Sometime this is asked as follow-up question of earlier data structure interview question, related to finding duplicates in Array. One way of solving this problem is using a Hashtable or HashMap data structure. You can traverse through array, and store each number as key and number of occurrence as value. At the end of traversal you can find all duplicate numbers, for which occurrence is more than one. In Java if a number already exists in HashMap then calling get(index) will return number otherwise it return null. this property can be used to insert or update numbers in HashMap.

### Question 10 : What is difference between Singly Linked List and Doubly Linked List data structure?

This is another classical interview question on data structure, mostly asked on telephonic rounds. Main difference between singly linked list and doubly linked list is ability to traverse. In a single linked list, node only points towards next node, and there is no pointer to previous node, which means you can not traverse back on a singly linked list. On the other hand doubly linked list maintains two pointers, towards next and previous node, which allows you to navigate in both direction in any linked list.

### Question 11 : Write Java program to print Fibonacci series ?

This is not a data structures question, but a programming one, which many times appear during data structure interview. Fibonacci series is a mathematical series, where each number is sum of previous two numbers e.g. 1,1, 2, 3, 5, 8, 13, 21. Interviewer is often interested in two things, a function which returns nth number in Fibonacci series and solving this problem using recursion in Java. Though, its easy question, recursion part often confuses beginners. 
### Question 12: Write Java program to check if a number is a palindrome or not?

This is similar to previous question, not directly related to data structures, but quite popular along with other questions. A number is called palindrome, if reverse of number is equal to number itself. Interviewer ask to solve this problem without taking help from Java API or any open source library. Any way it’s simple question, you can use division operator (/) and remainder operator (%) to solve this question. Just remember, division operator can be used to get rid of last digit e.g. 1234/10 will give you 123, and modulus operator can give you last digit e.g. 1234%10 will return 4.

### Question 13 : What is binary search tree?

This is a data structure question from Tree data structures. Binary Search Tree has some special properties e.g. left nodes contains items whose value is less than root , right sub tree contains keys with higher node value than root, and there should not be any duplicates in the tree. Apart from definition, interview can ask you to implement binary search tree in Java and questions on tree traversal e.g. IN order, preorder, and post order traversals are quite popular data structure question.

### Question 14 : How to reverse linked list using recursion and iteration?

This is another good question on data structures. There are many algorithms to reverse linked list and you can search for them using google. I am thinking of writing another blog post to explain linked list reversal and will share with you later.

### Question 15: Write a Java program to implement Stack in Java?

You can implement Stack by using array or linked list. This question expect you to implement standard method provided by stack data structure e.g. push() and pop().  Both push() and pop() should be happen at top of stack, which you need to keep track. It’s also good if you can implement utility methods like contains(), isEmpty() etc. By the way JDK has java.util.Stack class and you can check it’s code to get an idea. 

### Question 16: How do you reverse a linked list?

```
public ListNode Reverse(ListNode list) {
    if (list == null) return null; // first question

    if (list.next == null) return list; // second question

    // third question - in Lisp this is easy, but we don't have cons
    // so we grab the second element (which will be the last after we reverse it)

    ListNode secondElem = list.next;

    // bug fix - need to unlink list from the rest or you will get a cycle
    list.next = null;

    // then we reverse everything from the second element on
    ListNode reverseRest = Reverse(secondElem);

    // then we join the two lists
    secondElem.Next = list;

    return reverseRest;
}
```
### OR

```
This should reverse a singly linked list, called with reverse(head,NULL); so if this were your list:
//Takes as parameters a node in a linked list, and p, the previous node in that list
    //returns the head of the new list
    
    Node reverse(Node n,Node p){   
        if(n==null) return null;
        if(n.next==null){ //if this is the end of the list, then this is the new head
            n.next=p;
            return n;
        }
        Node r=reverse(n.next,n);  //call reverse for the next node, 
                                      //using yourself as the previous node
        n.next=p;                     //Set your next node to be the previous node 
        return r;                     //Return the head of the new list
    }  
```


Read more: http://javarevisited.blogspot.com/2013/03/top-15-data-structures-algorithm-interview-questions-answers-java-programming.html#ixzz4hvjEVHhK
