void topo(vector<int> adj[],vector<int>&visited,stack<int>&s,int n,int node){
        visited[node]=1;
        for(auto it:adj[node]){
            if(!visited[it]){
                topo(adj,visited,s,n,it);
            }
        }
        s.push(node);
        
    }
    //Function to return list containing vertices in Topological order. 
    vector<int> topoSort(int n, vector<int> adj[]) 
    {
              
        stack<int>s;
        vector<int>visited(n,0);
        for(int i=0;i<n;i++){
            if(!visited[i]){
                topo(adj,visited,s,n,i);
            }
        }
        vector<int>ans;
        while(!s.empty()){
            ans.push_back(s.top());
            s.pop();
        }
        return ans;
    }

 Time Complexity => O(N+E)
 Space Complexity=> O(N),O(N)
