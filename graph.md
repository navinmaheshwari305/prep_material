# Graph

## BFS
1. Alogrithm
```py
# v -> number of vertices
# adjList {vertice -> [neighbours,]}
    def BFS(self, V,adjList):
        visited = [False] * (max(self.graph) + 1)
        queue = []
 
        # Mark the source node as
        # visited and enqueue it
        queue.append(s)
        visited[s] = True
 
        while queue:
            s = queue.pop(0)
            print (s, end = " ")
 
            # Get all adjacent vertices of the dequeued vertex s. If a adjacent
            # has not been visited, then mark it visited and enqueue it
            for i in self.graph[s]:
                if visited[i] == False:
                    queue.append(i)
                    visited[i] = True
```
2. Complexities:
```py
Time Complexity: O(V+E) where V is number of vertices in the graph and E is number of edges in the graph.
```


## DFS
1. Algorithm:
```py

    # A function used by DFS
    def DFSUtil(self, v, visited):
  
        # Mark the current node as visited
        # and print it
        visited.add(v)
        print(v, end=' ')
  
        # Recur for all the vertices
        # adjacent to this vertex
        for neighbour in self.graph[v]:
            if neighbour not in visited:
                self.DFSUtil(neighbour, visited)
  
    # The function to do DFS traversal. It uses
    # recursive DFSUtil()
    def DFS(self, v):
  
        # Create a set to store visited vertices
        visited = set()
  
        # Call the recursive helper function
        # to print DFS traversal
        self.DFSUtil(v, visited)
```
2.Complexities:
```py
Time complexity: O(V + E), where V is the number of vertices and E is the number of edges in the graph.
Space Complexity :O(V). 
Since an extra visited array is needed of size V.
```

## Mother Vertex
1. Problem:
```
A mother vertex in a graph G = (V, E) is a vertex v such that all other vertices in G can be reached by a path from v.

Case 1:- Undirected Connected Graph : In this case, all the vertices are mother vertices as we can reach to all the other nodes in the graph.
Case 2:- Undirected/Directed Disconnected Graph : In this case, there is no mother vertices as we cannot reach to all the other nodes in the graph.
Case 3:- Directed Connected Graph : In this case, we have to find a vertex -v in the graph such that we can reach to all the other nodes in the graph through a directed path.
```

2. Approaches
```
1. Do DFS/BFS to in for loop for each vertex. Check if all vertexes are visited. it has complexity of O(v(V+E))
2. If there exist mother vertex (or vertices), then one of the mother vertices is the last finished vertex in DFS. (Or a mother vertex has the maximum finish time in DFS traversal).This takes O(V+E) time.
```

3. Code
```py
# code for approach 2
def findMother():

    # visited[] is used for DFS. Initially all are
    # initialized as not visited
    visited =[False]*(V)

    # To store last finished vertex (or mother vertex)
    v=0

    # Do a DFS traversal and find the last finished
    # vertex
    for i in range(V):
        if visited[i]==False:
            DFSUtil(i,visited)
            v = i
    return v
```