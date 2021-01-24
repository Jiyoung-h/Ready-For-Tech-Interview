# DFS & BFS

- 그래프 알고리즘, 경로를 찾는 문제시 활용

## DFS
- 깊이 우선 탐색
- 임의의 노드에서 다음 브랜치로 넘어가기 전에, 해당 브랜치를 모두 탐색하는 방법
- 스택 / 재귀함수를 통해 구현
- 모든 경로를 방문해야 할 경우 적합
- 시간복잡도 (V: 접점, E: 간선)
    - 인접 행렬 : ```O(V^2)```
    - 인접 리스트 : ```O(V+E)```

```
void dfs(int start){
    if(visit[start]) return;
    visit[start] = true;
    for(int i=0; i<a[start].size(); i++){
        int x = a[start][i];
        dfs[x];
    }
}
```

## BFS

- 너비 우선 탐색
- 임의의 노드에서 인접한 노드를 먼저 탐색하는 방법
- 시작 정점으로부터 가까운 정점을 먼저 방문하고 멀리 떨어져 있는 정점은 나중에 방문하는 순회 방법
- 큐를 통해 구현
- 최소 비용을 구할 때 적합
- 시간복잡도 (V: 접점, E: 간선)
    - 인접 행렬 : ```O(V^2)```
    - 인접 리스트 : ```O(V+E)```

```
void bfs(int start){
    queue<int> q;
    q.push(start);
    visit[start] = true;
    
    while(!q.empty()){
        int x = q.front();
        q.pop();
        printf("%d", x);
        for(int i=0; i<a[x].size(); i++){
            int y=a[x][i];
            if(!visit[y]){
                q.push(y);
                visit[y]=true;
            }
        }
    }
```
