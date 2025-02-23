# dfs & bfs

* retry: 1,**3,4**,5,6,**7**,8,14,**15**,17

## ⛹️‍♀️ Learned

### dfs
* 깊이 우선 탐색
* 부분집합, 순열, 중복순열, 조합, 모든 경우의 수, 각 원소의 상태 결정(ex.0번사용/1번사용/2번사용) 등..
* dfs문제 같다 => 바로 `상태트리`를 그리려고 해야함! 
* Tip: 백준 사이트에서 시간제한이 타이트한 문제의 경우 재귀함수 돌릴 떄 `sys.setrecursionlimit(10**6)` 넣어야지 runtime error안난다

### bfs
- 넓이(레벨) 우선 탐색
- `최단 거리`를 구할때 사용한다!
    - 왜냐? 쭈욱 레벨 우선 탐색하다가 루트노드랑 제일 가까운 레벨에서 나오는 답이 최단거리다!
      - 그 이후 레벨은 최단거리가 아니므로 더이상 볼 필요가 없으므로 바로 break한다. 
    - ex) 한번만에 가는 곳 다 탐색했는데 없어요. 두번만에 다 가는 곳 탐색했는데 또 없어요. 세번만에 가는 곳 탐색했는데 있어요 ! => 세번이최단거리. 이 순간 종착점.
     
    
- `deque()` 를 이용.
    ```
    - queue에 start 값 넣은다음에.
    - while queue: 를 이용 !!!! 보통 bfs는 queue가 비면 멈춘다.!! (dfs처럼 재귀 호출(스택) 이용하는 것 아님)
    - queue애서 popleft()한다음에
    - 뽑은 값의 자식들을 큐에 넣는데, 이때 중복 체크를 통해 갔던 곳 또 안가게 한다.
    ```

    * **최단 거리를 구하려면?** `dis` 사용. 부모의 dis + 1씩 해나간다.


### dfs VS bfs
* dfs
  * 출발점에서 도착점까지 가는 경우의 수(가지수)를 구하는 것
  * 한곳으로 쭉 뻗어나가서 도착점까지 가고 back해서 다른길 찾아보고 하는 것
    * 도착점에 도착하면 **back. 이때 꼭 check를 풀어줘야함** 다른길로 왔을때 다시 방문할 수 있게끔!!!!

* bfs
  * 최단거리 문제
  * 호수에 물을 던졌을때 동심원이 계속 커지는 것과 같음


### 격자판 탐색
* 격자판은 시계방향으로 탐색
  ```
  dx = [-1, 0, 1, 0]
  dy = [0, 1, 0, -1]
  ```
  ```
  for i in range(4):
        x = nowx + dx[i]
        y = nowy + dy[i]

        if 0<=x<=6 and 0<=y<=6 and a[x][y] == 0 and ch[x][y] == 0:
              ch[x][y] = 1
              dfs(x,y)
              ch[x][y] = 0
  ```
* 상태트리로 나타내면 자식은 부모의 상하좌우.
* dfs, bfs 모두 가능. 
  * 시작좌표에서 도착좌표까지 최단거리를 구할땐 bfs
  * 시작좌표에서 도착좌표까지 모든 경로의 가지수를 구할땐 dfs. 이때 back과정에서 check를 풀어줘야함!


### coloring a border
<img src="https://user-images.githubusercontent.com/60434971/128637436-18e6cee5-805c-4824-8e0b-6fb06d0a4f36.png" width="300"/><br>
* coloring a border, 단지찾기 같은 문제는 **DFS/BFS 둘 다 가능**
    * 단, dfs의 경우 ch 해제를 안하면 된다  

### 병합정렬 
<img src="https://user-images.githubusercontent.com/60434971/130552580-e53a8d74-436d-41c7-a3d7-e17ce362d8d0.jpg" width="1000"/><br>

### 퀵정렬
<img src="https://user-images.githubusercontent.com/60434971/130552483-b206142c-78fd-4b98-b222-664e6e78875c.png" width="1000"/><br>
