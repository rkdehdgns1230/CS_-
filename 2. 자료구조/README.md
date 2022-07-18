# Data Structure

## Dijkstra(다익스트라)
다익스트라 알고리즘(dijkstra algorithm)은 그래프 상에서 시작 노드를 기점으로 다른 노드로 가는 최단 경로를 탐색하는 대표적인 최단 경로(shortest path) 탐색 알고리즘이다.

간단하게 말해서 다익스트라 알고리즘을 사용하면, 하나의 노드에서 그래프 내의 모든 노드로 가는 최단 경로를 구할 수 있다. 다만, 다익스트라 알고리즘을 사용해서 최단 경로를 탐색하기 위해서는 그래프 내에 음의 간선이 포함돼서는 안된다는 점을 유의해야 한다.

**다익스트라 알고리즘의 흐름**

1. 시작 노드를 기준으로 모든 노드에 대한 최단 거리를 저장하는 배열을 초기화한다. (일반적으로 최댓값으로 갱신해 준다.)
2. Heap 자료 구조(priority queue)에 시작 노드를 넣어줍니다. (최소힙을 사용합니다. 이는 다음 방문할 노드를 최솟값을 우선으로 방문하기 위함이다.)
3. Heap이 빌 때까지 while 문을 반복한다.
4. Heap의 head에 해당하는 노드의 인접한 노드(연결되어 있는 노드)에 대해서 현재 노드를 거쳐 가는 경우 최단 거리가 갱신되는지 판단한다.
5. 최단 거리가 갱신되면 Heap에 해당 인접 노드를 넣어준다.
6. 3번 ~ 6번 과정으로 while 문이 끝날 때까지 반복

```c
#include <iostream>
#include <vector>
#include <queue>

using namespace std;

int n, m; // 노드의 개수, 간선의 개수
int INF = 1000000000;

// edge data
vector<pair<int, int>> a[7]; // pair<end point, distance>
// 그래프 내의 모든 노드로의 최단 경로를 저장한다.
int d[7];

void dijkstra(int start) {
	d[start] = 0;
	priority_queue<pair<int, int>> pq; // heap structure <distance, end point>
	pq.push(make_pair(0, start));

	while (!pq.empty()) {
		int cur = pq.top().second; // shortest path's index in heap
		// 짧은 길이가 가장 위로 저장될 수 있도록 음수의 형태로 저장하자!
		int distance = -pq.top().first;
		pq.pop();

		// 이미 shortest path가 아닌 경우 skip
		if (d[cur] < distance) continue;

		// 선택된 노드의 인접 노드를 이용하여 최소 거리를 갱신하는 for loop
		for (int i = 0; i < a[cur].size(); i++) {
			int next = a[cur][i].first;
			int next_distance = a[cur][i].second + distance;

			if (d[next] < next_distance)
				continue;

			d[next] = next_distance;
			// same with pq.push(make_pair(next, -next_distance));
			pq.push({ -next_distance, next });
		}
	}
}

int main() {
	cin >> n >> m;

	// 모든 최단 경로의 거리를 INF로 초기화
	for (int i = 1; i <= n; i++) {
		d[i] = INF;
	}

	for (int i = 0; i < m; i++) {
		int start, end, distance;
		cin >> start >> end >> distance;

		a[start].push_back({ end, distance });
	}

	dijkstra(1); // 1번 노드에서 시작한다.

	for (int i = 1; i <= n; i++) {
		cout << i << "번째 노드로의 최단 경로: " << d[i] << "\n";
	}

	return 0;
}
```

```
입력:
6 7
1 2 3
1 5 5
2 3 3
2 4 5
5 4 1
5 6 5
6 3 1

출력:
1번째 노드로의 최단 경로: 0
2번째 노드로의 최단 경로: 3
3번째 노드로의 최단 경로: 6
4번째 노드로의 최단 경로: 6
5번째 노드로의 최단 경로: 5
6번째 노드로의 최단 경로: 10
```
