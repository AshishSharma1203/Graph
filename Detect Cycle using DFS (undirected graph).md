# Detect a Cycle in an Undirected Graph using DFS
> [GFG Problem link ](https://practice.geeksforgeeks.org/problems/detect-cycle-in-an-undirected-graph/1)



# Approach 
- While pushin nodes to queue push node along with parent node 
-While performing DFS traversal if adjacent node is already visited and its not the parent node then ther is loop
# Code
```
class Solution {
  public:
    // Function to detect cycle in an undirected graph.
    
    bool check(int src,vector<int> &visited,vector<int> adj[],int parent)
    {
        
        visited[src]=true;
        
        for(auto nodes:adj[src])
        {
            if(visited[nodes]==1)
            {
                if(nodes!=parent)
                {
                    return true;
                }
              
            }
              else
                {

                  if ( check(nodes,visited,adj,src)==true)
                  {
                      return true;
                  }
                }
        }
        
        return false;
        
    }
    
    bool isCycle(int v, vector<int> adj[]) {
        // Code here
        
       
        
        vector<int> visited (v,0);
        
        for(int i=0;i<v;i++)
        {
            if(visited[i]==0)
            {
                int parent=-1;
                if(check(i,visited,adj,parent))
                {
                    return true;
                }
              
            }
        }
        
     return false;
     
    }
};

```

# TC & SC 
__TC__ : O(N+2E)

for disconnected graph it will be O(N+2E) + O(N)

__SC__ : O(N) +O(N) for recursion stack and visited array
