# Data Structure
- [Data Structure](#data-structure)
- [Array](#array)
  - [Array 특징](#array-특징)
- [Linked List](#linked-list)
  - [Linked List 특징](#linked-list-특징)
- [Array List](#array-list)
- [Stack](#stack)
- [Queue](#queue)
- [Tree](#tree)
  - [Tree 용어](#tree-용어)
  - [Binary Tree](#binary-tree)
  - [BST(Binary Search Tree)](#bstbinary-search-tree)
  - [Binary Heap](#binary-heap)
    - [Heap 구현](#heap-구현)
    - [Heapify](#heapify)
  - [RBT(Red Black Tree)](#rbtred-black-tree)
    - [RBT 정의](#rbt-정의)
    - [RBT 특징](#rbt-특징)
    - [RBT 삽입 연산](#rbt-삽입-연산)
    - [RBT 삭제 연산](#rbt-삭제-연산)
    - [Reference](#reference)
  - [B-Tree](#b-tree)
    - [B-Tree 규칙](#b-tree-규칙)
  - [B+-Tree](#b-tree-1)
  - [B-Tree vs B+-Tree](#b-tree-vs-b-tree)
- [Hash Table](#hash-table)
  - [Hash Function](#hash-function)
  - [Resolve Collision](#resolve-collision)
- [Graph](#graph)
  - [정점과 간선의 집합, Graph](#정점과-간선의-집합-graph)
  - [그래프 관련 용어 정리](#그래프-관련-용어-정리)
    - [Undirected Graph 와 Directed Graph](#undirected-graph-와-directed-graph)
    - [Degree](#degree)
    - [가중치 그래프(weight graph)와 부분 그래프(sub graph)](#가중치-그래프weight-graph와-부분-그래프sub-graph)
  - [그래프를 구현하는 두 방법](#그래프를-구현하는-두-방법)
    - [인접 행렬(adjacent matrix): 정방 행렬을 사용하는 방법](#인접-행렬adjacent-matrix-정방-행렬을-사용하는-방법)
    - [인접 리스트(adjacent list): 연결 리스트를 사용하는 방법](#인접-리스트adjacent-list-연결-리스트를-사용하는-방법)
  - [그래프 탐색](#그래프-탐색)
    - [깊이 우선 탐색(Depth First Search: DFS)](#깊이-우선-탐색depth-first-search-dfs)
    - [너비 우선 탐색(Breadth First Search: BFS)](#너비-우선-탐색breadth-first-search-bfs)
  - [MST(Minimum Spanning Tree)](#mstminimum-spanning-tree)
    - [Kruskal Algorithm](#kruskal-algorithm)


# Array

배열은 논리적 저장순서와 물리적 저장순서가 일치하는 특정 자료형들이 메모리 공간 상에서 연속적으로 이루어진 자료형이다.

## Array 특징

__접근 속도__ 는 찾고자 하는 원소의 인덱스 값을 알고 있으면 `Big-O(1)`에 해당 원소를 접근할 수 있다.

__삭제__ 과정에서는 해당 원소를 접근한 뒤(O(1)), 연속적인 특징을 유지하기 위해 빈 공간을 `shift` 해줘야 하는 cost가 발생하고 이 경우 `Big-O(n)`이 된다.

__삽입__ 과정에서는 해당 원소를 접근한 뒤 (O(1)), 삽입 부분 뒤에 있는 원소들을 `shift` 해줘야 한다. 따라서 최악의 경우 n개의 배열에서 첫번째 자리에 원소를 넣었을 때 나머지 모든 원소들이 1씩 `shift` 해야 하기때문에 `Big-O(n)`의 시간 복잡도를 요구하게 된다.

__메모리 할당__ 은 `array`가 선언되자 마자 Compile time 에 할당이 이루어진다. 이를 정적 메모리 할당이라고 한다.

결론적으로 데이터 접근이 빈번하게 일어날 경우 Array를 사용하는 것이 좋다고 볼 수 있다.

[Back](../Readme.md) / [Top](#data-structure)


# Linked List

`Array` 에서 삽입, 삭제 시 나머지 원소들을 `shift`해줘야 한다는 문제점을 해결하기 위한 자료구조이다. 각 원소들은 자신과 근접한 원소만을 기억한다. 

## Linked List 특징

__삽입__ 과 __삭제__ 가 `Big-O(1)` 만에 해결될 수 있다는 장점을 가지고 있다.

하지만 원하는 위치에 접근하기 위해서는 모든 원소를 다 확인해야 한다는 문제점이 있다. Array와는 다르게 논리적 저장 순서와 물리적 저장 순서가 일치하지 않기 때문이다. 따라서 __삽입__, __삭제__ 과정이 일어났을 때, 목표 원소를 찾기 위해 `Big-O(n)`의 시간이 추가적으로 발생한다. 하지만 메모리를 동적으로 할당 받는 특징이 있어 `array`에서의 삽입 삭제에 비해 빠르게 연산이 수행된다.

결론적으로 `Linked List`는 메모리 접근, 삽입, 삭제 모두 `Big-O(n)`에 해당하는 time complexity를 가진다. 하지만 이 자료형은 `Tree` 구조의 근간이 되며, `Tree`에서 사용됐을 때 그 유용성이 드러난다.

[Back](../Readme.md) / [Top](#data-structure)

# Array List

`Dynamic Array`라고도 불리며 이름과 같이 내부적으로 배열을 사용하여 데이터를 관리한다. `Index`를 통해 데이터 검색에 적합하고 선형 시간복잡도 `Big-O(1)`를 가져 속도가 빠르다.

하지만 데이터 삽입 삭제 시 해당 데이터를 제외한 모든 데이터를 임시 배열에 복사하기 때문에 `Big-O(n)`의 시간 복잡도를 가지며 부적합하다.

[Back](../Readme.md) / [Top](#data-structure)

# Stack

선형 자료구조의 일종으로 (Last-In-First-Out,LIFO)나중에 들어간 원소가 먼저 나온다. `Stack`의 가장 큰 특징으로 주로 웹 브라우저의 뒤로가기나 문서 파일에서 시간 별 저장하기에 사용된다.

LIFO의 구조를 띄기 때문에 제일 상단(top)과 하단(bottom)에 있는 원소들이 중요하며 상단에 데이터를 __탐색__ 시간 복잡도는 `Big-O(n)`, __삽입__, __삭제__ 시간 복잡도는 `Big-O(1)`을 가진다.

이때 삽입 연산은 `push`, 삭제 연산은 `pop`이라고 불린다.

[Back](../Readme.md) / [Top](#data-structure)

# Queue

선형 자료구조의 일종으로 (First In First Out, FIFO) 나중에 들어간 원소가 먼저 나오는 형태의 구조를 가진다. 주로 버퍼나 bfs 탐색 등에 사용된다.

FIFO의 구조를 띄기 때문에 최 상단(top)과 최 하단(bottom)의 원소들이 주로 참조되며 __탐색__ 시간 복잡도는 `Big-O(n)`, __삽입__, __삭제__ 시간 복잡도는 `Big-O(1)`을 가진다.

[Back](../Readme.md) / [Top](#data-structure)

# Tree

나무를 거꾸로 세워놓은 듯 한 모양이라서 생긴 이름으로 스택이나 큐와 같은 선형 구조가 아닌 비선형 자료구조이다. 계층적 관계(Hierarchical Realtionship)을 표현한다.

## Tree 용어

- Node(노드): 트리를 구성하고 있는 각 요소
- Edge(간선): 트리를 구성하기 위해 노드와 노드를 연결하는 선
- Level(레벨): 각 노드가 위치한 층
- Root Node(루트 노드): 트리 구조에서 최상위에 있는 노드를 의미
- Terminal Node(Leaf Node, 단말 노드): 하위에 노드가 연결되어있지 않은 노드
- Internal Node(내부 노드, 비단말 노드): 단말노드를 제외한 모든 노드로 루트 노드를 포함한다.
  - Child Node(자식 노드): 상위 레벨에 자신을 연결한 노드가 존재하는 노드
  - Parent Node(부모 노드): 하위 레벨에 연결되는 노드가 존재하는 노드

## Binary Tree

노드의 개수가 n개이고, root가 0이 아닌 1에서 시작할 때, i 번째 노드에 대해서 `Paraent(i) = i / 2`,` left child(i) = 2 * i`, `right child(i) = 2 * i + 1`의 index 값을 가진다.

- Full Binary Tree(정 이진 트리)
  
  모든 노드가 0개 혹은 2개의 자식 노드만을 갖는 이진 트리

- Complete Binary Tree(완전 이진 트리)

  위에서 아래로, 왼쪽에서 오른쪽으로 순서에 맞게 채워진 이진 트리

- Perfect Binary Tree(포화 이진 트리)
  
  모든 레벨이 꽉 찬 이진 트리

- Skewd Tree(편향 트리)
  
  노드가 고루 분산되지 않고 편향을 이루는 트리
  
[Back](../Readme.md) / [Top](#data-structure)

## BST(Binary Search Tree)

`Binary tree`의 일종으로 데이터를 저장하는 규칙이 있다.

1. `BST`의 노드에 저장된 key는 유일하다.
2. Parent key > left child key
3. Parent key < right child key
4. 모든 `sub tree`는 `BST`이다.

BST의 탐색 연산은 `Big-O(log n)`의 시간 복잡도를 갖는다. 하지만 `skewed tree`가 될 경우 성능에 영향을 미쳐 'Big-O(n)`의 시간 복잡도를 가지게 된다.

이럴경우 배열보다 많은 메모리 사용에도 불구하고 시간복잡도가 동일한 비효율적인 상황이 발생한다. 이를 해결하기 위해 트리의 구조를 재조정하는 `Rebalancing` 기법이 등장한다.

[Back](../Readme.md) / [Top](#data-structure)

## Binary Heap

자료구조의 일종으로 Tree의 형식을 하고 있으며, Tree 중에서도 배열에 기반한 `Complete Binary Tree`이다. 배열에 트리의 값들을 넣어줄 때, 1번 index부터 루트 노드가 시작된다. 우선순위 큐의 개념을 도입하기 위해 만들어졌으며 시뮬레이션 시스템, 작업 스케줄링 등에 사용되며 __최소 힙(min heap)__, __최대 힙(max heap)__ 이 존재한다.

- `Max Heap`: 각 노드의 값이 자식 노드의 값보다 크거나 같은 Complete Binary Tree
- `Min Heap`: `Max Heap`의 반대

`Max Heap`에서는 Root node에 있는 값이 제일 크기 때문에 최대값을 찾는데 소요되는 시간 복잡도가 `Big-O(1)`이다. 또한 `complete binary tree`이기 때문에 배열을 사용하여 효율적으로 관리할 수 있다.(random access가 가능) 하지만 heap의 구조를 계속 유지하기 위해서 제거된 root node를 대체할 다른 노드가 필요하다. 여기서 heap은 맨 마지막 node를 root node로 대체시킨 후 다시 구조를 유지한다.

이 경우 `Big-O(log n)`의 시간복잡도로 최대값이나 최소값에 접근할 수 있다.
### Heap 구현

부모 노드와 자식 노드의 관계

- 왼쪽 자식 Index: (부모 Index) * 2
- 오른쪽 자식 Index: (부모 Index) * 2 + 1
- 부모 Index: (자식 Index) / 2

### Heapify

두개의 `sub tree`가 `max heap(min heap)`일 때, root를 포함하는 전체가 heap이 되도록 위치를 조정하는 과정이다. Root에서 작은 값이 흘러 내려가면서 처리되는 방식으로 진행된다.

 `max heap`의 경우 root가 child보다 작으면 두 개의 child node 중 값이 큰 노드를 root와 교체하고 교체할 노드가 없을 때 까지 반복한다.

[Back](../Readme.md) / [Top](#data-structure)

## RBT(Red Black Tree)

BST를 기반으로 하는 트리 형식의 자료구조로 __Search__, __Insert__, __Delete__ 에 `Big-O(log n)`의 시간 복잡도가 소요된다. 동일한 노드의 개수에서 depth를 최소화하여 시간복잡도를 줄이는 것이 핵심 아이디어로, 동일한 노드의 개수일 때, depth가 __최소__ 가 되는 경우는 __complete binary tree__ 인 경우다.

### RBT 정의

1. 각 노드는 `red` or `black`이라는 색을 가진다.
2. Root node와 leaf node는 `black`이다
3. 어떤 노드가 `red`일 경우 두 children은 모두 `black`이다.
4. 각 노드에 대해서 노드로부터 descendant leaves 까지의 단순 경로는 모두 같은 수의 black nodes들을 포함하고 있다. 이를 해당 노드의 `Black-Height` 라고 한다. 

    cf) Black-Height: 노드 x 로부터 노드 x 를 포함하지 않은 leaf node 까지의 simple path 상에 있는 black nodes 들의 개수

### RBT 특징

1. BST의 특징을 모두 가짐
2. Root node 부터 leaf node 까지의 모든 경로 중 최소 경로와 최대 경로의 크기 비율은 2보다 크지 않다.(`balanced` 상태)
3. 노드의 child가 없을 경우 child를 가리키는 포인터는 NIL값을 저장하며 이를 leaf node로 간주한다.

### RBT 삽입 연산

`BST`의 특성을 유지하면서 노드를 삽입한다. 삽입된 노드의 색을 `black-height` 변경을 최소화하기 위해 `red`로 지정한다. 만약 RBT 특성 위배 시 노드의 색을 조정하고, `black-height`가 위배 되었다면 rotation을 통해 height를 조정한다. 이를 통해 RBT의 동일한 레벨에 존재하는 internal node들의 `black-height`가 같아지고 최소 경로와 최대 경로의 크기 비율이 2 미만으로 유지된다.

### RBT 삭제 연산

`BST`의 특성을 유지하면서 해당 노드를 삭제한다. 삭제될 노드의 child의 개수에 따라 rotation 방법이 달라지게 된다. 만약 지워진 노드의 색이 `black`일 경우 `black-height`가 1 감소한 경로에 `black node`가 1개 추가되도록 rotation하고 노드의 색깔을 조정한다. 지워진 노드의 색이 `red`일 경우 조건에 위배되지 않아 RBT가 그대로 유지된다.

### Reference
[알고리즘) Red-Black Tree](https://zeddios.tistory.com/237)

[Back](../Readme.md) / [Top](#data-structure)

## B-Tree

데이터베이스, 파일 시스템에서 널리 사용되는 트리 자료구조로 이진 트리를 확장해서, 더 많은 수의 자식을 가질 수 있게 일반화 시킨 것이다. 자식 수에 대한 일반화를 통해 하나의 레벨에 더 저장되면서 트리의 균형을 맞춰주는 로직을 갖춘 트리이다.

### B-Tree 규칙
  
  - 노드의 자료 수가 N이면, 자식 수는 N+1
  - 각 노드의 자료는 정렬된 상태
  - Root node는 적어도 2개 이상의 자식을 가져야 한다.
  - Root node를 제외한 모든 노드는 적어도 M/2개의 자료를 가지고 있어야 한다.
  - 외부 노드로 가는 경로의 길이는 모두 동일
  - 입력 자료는 중복 될 수 없음

## B+-Tree

데이터의 빠른 접근을 위한 index 역할만 하는 비단말 노드가 추가로 존재하며 sequential search를 제공해주는 트리이다. internal node는 그저 데이터의 구분자 역할만 하고 실제 데이터가 들어 있는 구간은 leaf node이다. 따라서 데이터의 중복이 발생할 수 있다.

많은 `block size`를 이용할 수 있고, leaf node끼리 연결 리스트로 되어 sequential search를 수행할 수 있다는 장점이 있지만, leaf node까지 내려가봐야 탐색을 수행할 수 있다는 단점이 있다.

## B-Tree vs B+-Tree

B-Tree|B+-Tree
:--|:--
- 중복되는 노드가 없어서 사용하는 노드 수가 적음|- Fan-out 하는 내부노드의 수가 적어 높이가 더 낮음
- 단말노드 전에 값을 발견할 수 있음|- 삽입, 삭제 연산이 단순함

# Hash Table

내부적으로 배열을 사용하여 데이터를 저장하기 때문에 빠른 검색 속도를 갖는다. 특정한 값을 `Search` 하는데 데이터 고유의 `index`로 접근하게 되므로 `average case`에 대해 시간 복잡도가 `Big-O(1)`이 된다. 하지만 `key`값이 불규칙하다는 문제가 있다.

## Hash Function

고유한 `index` 값 설정이 중요한데 `hash function`은 저장되는 값들의 key 값을 작은 범위의 값들로 바꿔준다.

하지만 동일한 key 값에 복수개의 데이터가 하나의 테이블에 존재 하게 될 수 있는데 이를 `Collision`이라고 한다. 즉, 서로 다른 두 개의 다른 키가 같은 인덱스로 hashing된 경우이다.

`Hash function`은 키 일부분을 참조하여 해쉬 값을 만들지 않고 키 전체를 참조하여 해쉬 값을 만들어 낸다. 하지만 좋은 해쉬 함수는 키가 어떤 특성을 가지고 있느냐에 따라 달라진다.

__Collision__ 을 최소화 하는 방향으로 설계하고 발생하는 collision에 대비해 어떻게 대응할 것인가가 더 중요하다. 

## Resolve Collision

1. 개방 주소법(open addressing): 충돌이 발생할 경우 다른 해시 버킷에 해당 자료를 삽입

  - 선형 조사(linear probing)
  오버플로우 발생 시, home address부터 차례로 조사하여 가장 가까운 빈 공간을 찾아 삽입하는 방법이다. Worst case의 경우 빈 공간을 찾지 못하고 시작 위치로 되돌아 갈 수 있다. 또한 삽입/삭제를 반복하면서 레코드 저장 위치가 서로 바뀌는 경우가 생길 수 있다는 단점이 잇다.

2. 체인법(chaining): 오버플로우된 경우 저장 공간을 상대 파일 밖의 지정된 공간에서 해결한다. 즉, 독립된 오버플로우 구역을 유지한다.

  - 독립 오버플로우 구역(Separate Overflow Area)

    별개의 오버플로우 구역을 할당하여 오버플로우 뙨 모든 동거자들을 순차적으로 저장하는 방법이다. 동거자가 없는 레코드에 대해서 한번의 주소 접근만으로 레코들르 검색할 수 있으며, 환치 문제를 제거할 수 있다.
    
    하지만 오버플로우된 동거자를 접근하기 위해서 오버플로우 구역에 있는 모든 레코드들을 순차적으로 검색해야한다는 단점이 있다.

  - 이중 해싱(Double Hashing)

    오버플로우된 동거자들을 오버플로우 구역으로 직접 해싱하는 것으로 오버플로우 구역에서 순차 검색을 피할 수 있다. 일차 해시 함수에 의해 해싱이 된 후 오버 플로우가 발생하면 이차 해싱이 일어난다.

    오버플로우 구역에서의 순차 검색을 피할 수 있지만, 두 개의 해시 함수를 유지해야 하며, 충돌이 빈번한 경우 오버플로우 구역에서 환치와 같은 선형 조사의 문제점이 재발한다.

  - 동거자 체인(Synonym chaining)

    각 주소마다 링크를 두어 오버플로우된 레코드들을 연결하는 방법

    - 오버플로우가 일어나면 선형 조사나 오버플로우 구역을 이용해서 저장 후, 처음 해시 주소에 동거자를 포함하고 있는 주소에 대한 링크를 둠
    - 동거자에 대한 액세스는 링크로 연결된 동거자들만 조사해보면 됨
    - 독립 오버플로우 구역에 사용할 수도 있고, 원래의 상대 파일에 적용할 수도 있음

    Home address에서의 충돌이 감소되고, 충돌 시 순차 검색을 피할 수 있어, 검색 시간이 단축된다는 단점이 있다.

    각 주소가 링크 필드를 포함하도록 확장해야 한다. 이때 링크 필드를 유지하는 것이 오버헤드로 작용한다.

# Graph

## 정점과 간선의 집합, Graph

cf) 트리 또한 그래프이며, 그 중 사이클ㄹ이 허용되지 않는 그래프를 말한다.

## 그래프 관련 용어 정리

### Undirected Graph 와 Directed Graph

정점과 간선의 연결관계에 있어서 방향성이 없는 그래프를 undirected graph라 하고, 간선에 방향성이 포함되어 있는 그래프를 directed graph라고 한다.

- Directed Graph (Digraph)
```py
V = {1, 2, 3, 4, 5, 6}
E = {(1, 4), (2, 1), (3, 4), (3, 4), (5, 6)}
(u, v) = vertex u에서 vertex v로 가는 edge
```

- Undirected Graph
```py
V = {1, 2, 3, 4, 5, 6}
E = {(1, 4), (2, 1), (3, 4), (3, 4), (5, 6)}
(u, v) = vertex u에서 vertex v로 가는 edge
```

### Degree

Undirected Graph 에서 각 정점(vertex)에 연결된 간선(edge)의 개수를 degree라 한다. Directed Graph에서는 간선에 방향성이 존재하기 때문에 Degree가 두 개로 나뉘게 된다. 각 정점으로부터 나가는 간선의 개수를 outdegree 라 하고, 들어오는 간선의개수를 Indegree라 한다.

### 가중치 그래프(weight graph)와 부분 그래프(sub graph)

가중치 그래프란 간선에 가중치 정보를 두어서 구성한 그래프를 말한다. 반대의 개념인 비가중치 그래프 즉, 모든 간선의 가중치가 동일한 그래프도 물론 존재한다. 부분 집합과 유사한 개념으로 부분 그래프라는 것이 있다. 부분 그래프는 본래의 그래프의 일부 정점 및 간선으로 이루어진 그래프를 말한다.

## 그래프를 구현하는 두 방법

### 인접 행렬(adjacent matrix): 정방 행렬을 사용하는 방법

해당하는 위치의 값을 통해서 vertex 간의 연결 관계를 `Big-O(1)`으로 파악할 수 있다. Edge 개수와는 무관하게 `v^2`의 공간 복잡도를 가진다. Dense graph를 표현할 때 적절한 방법이다.

### 인접 리스트(adjacent list): 연결 리스트를 사용하는 방법

Vertex의 adjacent list를 확인해봐야 하므로 vertex 간 연결되어있는지 확인하는데 오래 걸린다. 공간 복잡도는 `Big-O(E + V)`로 sparse graph을 표현하는데 적당한 방법이다.

## 그래프 탐색

그래프는 정점의 구성 뿐 아니라 간선의 연결에도 규칙이 존재하지 않기 때문에 탐색이 복잡하다. 따라서 그래프의 모든 정점을 탐색하기 위한 방법은 다음의 두 가지 알고리즘을 기반으로 한다.

### 깊이 우선 탐색(Depth First Search: DFS)

그래프 상에 존재하는 임의의 한 정점으로부터 연결되어 있는 한 정점으로만 나아가면서 탐색한다. 연결된 정점이 긑날 때 까지 계속 지나가다가 더이상 연결되지 않은 정점이 없으면 그 전 단계의 정점으로 돌아가서 연결할 수 있는 정점이 있는지 살핀다. 이를 위해 `Stack`을 사용한다.

시간 복잡도: `Big-O(V+E)`

### 너비 우선 탐색(Breadth First Search: BFS)

그래프 상에 존재하는 임의의 한 정점으로부터 연결되어 있는 모든 정점으로 나아간다. Tree에서의 Level Order Traversal 형식으로 진행되는데 이를 위해 `Queue`를 사용한다. 정점을 `queue`에 삽입하고 `dequeue`하면서 dequeue되는 정점의 자식 노드들을 `enqueue`한다. 즉 정점들을 방문한 순서대로 queue에 저장하는 방법을 사용한다.

시간 복잡도: `Big-O(V+E)`

## MST(Minimum Spanning Tree)

그래프 G의 spanning tree 중 edge weight의 합이 최소인 `spanning tree`를 말한다.

### Kruskal Algorithm

초기화 작업으로 edge 없이 vertex 들만으로 그래프를 구성한다. 그리고 weight 가 제일 작은 edge 부터 검토한다. 그러기 위해선 edge