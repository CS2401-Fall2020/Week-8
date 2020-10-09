# Week 8

We will maintain a double linked list and keep a single node pointer. 
That stored node may not always be the head or the tail, 
but since it is doubly linked you can still reach all possible nodes by moving left or right. 

Your task is to keep a list of users and thier average scores in a game. 
Each node in the list will store the sum of that users scores so far, and the number of scores received. 
The nodes will be sorted by the `username` and this ordering will be maintained by inserting any new user in-order. 

You can print the entire list by printing the nodes to the left of a given node in reverse order, the node itself, then the nodes to the right of the given node. 

# Example
Assume that we start with a list in the following state: 

![Initial State](/images/initial.png)

We then want to add `"dfdeblasio"` recent score of `6149`. 
Do do this we move `current` to the node with the username `"dfdeblasio"` then add the score and increment the counter. 
In this case this user is to the left of the original node because it is lexicographically smaller than `"saflores"`. 
This is the state after this addition. 

![After Step 2](/images/step2.png)

When we print the entire list, it will look like the following since `"dfdeblasio"` is the `current` node. 

```
/-> caalvarado (xx) <--> null
|
\/
dfdeblasio (xx)
/\
|
\-> saflores (xx) <--> null
```

(note that `printForward()` and `printReverse()` were defined in class and can be found in the `ScoresLLNode` class already)


If we then add the score `9201` for `"igastelum"` followed by the score `8834` for `"atberowitz"` (note the order is important) 
the states would be 

![After Step 3](/images/step3.png)

after the first addition, then 

![After Step 4](/images/step4.png)

after the second addition. 

Then when printed the output would be 
```
/->
|
\/
atberowitz (8834)
/\
|
\-> caalvarado (7686) <--> dfdeblasio (6451) <--> igastelum (9201) <--> saflores (6640.6666667) <--> 
```
