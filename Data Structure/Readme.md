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
  
## BST(Binary Search Tree)

`Binary tree`의 일종으로 데이터를 저장하는 규칙이 있다.

1. `BST`의 노드에 저장된 key는 유일하다.
2. Parent key > left child key
3. Parent key < right child key
4. 모든 `sub tree`는 `BST`이다.

BST의 탐색 연산은 `Big-O(log n)`의 시간 복잡도를 갖는다. 하지만 `skewed tree`가 될 경우 성능에 영향을 미쳐 'Big-O(n)`의 시간 복잡도를 가지게 된다.

이럴경우 배열보다 많은 메모리 사용에도 불구하고 시간복잡도가 동일한 비효율적인 상황이 발생한다. 이를 해결하기 위해 트리의 구조를 재조정하는 `Rebalancing` 기법이 등장한다.