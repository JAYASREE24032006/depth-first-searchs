# EX-2 : IMPLEMENT DEPTH FIRST SEARCH TRAVERSAL OF A GRAPH 

#### NAME : R.JAYASREE
#### R.NO : 212223040074

## AIM 
To Implement Depth First Search Traversal of a Graph using Python 3.

## THEORY :
<ol>
 <li>Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree.  </li>
 <li>The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). </li>
 <li>Use a Boolean visited array to avoid processing a node more than once.  </li>
 <li>A graph can have more than one DFS traversal. </li>
 <li>Depth-first search is an algorithm for traversing or searching trees or graph data structures. </li>
</ol>


## PROCEDURE :

The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

Step 1: Initially, stack and visited arrays are empty.

 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/640b3c6f-3ac1-49a2-a955-68da9a71f446)

Queue and visited arrays are empty initially.
Stack and visited arrays are empty initially.

Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/86dcf7d9-1f9d-49b0-a821-5976a6e77606)

 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack
 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/e6017942-08b1-4742-87ad-c97eb97bf985)

Visit node 1
Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c)

 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack
 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/20b76a05-5668-4da5-8189-e10fb1bb7238)

 Visit node 4
 Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/3b88f04a-7846-4f75-89b4-22bbd5b48e52)

Visit node 3
Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

## ALGORITHM :
</ol>
 <li>Construct a Graph with Nodes and Edges</li>
 <li>Depth First Search Uses Stack and Recursion</li>
 <li>Insert a START node to the STACK</li>
 <li>Find its Successors Or neighbors and Check whether the node is visited or not</li>
 <li>If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.</li>
</ol>

## PROGRAM : 
```
from collections import defaultdict

def dfs(g, node, visited, path):
    path.append(node)
    visited[node] = True
    for nbr in g[node]:
        if not visited[nbr]:
            dfs(g, nbr, visited, path)
    return path

g = defaultdict(list)
n, e = map(int, input().split())

for _ in range(e):
    u, v = input().split()
    g[u].append(v)
    g[v].append(u)

start = input()
visited = defaultdict(bool)
path = []
result = dfs(g, start, visited, path)
print(result)

```

## OUTPUT :

#### Sample Input 

<img width="119" height="324" alt="image" src="https://github.com/user-attachments/assets/cb9c807a-fcdf-4333-b60e-5921a04ecab7" />

#### Sample Output
<img width="288" height="53" alt="image" src="https://github.com/user-attachments/assets/241b117d-978a-4adc-8e01-790b970a8ea4" />


<img width="272" height="132" alt="image" src="https://github.com/user-attachments/assets/a580bcca-de88-4b01-a0b2-77fe919b011d" />





## RESULT :
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.

