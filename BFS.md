# BFS Traversal of Graph

> Traverse the adjacent nodes first then move ahead.

# Algorithm
- *Use  loop to travaerse all the components of graph*
- Use queue data structure and a visited array ( or visted vector to keep trcak of whether nodes are visited or not)
- Push the starting node in queue and mark it as visited .
- While queue is not empty :
  - dequeue the first node and print it.
  - If their adjacent nodes are not visted then push them in queue and mark them as visited. 
  - Reapeat the steps 
# Code
```
vector<int> bfsOfGraph(int V, vector<int> adj[]) {
        vector<int> bfs;
        vector<int> vis(V,0);
        // 0 denotes node isn't visited yet and 1 signifies node is visited
        for(int i=0 ;i<V;i++)
        {
            if(!vis[i])
            {
                queue<int> q;
                q.push(i);
                vis[i]=1;
                while(!q.empty())
                {
                    int node = q.front();
                    q.pop();
                    bfs.push_back(node);
                    
                    for(int it:adj[node])
                    {
                        if(!vis[it])
                        {
                        q.push(it);
                        vis[it] =1;
                        }
                    }
                }
            }
        }
        return bfs;
    }
```

# Time & Space Complexity 
- **TC** : O(N+E) 
- **SC** : O(N)
N- Nodes , E - Edges
