# DFS Traversal of Graph

> Recursively traverse all the connected node until unvisited node is there.

# Algorithm

- *Use  loop to travaerse all the components of graph*
- Use  visited array ( or visted vector to keep trcak of whether nodes are visited or not)
- Check whether a node is visted or not .
- Recursively traverse all the nodes connected to it .

# Code
```
 void dfs(vector<int> adj[],int i,vector<int> &ans,vector<int> &visited)
    {
        ans.push_back(i);
        visited[i]=1;
        for(auto a :adj[i]){
            
            if(visited[a]==0)
            {
               
                dfs(adj,a,ans,visited);
            }
        }
        
        
    }
    vector<int> dfsOfGraph(int V, vector<int> adj[]) {
        // Code here
        vector<int> ans;
        vector<int> visited (V,0);
        for(int i=0;i<V;i++)
        {
            if(visited[i]==0)
            
            {
            
                dfs(adj,i,ans,visited);
            }
        }
        return ans; 
    }
```

# Time & Space Complexity 

- **TC** : O(N) + O(2E) {for undirected) 
- **SC** : O(N)
N- Nodes , E - Edges
