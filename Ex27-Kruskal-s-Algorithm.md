# Ex27 Kruskal’s Algorithm
## DATE:
## AIM:
To write a C program to implement Kruskal's Algorithm for finding minimum cost

## Algorithm
```
1.nitialize:Set ne = 1, mincost = 0; declare cost[9][9] for adjacency matrix and parent[9] for disjoint sets; define find(int) and uni(int, int) functions.
2.Input: Read number of vertices n; fill cost[i][j] matrix using scanf; replace 0 with 999.
3.MST Construction Loop:While ne < n: find the minimum edge, use find() to check if it connects different trees.
5.Include Edge: If valid, merge trees with uni(), print the edge, increment ne, and update mincost; set used cost[a][b] and cost[b][a] to 999.
5.Result: After the loop, print Minimum cost = %d\n, showing total MST cost.
```
## Program:
```
/*
/*
Program to implement Kruskal's Algorithm
Developed by: ADITYA NAGA SAI P
RegisterNumber:  212223110036
*/
    #include <stdio.h>
    #include <stdlib.h>
    int i,j,k,a,b,u,v,n,ne=1;
    int min,mincost=0,cost[9][9],parent[9];
    int find(int);
    int uni(int,int);
    int main()
    {
          scanf("%d",&n);
          for(i=1;i<=n;i++)
     {
     for(j=1;j<=n;j++)
     {
     scanf("%d",&cost[i][j]);
     if(cost[i][j]==0)
     cost[i][j]=999;
     }
     }
         while(ne < n)
     {
     for(i=1,min=999;i<=n;i++)
     {
     for(j=1;j <= n;j++)
     {
     if(cost[i][j] < min)
     {
     min=cost[i][j];
     a=u=i;
     b=v=j;
     }
     }
     }
     u=find(u);
     v=find(v);
     if(uni(u,v))
     {
     printf("%d edge (%d,%d) =%d\n",ne++,a,b,min);
     mincost +=min;
     }
     cost[a][b]=cost[b][a]=999;
     }
     printf("Minimum cost = %d\n",mincost);
     return 0;
       }
    int find(int i)
    {
     while(parent[i])
     i=parent[i];
     return i;
    }
    int uni(int i,int j)
    {
     if(i!=j)
     {
     parent[j]=i;
     return 1;
     }
     return 0;
    }
 
*/
```

## Output:

![image](https://github.com/user-attachments/assets/e2f3789e-4030-4255-9c57-0da716fea18d)


## Result:
Thus, the C program to implement Kruskal's Algorithm for finding minimum cost is implemented successfully.
